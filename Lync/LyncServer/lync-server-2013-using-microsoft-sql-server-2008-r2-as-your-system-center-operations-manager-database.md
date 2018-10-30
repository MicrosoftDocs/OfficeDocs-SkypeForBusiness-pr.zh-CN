---
title: 将 Microsoft SQL Server 2008 R2 用作 System Center Operations Manager 数据库
TOCTitle: 将 Microsoft SQL Server 2008 R2 用作 System Center Operations Manager 数据库
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49888301
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Microsoft SQL Server 2008 R2 用作 System Center Operations Manager 数据库

 

_**上一次修改主题：** 2013-07-29_

要使用 SQL Server 2008 R2 作为您的后端数据库，请完成本主题中介绍的具体步骤。

## 配置 SQL Server 2008 R2 和 SQL Server Reporting Services

在开始安装 System Center Operations Manager 之前，您必须对您的 SQL Server 2008 R2 和 SQL Server Reporting Services 配置做两处修改。（仅在您使用 SQL Server 2008 R2 作为您的 Operations Manager 数据库时才需要进行这些更改。）首先，在将承载您的 Operations Manager 数据库的计算机上执行下列操作：

1.  单击“开始”，然后单击“运行”。

2.  在“运行”对话框中，键入 **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer**，然后按 Enter。

3.  在 **ReportServer** 文件夹中，用记事本或任何其他文本编辑器打开文件 **rsreportserver.config**。

4.  在文件开头附近，您会看到一系列的“Add Key”（添加键）节点。找到以 **\<Add Key="SecureConnectionLevel"** 开头的项并将其值设置为**0**：
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  保存文件 **rsreportserver.config** 然后关闭文本编辑器。

更新报表服务器配置文件后，必须将正确的证书分配给 SQL Server Reporting Services。为此，请执行下列操作：

1.  依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”、“Reporting Services 配置管理器”。

2.  在“Reporting Services 配置连接”对话框中，确保您的服务器的名称显示在“服务器名称”框中。从“报表服务器实例”下拉列表中选择将承载您的 Operations Manager 数据库的 SQL Server 实例（例如，**ARCHINST**），然后单击“连接”。

3.  在 Reporting Services 配置管理器中，单击“Web 服务 URL”。

4.  在“Web 服务 URL”页面上，从“SSL 证书”下拉列表选择要用于您的 Reporting Services 的证书，然后单击“应用”。几秒钟后，您会看到在“报表服务器 Web 服务 URL”下列出一对 URL。

5.  单击两个 Url 验证您是否可以访问 SQL Server Reporting Services。

6.  关闭 Reporting Services 配置管理器。

## 创建 System Center Operations Manager 数据库以用于 SQL Server 2008 R2

如果您要配置 System Center Operations Manager 以使用 SQL Server 2008 R2 数据库，需要在运行 SQL Server 2008 R2 的计算机上“手动”创建 Operations Manager 数据库。（另外，如果您正在使用 SQL Server 2005 或 SQL Server 2008 作为后端数据库，则不需要这些步骤。）

若要手动创建 Operations Manager 数据库，请执行以下操作：

1.  在 System Center Operations Manager 2007 R2 安装媒体的 SupportTools\\AMD64 文件夹中，双击 **DBCreateWizard.exe**。

2.  在数据库配置向导的“欢迎使用数据库配置向导”页面上，单击“下一步”。

3.  保持“数据库信息”页面上的所有设置不变，然后单击“下一步”

4.  在“管理组配置”页面上，在“管理组名称”框中键入您的管理组名称（例如，**Lync Server 监控**），然后单击“下一步”。

5.  在“Operations Manager 错误报表”页面上，单击“下一步”。

6.  在“摘要”页面上，单击“完成”。

## 创建 System Center Operations Manager 数据仓库以用于 SQL Server 2008 R2

Microsoft Lync Server 2013 附带三种新的 System Center Operations Manager 报告：

  - **端到端方案可用性报告**   此报告详细说明了关键 Lync Server 服务（如注册或状态等）的可用性/正常运行时间。

  - **容量报告**   使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用）的趋势

  - **组件报告**   此报告列出按 Lync Server 组件进行分组的顶级警报生成器。

为了使用这些新的报告，您必须安装 System Center Operations Manager 数据仓库。（数据仓库为操作数据提供长期存储。）若要通过 SQL Server 2008 R2 使用数据仓库，必须在承载您的 SQL Server 数据库的计算机上执行下列步骤：

1.  在 System Center Operations Manager 安装媒体的 Setup\\SupportTools\\AMD64 文件夹下，双击 **DBCreateWizard.exe**。

2.  在数据库配置向导的“欢迎使用数据库配置向导”页面上，单击“下一步”。

3.  在“数据库信息”页面上，从“数据库类型”下拉列表中选择“Operations Manager 数据仓库数据库”，然后单击“下一步”。

4.  在“摘要”页面上，单击“完成”。

## 安装 System Center Operations Manager 控制台

Operations Manager 控制台是用于管理 System Center Operations Manager 的主要工具。在安装 Operations Manager 控制台之前，请确保已安装了受支持的 SQL Server 版本和 SQL Server Reporting Services。另外，建议您还应运行 SQL Server 的 Reporting Services 配置管理器以验证 Reporting Services 是否已正确安装和配置。

若要安装 System Center Operations Manager 控制台，请执行以下操作：

1.  在 System Center Operations Manager 安装媒体上，双击 **SetupOM.exe**。

2.  在 System Center Operations Manager 2007 R2 安装程序中，单击“检查先决条件”。

3.  在 System Center Operations Manager 先决条件查看器中，选择要安装的 System Center 组件：（**服务器**；**控制台**；**PowerShell**），然后单击“检查”。验证未报告阻止问题后，单击“关闭”。如果已报告阻止问题，则纠正该问题，然后单击“检查”来重新运行先决条件测试。

4.  在 System Center Operations Manager 安装程序中，单击“安装 Operations Manager”。

5.  在 System Center Operations Manager 安装向导的“欢迎使用 System Center Operations Manager 安装向导”页面上，单击“下一步”。

6.  在“最终用户许可协议”页面上，单击“我接受许可协议中的条款”，然后单击“下一步”。

7.  在“产品注册”页面上，在“用户名称”框中键入您的姓名，在“组织”框中键入贵组织的名称。在“输入您的 25 位 CD 密钥”框中键入您的 System Center Operations Manager 产品密钥，然后单击“下一步”。

8.  在“自定义安装”页面上选择要安装的 System Center 选项，然后单击“下一步”。您应该选择安装“管理服务器”、“用户界面”和“Web 控制台”。不应选择和安装“数据库”。

9.  在“SC 数据库服务器实例”页面上，验证安装了 Operations Manager 数据库的计算机的名称是否出现在“System Center 数据库服务器”框中。单击“下一步”。

10. 在“管理服务器操作帐户”页面上，选择“域或本地计算机帐户”，然后在“用户帐户”、“密码”和“域或本地计算机”框中输入适当值。单击“下一步”。

11. 在“SDK 和配置服务帐户”页面上，选择“域或本地计算机帐户”，然后在“用户帐户”、“密码”和“域或本地计算机”框中输入适当值。单击“下一步”。

12. 在“Operations Manager 错误报告”页面上，单击“下一步”。

13. 在“客户体验改善计划”页面上，单击“下一步”。

14. 在“准备安装程序”页面上，单击“下一步”。

15. 在“正在完成 System Center Operations Manager 安装”页面上，清除“备份加密密钥”和“启动控制台”复选框，然后单击“完成”。

16. 在 System Center Operations Manager 安装程序中，单击“退出”。

## 安装 System Center Reporting Services

安装和配置 System Center Operations Manager 控制台后，您必须安装 System Center Reporting Services。如果您正在使用SQL Server 2008 R2 作为您的 Operations Manager 后端数据库，这意味着您必须先对与 SQL Server Reporting Services 关联的安全组做临时修改。如果您正在使用 SQL Server 2008 R2，则必须执行以下操作：

1.  单击“开始”，指向“管理工具”，然后单击“服务器管理器”。

2.  在“服务器管理器”中，展开“配置”，展开“本地用户和组”，然后单击“组”。

3.  找到下面的组，其中 atl-sc-001 表示您的计算机的名称，ARCHINST 表示 System Center 数据库的 SQL Server 实例：**SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST** 。

4.  右键单击该组，然后单击“重命名”。从组名称中删除“\_50”来重命名组。例如：**SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**。

5.  关闭服务器管理器。

此时，您可以安装 System Center Reporting Services 了。为此，请执行下列操作：

1.  在 System Center Operations Manager 2007 R2 安装媒体上双击 **SetupOM.exe** 。

2.  在 System Center Operations Manager 2007 R2 安装程序中，单击“安装 Operations Manager 报表”。

3.  在 System Center Operations Manager 2007 R2 报表安装向导的“欢迎使用 Operations Manager 报表安装程序”页面上，单击“下一步”。

4.  在“最终用户许可协议”页面上，单击“我接受许可协议中的条款”，然后单击“下一步”。

5.  在“产品注册”页面上，确保您的姓名和贵组织的名称出现在“用户名称”和“组织”文本框中，然后单击“下一步”。

6.  在“自定义安装”页面上，单击“报表服务器”，选择“此组件及所有相关组件将被安装在本地硬盘上”。单击“数据仓库”，选择“此组件将不可用”，然后单击“下一步”。

7.  在“连接到根管理服务器”页面上，在“根管理服务器”框中键入您的 Operations Manager 根管理服务器的名称，然后单击“下一步”。

8.  在“连接至 Operations Manager 数据仓库”页面上，在“SQL Server 实例”框中键入您的数据仓库所处于的 SQL Server 实例。（如果您的数据仓库位于默认实例中，则只需键入服务器名称；例如 atl-sql-001。）验证数据库名称“OperationsManagerDW”是否出现在“名称”框中，以及端口“1433”是否出现在“SQL Server 端口”框中。单击“下一步”。

9.  在“SQL Server Reporting 实例”页面上，从“输入 SQL Server Reporting Services 服务器”下拉列表中选择您的 SQL Server 报表服务器，然后单击“下一步”。

10. 在“数据仓库写帐户”页面上，在“用户帐户”和“密码”框中输入初始向数据库仓库分配写权限的用户的名称和密码。从“域”下拉列表中选择用户的域，然后单击“下一步”。

11. 在“数据读取器帐户”页面上，在“用户帐户”和“密码”框中输入 SQL Reporting Services 查询数据仓库时要使用的用户帐户的名称和密码。从“域”下拉列表中选择帐户域，然后单击“下一步”。

12. 在“操作数据报表”页面上，单击“下一步”。

13. 在“Microsoft 更新”页面上，单击“下一步”。

14. 在“准备安装程序”页面上，单击“安装”。

15. 在“正在完成 Operations Manager 报表组件安装向导”页面上，单击“完成”。

16. 在 System Center Operations Manager 2007 R2 安装程序中，单击“退出”。

安装了 System Center 报表后，您可以使用下面的过程重置与 SQL Server 报表关联的安全组名称。另外，只有在使用 SQL Server 时才需要此过程：

1.  单击“开始”，指向“管理工具”，然后单击“服务器管理器”。

2.  在“服务器管理器”中，展开“配置”，展开“本地用户和组”，然后单击“组”。

3.  找到下面的组，其中 atl-sc-001 表示您的计算机的名称，ARCHINST 表示存档和监控数据库的 SQL Server 实例：**SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**。

4.  右键单击该组，然后单击“重命名”。通过在组名称末尾正好 SQL Server 实例名称的前面添加“\_50”来重命名。例如：**SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST** 。

5.  关闭服务器管理器。

如果 System Center 操作控制台处于打开状态，您需要关闭该应用程序然后重启它；否则，此“报表”选项卡不会出现在操作控制台用户界面上。注意，第一次重启操作控制台后, 需要等几分钟后所有监控报表才会出现在“报表”选项卡上。

