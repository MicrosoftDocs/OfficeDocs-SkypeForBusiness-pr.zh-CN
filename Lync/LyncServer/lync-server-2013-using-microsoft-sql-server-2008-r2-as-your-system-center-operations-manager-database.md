---
title: Lync Server 2013：使用 Microsoft SQL Server 2008 R2 作为 System Center Operations Manager 数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0001d70033aac6d7c6125bb9e4016143beefc80f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-29_

若要将 SQL Server 2008 R2 用作后端数据库，请完成本主题中详细介绍的步骤。

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>配置 SQL Server 2008 R2 和 SQL Server Reporting Services

在开始安装 System Center Operations Manager 之前，必须对 SQL Server 2008 R2 和 SQL Server Reporting Services 配置进行两处更改。 （仅当您使用 SQL Server 2008 R2 作为 Operations Manager 数据库时，才需要进行这些更改。）首先，在将承载 Operations Manager 数据库的计算机上执行以下操作：

1.  单击“开始”****，再单击“运行”****。

2.  在 "**运行**" 对话框中，**键入 C\\： Program\\Files Microsoft SQL\\ Server\_MSRS10 ARCHINST\\Reporting Services\\ReportServer** ，然后按 enter。

3.  在 " **ReportServer** " 文件夹中，打开 "记事本" 或任何其他文本编辑器中的文件 " **rsreportserver** "。

4.  在文件的开头附近，你将看到一系列 "添加密钥" 节点。 查找开始** \<添加 Key = "SecureConnectionLevel"** 的条目，并将值设置为**0**：
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  保存文件 " **rsreportserver** "，然后关闭文本编辑器。

更新报表服务器配置文件后，必须将正确的证书分配给 SQL Server Reporting Services。 为此，请执行以下操作：

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft SQL Server 2008 R2**"、"**配置工具**"，然后单击 " **Reporting Services 配置管理器**"。

2.  在 " **Reporting Services 配置连接**" 对话框中，确保您的服务器名称显示在 "**服务器名称**" 框中。 从 "**报表服务器实例**" 下拉列表中选择将承载 Operations Manager 数据库的 SQL Server 实例（例如， **ARCHINST**），然后单击 "**连接**"。

3.  在 Reporting Services 配置管理器中，单击 " **Web 服务 URL**"。

4.  在 " **Web 服务 URL** " 页上，从 " **SSL 证书**" 下拉列表中选择要用于您的 Reporting Services 的证书，然后单击 "**应用**"。 几秒钟后，您将看到 "**报表服务器 Web 服务 url**" 下列出的一对 url。

5.  单击这两个 Url 以验证您是否可以访问 SQL Server Reporting Services。

6.  关闭 Reporting Services 配置管理器。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据库

如果要将 System Center Operations Manager 配置为使用 SQL Server 2008 R2 数据库，将需要 "手动" 在运行 SQL Server 2008 R2 的计算机上创建 Operations Manager 数据库。 （同样，如果您使用 SQL Server 2005 或 SQL Server 2008 作为后端数据库，则不需要执行这些步骤。）

若要手动创建 Operations Manager 数据库，请执行以下操作：

1.  在 System Center Operations Manager 2007 R2 安装介质上，在 SupportTools\\AMD64 文件夹中，双击 " **DBCreateWizard**"。

2.  在数据库配置向导中的 "**欢迎使用数据库配置向导**" 页上，单击 "**下一步**"。

3.  在**数据库信息**页面上，将所有设置保留为，然后单击 "**下一步**"

4.  在 "**管理组配置**" 页上，在 "**管理组名称**" 框中键入管理组的名称（例如， **Lync Server Monitoring**），然后单击 "**下一步**"。

5.  在 " **Operations Manager 错误报告**" 页上单击 "**下一步**"。

6.  在 "**摘要**" 页上单击 "**完成**"。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>创建用于 SQL Server 2008 R2 的 System Center Operations Manager 数据仓库

Microsoft Lync Server 2013 随附三个新的 System Center Operations Manager 报告：

  - **端到端方案可用性报告**   此报告详细介绍了关键 Lync Server 服务（如注册或状态）的可用性/正常运行时间。

  - **容量报告**   使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用情况）的趋势。

  - **组件报告**   此报告列出按 Lync Server 组件分组的顶部警报生成器。

必须安装 System Center Operations Manager 数据仓库，才能使用这些新报告。 （数据仓库为运营数据长期存储提供。）若要将数据仓库与 SQL Server 2008 R2 一起使用，必须在承载 SQL Server 数据库的计算机上执行以下步骤：

1.  在 System Center Operations Manager 安装程序媒体的 "Setup\\SupportTools\\AMD64" 文件夹中，双击 " **DBCreateWizard**"。

2.  在数据库配置向导中的 "**欢迎使用数据库配置向导**" 页上，单击 "**下一步**"。

3.  在 "**数据库信息**" 页上，从 "**数据库类型**" 下拉列表中选择 " **Operations Manager 数据仓库数据库**"，然后单击 "**下一步**"。

4.  在 "**摘要**" 页上单击 "**完成**"。

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>安装 System Center Operations Manager 控制台

Operations Manager 控制台是用于管理 System Center Operations Manager 的主要工具。 在安装 Operations Manager 控制台之前，请确保已安装支持的 SQL Server 版本和 SQL Server Reporting Service。 此外，还建议您运行 SQL Server 的 Reporting Services 配置管理器，以验证是否已正确安装和配置报告服务。

若要安装 System Center Operations Manager 控制台，请执行以下操作：

1.  在 System Center Operations Manager 安装程序媒体上，双击 " **SetupOM**"。

2.  在 System Center Operations Manager 2007 R2 安装程序中，单击 "**检查必备组件**"。

3.  在 System Center Operations Manager 必备组件查看器中，选择要安装的 System Center 组件：（**服务器**;**控制台**;和**PowerShell**），然后单击 "**检查**"。 验证是否未报告任何阻止问题，然后单击 "**关闭**"。 如果已报告阻止问题，请更正问题，然后单击 "**检查**" 以重新运行先决条件测试。

4.  在 System Center Operations Manager 安装程序中，单击 "**安装 Operations Manager**"。

5.  在 System Center Operations Manager 安装向导中，在 "**欢迎使用 System Center Operations Manager 安装向导**" 页上，单击 "**下一步**"。

6.  在 "**最终用户许可协议**" 页上，选择 "**我接受许可协议中的条款"** ，然后单击 "**下一步**"。

7.  在 "**产品注册**" 页上，在 "**用户名**" 框中键入您的姓名，并在 "**组织**" 框中键入您的组织的名称。 在 "**输入25个数字的 CD 密钥**" 框中键入 System Center Operations Manager 产品密钥，然后单击 "**下一步**"。

8.  在 "**自定义安装**" 页上，选择要安装的 System Center 选项，然后单击 "**下一步**"。 应选择要安装的**管理服务器**、**用户界面**和**Web 控制台**。 不应选择**数据库**且不应安装它。

9.  在 " **SC Database Server Instance** " 页上，验证安装了 Operations Manager 数据库的计算机的名称是否出现在 " **System Center 数据库服务器**" 框中。 单击“**下一步**”。

10. 在 "**管理服务器操作帐户**" 页上，选择 "**域或本地计算机帐户**"，然后在 "**用户帐户**"、"**密码**" 和 "**域" 或 "本地计算机**" 框中输入适当的值。 单击“**下一步**”。

11. 在 " **SDK 和 Config 服务帐户**" 页上，选择 "**域或本地计算机帐户**"，然后在 "**用户帐户**"、"**密码**" 和 "**域" 或 "本地计算机**" 框中输入适当的值。 单击“**下一步**”。

12. 在 " **Operations Manager 错误报告**" 页上单击 "**下一步**"。

13. 在 "**客户体验改善计划**" 页上，单击 "**下一步**"。

14. 在 "**准备安装程序"** 页上，单击 "**安装**"。

15. 在 "**正在完成 System Center Operations Manager 安装程序**" 页上，清除 "**备份加密密钥**" 并**启动控制台复选框**，然后单击 "**完成**"。

16. 在 System Center Operations Manager 安装程序中，单击 "**退出**"。

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>安装 System Center Reporting Services

在安装和配置 System Center Operations Manager 控制台之后，必须安装 System Center Reporting Services。 如果要将 SQL Server 2008 R2 用作 Operations Manager 后端数据库，则意味着必须首先对与 SQL Server Reporting Services 关联的安全组进行临时更改。 如果使用的是 SQL Server 2008 R2，则必须执行以下操作：

1.  单击"开始"，指向"管理工具"，然后单击"服务器管理器"。

2.  在服务器管理器中，展开“配置”****，展开“本地用户和组”****，然后单击“组”****。

3.  找到以下组，其中 atl-ws-01-001 表示您的计算机的名称，ARCHINST 表示 System Center 数据库的 SQL Server 实例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。

4.  右键单击该组，然后单击 "**重命名**"。 通过从组名称中删除** \_50**来重命名组。 例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。

5.  关闭服务器管理器。

此时，你已准备好安装 System Center Reporting Services。 若要执行此操作：

1.  在 System Center Operations Manager 2007 R2 安装程序媒体上，双击 " **SetupOM**"。

2.  在 System Center Operations Manager 2007 R2 安装程序中，单击 "**安装 Operations Manager 报告**"。

3.  在 System Center Operations Manager 2007 R2 报告安装向导中，在 "**欢迎使用 Operations Manager 报告安装程序**" 页上，单击 "**下一步**"。

4.  在 "**最终用户许可协议**" 页上，选择 "**我接受许可协议的条款"** ，然后单击 "**下一步**"。

5.  在 "**产品注册**" 页上，确保 "**用户名**" 和 "**组织**" 框中显示您的姓名和组织名称，然后单击 "**下一步**"。

6.  在 "**自定义安装**" 页上，单击 "**报告服务器**"，然后选择 "**此组件和所有相关组件将安装在本地磁盘驱动器上**"。 单击 "**数据仓库**"，选择 "**此组件将不可用**"，然后单击 "**下一步**"。

7.  在 "**连接到根管理服务器**" 页上，在 "**根管理服务器**" 框中键入 Operations Manager 根管理服务器的名称，然后单击 "**下一步**"。

8.  在 "**连接到 Operations Manager 数据仓库**" 页上，在 " **sql server 实例**" 框中键入您的数据仓库所在的 sql server 实例。 （如果您的数据仓库位于默认实例中，只需键入服务器名称; 例如： atl-sql-001。）验证 "**名称**" 框中显示 "数据库名称**OperationsManagerDW** "，并在 " **SQL Server 端口**" 框中显示 "端口**1433** "。 单击“**下一步**”。

9.  在 " **Sql Server 报告实例**" 页上，从 "**输入 Sql Server reporting Services 服务器**" 下拉列表中选择您的 sql server 报告服务器，然后单击 "**下一步**"。

10. 在 "**数据仓库写入帐户**" 页上，在 "**用户帐户**" 和 "**密码**" 框中输入要最初为其分配的对数据仓库的写入权限的用户的名称和密码。 从 "**域**" 下拉列表中选择用户的域，然后单击 "**下一步**"。

11. 在 "**数据读取器帐户**" 页上，输入 SQL Reporting Services 在 "**用户帐户**" 和 "**密码**" 框中查询数据仓库时要使用的用户帐户的名称和密码。 从 "**域**" 下拉列表中选择帐户域，然后单击 "**下一步**"。

12. 在 "**操作数据报告**" 页上，单击 "**下一步**"。

13. 在 " **Microsoft 更新**" 页上，单击 "**下一步**"。

14. 在 "**准备安装程序"** 页上，单击 "**安装**"。

15. 在 "**正在完成 Operations Manager 报告组件安装向导**" 页上，单击 "**完成**"。

16. 在 System Center Operations Manager 2007 R2 安装程序中，单击 "**退出**"。

安装 System Center reporting 后，请使用以下过程重置与 SQL Server 报告关联的安全组的名称。 同样，仅当您使用 SQL Server 时，才需要执行此过程：

1.  单击"开始"，指向"管理工具"，然后单击"服务器管理器"。

2.  在服务器管理器中，展开“配置”****，展开“本地用户和组”****，然后单击“组”****。

3.  找到以下组，其中 atl-ws-01-001 表示您的计算机的名称，ARCHINST 表示用于存档和监视数据库的 SQL Server 实例： **SQLServerReportServerUser $ atl-ws-01-001 $ MSRS10。ARCHINST**。

4.  右键单击该组，然后单击 "**重命名**"。 通过将** \_50**添加到组名称的末尾，在 SQL Server 实例名称前面添加 "." 对组进行重命名。 例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。

5.  关闭服务器管理器。

如果 System Center Operations 控制台处于打开状态，你将需要关闭应用程序，然后重新启动它;如果不执行此操作，则 "**报告**" 选项卡不会显示在操作控制台用户界面中。 请注意，第一次重新启动操作控制台之后，可能需要几分钟的时间，"**报告**" 选项卡上才会显示所有监控报告。

</div>

</div>

<span> </span>

</div>

</div>

</div>

