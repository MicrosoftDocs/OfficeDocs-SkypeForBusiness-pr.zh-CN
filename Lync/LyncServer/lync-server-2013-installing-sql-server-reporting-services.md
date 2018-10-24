---
title: 安装 SQL Server Reporting Services
TOCTitle: 安装 SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204957(v=OCS.15)
ms:contentKeyID: 49313048
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 SQL Server Reporting Services

 

_**上一次修改主题：** 2012-06-20_

如果您打算使用 Microsoft Lync Server 2013 监控报告（有关详细信息，请参阅本文档的下一节），您必须先安装 SQL Server Reporting Services；可在安装 Microsoft SQL Server 时或安装 SQL Server 后随时安装 Reporting Services。如果您未安装 SQL Server，则请按照本文档之前提供的说明操作。安装 SQL Server 时，确保在“功能选择”页上选择 Reporting Services。这将安装 SQL Server Reporting Services。

如果您已安装 SQL Server 但未安装 SQL Server Reporting Services，则可根据需要按照 SQL Server 2008 R2 或 SQL Server 2012 中的相应说明集添加此功能。

若要验证 reporting Services 安装是否成功，请完成下列步骤：

1.  如果您运行的是 Microsoft SQL Server 2008 R2，则依次单击“开始”、“所有程序”、“Microsoft SQL Server 2008 R2”、“配置工具”和“Reporting Services 配置管理器”。
    
    如果您运行的是 Microsoft SQL Server 2012，则依次单击“开始”、“所有程序”、“Microsoft SQL Server 2012”、“配置工具”和“Reporting Services 配置管理器”。

2.  在“Reporting Services 配置连接”对话框中，验证服务器的名称是否显示在“服务器名称”框中以及存储监控数据的 SQL Server 实例的名称是否显示在“报表服务器实例”框中。单击“连接”。

在 Reporting Service 配置管理器中，报表服务器的“状态”窗格应显示已安装 SQL Server Reporting Services 并且当前正在运行 Reporting Services：报表服务器的状态应显示为“已启动”，并且“开始”按钮应处于灰显状态并且不可用。如果 Reporting Service 未在运行，则单击“开始”以启动此服务。

如果报表服务器数据库名称标签旁未列出任何数据库，则执行下列操作：

1.  在 Reporting Services 配置管理器中，单击“数据库”。

2.  在“报表服务器数据库”窗格中，单击“更改数据库”。

3.  在“报表服务器数据库配置”向导的“操作”窗格中，选择“创建新的报表服务器数据库”，然后单击“下一步”。

4.  在“报表服务器数据库配置”向导的“数据库服务器”窗格中，验证“服务器名称”、“身份验证类型”和“用户名”中列出的信息是否正确。单击“测试连接”以验证是否能连接到数据库服务器，然后单击“下一步”。

5.  在“报表服务器数据库配置”向导的“数据库”窗格中，接受“数据库名称”、“语言”和“报表服务器模式”的默认值，然后单击“下一步”。

6.  在“报表服务器数据库配置”向导的“凭据”窗格中，验证“身份验证类型”下拉列表和“用户名”框以及“密码”框中是否列出了正确的信息，然后单击“下一步”。

7.  在“报表服务器数据库配置”向导的“摘要”窗格中，单击“下一步”。

8.  在“报表服务器数据库配置”向导的“进度和完成”窗格中，单击“完成”。

若要验证是否配置了 Reporting Service URL，请单击“Web 服务 URL”。您应在标题“报表服务器 Web 服务 URL”下看到列出了一个或多个 URL。单击其中每个 URL 以验证您是否能够访问本地安装的 SQL Server Reporting Services 的主页。

