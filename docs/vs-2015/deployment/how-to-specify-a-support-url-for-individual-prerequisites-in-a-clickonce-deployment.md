---
title: 如何：为 ClickOnce 部署中的各个必备项指定支持 URL |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- ClickOnce deployment, URLs
ms.assetid: 590742c3-a286-4160-aa75-7a441bb2207b
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1907b619bcc616c73d9b9e37af30722c02bf100e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "65679971"
---
# <a name="how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment"></a>如何：为 ClickOnce 部署中的各个系统必备项指定一个支持 URL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]部署可以测试客户端计算机上必须提供的用于 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 运行应用程序的多个先决条件。 其中包括所需的最低版本 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 、操作系统的版本，以及必须在全局程序集缓存中预安装的任何程序集 (GAC) 。 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]但是，不能自行安装任何这些必备组件;如果找不到先决条件，它只是暂停安装并显示一个对话框，说明安装失败的原因。  
  
 安装必备组件有两种方法。 可以使用引导程序应用程序进行安装。 或者，您可以为单个必备项指定一个支持 URL，如果找不到先决条件，则会向用户显示该 URL。 该 URL 引用的页面可以包含指向有关安装所需必备组件的说明的链接。 如果应用程序没有为单独的先决条件指定支持 URL，则将 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 在应用程序的部署清单（如果已定义）中显示指定的支持 url。  
  
 尽管 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 、Mage.exe 和 MageUI.exe 均可用于生成 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 部署，但这些工具都不能直接支持为单独的先决条件指定支持 URL。 本文档介绍如何修改部署的应用程序清单和部署清单，以包含这些支持 Url。  
  
### <a name="specifying-a-support-url-for-an-individual-prerequisite"></a>为单个必备项指定支持 URL  
  
1. 在文本编辑器中打开应用程序清单， (应用程序的清单文件) 。 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]  
  
2. 对于操作系统必备，请将属性添加 `supportUrl` 到元素中 `dependentOS` ：  
  
    ```  
     <dependency>  
        <dependentOS supportUrl="http://www.adatum.com/MyApplication/wrongOSFound.htm">  
          <osVersionInfo>  
            <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" servicePackMinor="0" />  
          </osVersionInfo>  
        </dependentOS>  
      </dependency>  
    ```  
  
3. 对于特定版本的公共语言运行时的先决条件，请将特性添加 `supportUrl` 到 `dependentAssembly` 指定公共语言运行时依赖项的项：  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/wrongClrVersionFound.htm">  
          <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.30319.0" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
4. 对于必须预安装在全局程序集缓存中的程序集的先决条件，请为 `supportUrl` `dependentAssembly` 指定所需程序集的元素设置：  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/missingSampleGACAssembly.htm">  
          <assemblyIdentity name="SampleGACAssembly" version="5.0.0.0" publicKeyToken="04529dfb5da245c5" processorArchitecture="msil" language="neutral" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
5. 可选。 对于面向 .NET Framework 4 的应用程序，请 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 在文本编辑器中打开应用程序 (应用程序文件) 的部署清单。  
  
6. 对于 .NET Framework 4 必备项，请将 `supportUrl` 属性添加到 `compatibleFrameworks` 元素：  
  
    ```  
    <compatibleFrameworks  xmlns="urn:schemas-microsoft-com:clickonce.v2" supportUrl="http://adatum.com/MyApplication/CompatibleFrameworks.htm">  
      <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.30319" />  
      <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.30319" />  
    </compatibleFrameworks>  
    ```  
  
7. 手动更改应用程序清单后，必须使用数字证书对应用程序清单进行重新签名，然后更新并重新签署部署清单。 你必须使用 Mage.exe 或 MageUI.exe SDK 工具来完成此任务，因为重新生成这些文件时，将会 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 清除你的手动更改。 有关使用 Mage.exe 清单进行重新签名的详细信息，请参阅[如何：为应用程序和部署清单重新签名](../deployment/how-to-re-sign-application-and-deployment-manifests.md)。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 如果将应用程序标记为在部分信任环境中运行，则不会在对话框中显示支持 URL。  
  
## <a name="see-also"></a>另请参阅  
 [Mage.exe (清单生成和编辑工具) ](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)   
 [演练：手动部署 ClickOnce 应用程序](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [\<compatibleFrameworks> Element](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [ClickOnce 和 Authenticode](../deployment/clickonce-and-authenticode.md)   
 [应用程序部署先决条件](../deployment/application-deployment-prerequisites.md)
