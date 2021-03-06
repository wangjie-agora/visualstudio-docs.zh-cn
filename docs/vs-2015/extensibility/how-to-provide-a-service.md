---
title: 如何：提供服务 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 565a8a91797c826b6419dc5a8488d7d3baf9cddc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840520"
---
# <a name="how-to-provide-a-service"></a>如何：提供服务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPackage 可以提供其他 Vspackage 可以使用的服务。 若要提供服务，VSPackage 必须向 Visual Studio 注册服务并添加该服务。  
  
 <xref:Microsoft.VisualStudio.Shell.Package>类实现 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 和 <xref:System.ComponentModel.Design.IServiceContainer> 。 <xref:System.ComponentModel.Design.IServiceContainer> 包含提供按需服务的回叫方法。  
  
 有关服务的详细信息，请参阅 [Service Essentials](../extensibility/internals/service-essentials.md) 。  
  
> [!NOTE]
> 当 VSPackage 即将卸载时，Visual Studio 将等待，直到已提供 VSPackage 提供的服务的所有请求。 它不允许对这些服务的新请求。 卸载时，不应显式调用 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> 方法来撤消服务。  
  
#### <a name="implementing-a-service"></a>实现服务  
  
1. 创建 VSIX 项目 (**文件/新建/项目/Visual c #/所在/VSIX 项目**) 。  
  
2. 将 VSPackage 添加到项目。 在 **解决方案资源管理器** 中选择项目节点，然后单击 " **添加/新建项"/"Visual c # 项"/"扩展性/visual Studio 包**"。  
  
3. 若要实现服务，需要创建以下三种类型：  
  
   - 用于描述服务的接口。 其中的许多接口都是空的，也就是说，它们没有方法。  
  
   - 描述服务接口的接口。 此接口包含要实现的方法。  
  
   - 一个实现服务和服务接口的类。  
  
     下面的示例演示了三种类型的一个非常基本的实现。 服务类的构造函数必须设置服务提供程序。  
  
   ```csharp  
   public class MyService : SMyService, IMyService  
   {  
       private Microsoft.VisualStudio.OLE.Interop.IServiceProvider serviceProvider;  
       private string myString;  
       public MyService(Microsoft.VisualStudio.OLE.Interop.IServiceProvider sp)  
       {  
           Trace.WriteLine(  
                  "Constructing a new instance of MyService");  
           serviceProvider = sp;  
       }  
       public void Hello()  
       {  
           myString = "hello";  
       }  
       public string Goodbye()  
       {  
          return "goodbye";  
       }  
   }  
   public interface SMyService  
   {  
   }  
   public interface IMyService  
   {  
       void Hello();  
       string Goodbye();  
   }  
  
   ```  
  
### <a name="registering-a-service"></a>注册服务  
  
1. 若要注册服务，请将添加 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 到提供该服务的 VSPackage。 以下是示例：  
  
    ```csharp  
    [ProvideService(typeof(SMyService))]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [Guid(VSPackage1.PackageGuidString)]  
    public sealed class VSPackage1 : Package  
    {. . . }  
    ```  
  
     此属性 `SMyService` 在 Visual Studio 中注册。  
  
    > [!NOTE]
    > 若要注册用同一名称替换另一个服务的服务，请使用 <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute> 。 请注意，只允许对服务进行一次重写。  
  
### <a name="adding-a-service"></a>添加服务  
  
1. 1.  在 VSPackage 初始值设定项中，添加服务并添加一个回调方法来创建服务。 下面是对方法所做的更改 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> ：  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
    . . .  
    }  
    ```  
  
2. 实现回调方法，该方法应创建并返回服务，如果无法创建，则为 null。  
  
    ```  
    private object CreateService(IServiceContainer container, Type serviceType)  
    {  
        if (typeof(SMyService) == serviceType)  
            return new SMyService(this);  
        return null;  
    }  
    ```  
  
    > [!NOTE]
    > Visual Studio 可以拒绝请求来提供服务。 如果另一个 VSPackage 已提供该服务，则它会执行此操作。  
  
3. 现在，可以获取服务并使用其方法。 在初始值设定项中将显示这种情况，但你可以在想要使用该服务的任何位置获取该服务。  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
  
        MyService myService = (MyService) this.GetService(typeof(SMyService));  
        myService.Hello();  
        string helloString = myService.myString;  
  
        base.Initialize();  
    }  
    ```  
  
     的值 `helloString` 应为 "Hello"。  
  
## <a name="see-also"></a>另请参阅  
 [如何：获取服务](../extensibility/how-to-get-a-service.md)   
 [使用和提供服务](../extensibility/using-and-providing-services.md)   
 [服务基础知识](../extensibility/internals/service-essentials.md)
