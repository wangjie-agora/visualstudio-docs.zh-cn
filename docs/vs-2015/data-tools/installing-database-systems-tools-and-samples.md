---
title: 安装数据库系统、工具和示例 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- sample databases
- databases, samples
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
caps.latest.revision: 31
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 091338e411369e40f19e028cd19b6cb2e697718c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "74299608"
---
# <a name="installing-database-systems-tools-and-samples"></a>安装数据库系统、工具和示例
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 本身不包括它在内部使用的任何数据库系统。 若要在 Visual Studio 中开发数据连接的应用程序，通常需要在本地开发计算机上安装数据库系统，然后将应用程序和数据库部署到生产环境中。 为了使数据库系统可从 .NET 应用程序访问，并在 Visual Studio 数据工具窗口中可见，它必须具有 ADO.NET 数据提供程序。 如果计划在 .NET 应用程序中使用实体数据模型，则提供程序必须专门支持实体框架。     许多提供程序是通过 NuGet 包管理器或 Visual Studio 库提供的。

 对于 SQL 开发，请确保已在 Visual Studio 中安装 SQL Server Data Tools。 单击 " **查看** " 菜单。 如果看不到 SQL Server 对象资源管理器，请转到 "控制面板"，然后更改 Visual Studio。 在安装程序中，选择 " **Microsoft SQL Server Data Tools**"。

 如果使用的是 Azure 存储 Api，请在开发过程中在本地计算机上安装 Azure 存储模拟器，以避免收费，直到准备好部署到生产环境。 有关详细信息，请参阅 [使用 Azure 存储模拟器进行开发和测试](https://azure.microsoft.com/documentation/articles/storage-use-emulator/)。

 下面的列表包含一些可在 Visual Studio 项目中使用的更常用的数据库系统。 表格并不详尽。 有关提供 ADO.NET 数据提供程序的第三方供应商列表，这些提供程序可实现与 Visual Studio 工具的深度集成，请参阅 [ADO.NET 数据提供程序](https://msdn.microsoft.com/library/dd363565.aspx)。

### <a name="microsoft-sql-server"></a>Microsoft SQL Server
 SQL Server 是 Microsoft 旗舰数据库产品/服务。 SQL Server 2016 提供突破性的性能、高级安全性以及丰富的、集成的报告和分析。 它随附在为不同用途设计的各种版本中：从高度可缩放的高性能业务分析，到一台计算机上使用。 SQL Server Express 是一种功能齐全的 SQL Server 版本，专为重新分发和嵌入进行定制。  LocalDB 是 SQL Server Express 简化版本，无需进行任何配置，就能在应用程序的进程中运行。 你可以从 ["SQL Server Express 下载" 页](https://www.microsoft.com/sql-server/sql-server-editions-express)下载其中一个或两个产品。 本节中的许多 SQL 示例使用 SQL Server LocalDB。 SQL Server Management Studio (SSMS) 是一个独立的数据库管理应用程序，其功能比 Visual Studio SQL Server 对象资源管理器中提供的功能更多。 可以从上一个链接获取 SSMS。

### <a name="oracle"></a>Oracle
 你可以从 " [Oracle 技术网络](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html) " 页下载 oracle 数据库的付费或免费版本。 对于实体框架和 Tableadapter 的设计时支持，将需要 [Oracle 开发人员工具 For Visual Studio](https://www.oracle.com/database/technologies/developer-tools/visual-studio/)。 其他官方 Oracle 产品（包括 Oracle 即时客户端）可通过 NuGet 包管理器获得。  可以按照 [Oracle 联机文档](https://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm)中的说明下载 oracle 示例架构。

### <a name="mysql"></a>MySQL
 MySQL 是一种常用的开源数据库系统，广泛用于企业和网站。 Mysql、Visual Studio 和相关产品的下载在 [Windows 上的 mysql](https://www.mysql.com/why-mysql/windows/)中。  第三方提供各种 Visual Studio 扩展和 MySQL 独立管理应用程序。 可以在 nuget 包管理器中浏览产品 (**工具**"  >  **nuget 包管理器**" "  >  **管理解决方案) 的 NuGet 包**"。

### <a name="postgresql"></a>PostgreSQL
 PostgreSQL 是一个免费的开源对象关系数据库系统。 若要在 Windows 上安装，可以从 [PostgreSQL 下载页](http://www.postgresql.org/download/windows/)下载。  还可以从源代码生成 PostgreSQL。  PostgreSQL 核心系统包含 C 语言接口。 许多第三方提供了用于从 .NET 应用程序使用 PostgreSQL 的 NuGet 包。  可以在 nuget 包管理器中浏览产品 (**工具**"  >  **nuget 包管理器**" "  >  **管理解决方案) 的 NuGet 包**"。 最常见的包可能由 [npgsql.org](http://www.npgsql.org/)提供。

### <a name="sqlite"></a>SQLite
 SQLite 是在应用程序自身的进程中运行的嵌入式 SQL 数据库引擎。 可以从 [SQLite 下载页面](http://www.sqlite.org/download.html)下载。 还提供了许多用于 SQLite 的第三方 NuGet 包。 可以在 nuget 包管理器中浏览产品 (**工具**"  >  **nuget 包管理器**" "  >  **管理解决方案) 的 NuGet 包**"。

### <a name="firebird"></a>Firebird
 Firebird 是一个开源 SQL 数据库系统。 可以从 [Firebird 下载页](http://firebirdsql.org/en/downloads/)下载。 可以通过 NuGet 包管理器使用 ADO.NET 数据提供程序。

## <a name="see-also"></a>另请参阅
 [如何确定 SQL Server 及其组件的版本和版本类别](https://support.microsoft.com/help/321185/how-to-determine-the-version-edition-and-update-level-of-sql-server-an)
