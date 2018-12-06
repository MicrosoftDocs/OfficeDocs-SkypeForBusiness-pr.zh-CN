---
title: 安装 Operation Manager 代理文件
TOCTitle: 安装 Operation Manager 代理文件
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205345(v=OCS.15)
ms:contentKeyID: 49314527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Operation Manager 代理文件

 

_**上一次修改主题：** 2012-10-20_

要在计算机上安装 Operations Manager 代理文件，请完成下列步骤。

1.  在 System Center 安装介质上，双击“SetupOM.exe”。

2.  在 System Center Operation Manager 安装中，单击“安装 Operations Manager 代理”。

3.  在 System Center 安装向导的“欢迎使用 System Center Operations Manager 安装”向导页上，单击“下一步”。

4.  在“目标文件夹”页面上，选择其中将安装 Operations Manager 代理文件的文件夹，然后单击“下一步”。

5.  在“管理组配置”页面上选择“指定管理组信息”。然后单击“下一步”。

6.  在“管理组配置”页面上的“管理组名称”框中键入 Operations Manager 管理组的名称，然后在“管理服务器”框中键入 Operations Manager 服务器（例如，atl-scom-001）的主机名。如果已更改由 Operations Manager 使用的端口号，则在管理服务器端口框中键入新端口号。否则，保留该端口为默认值 5723，并单击“下一步”。

7.  在“代理操作帐户”页面上，选择“本地系统”，然后单击“下一步”。

8.  在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”，然后单击“下一步”。

9.  在“安装准备就绪”页面上，单击“安装”。

10. 在“完成 System Center Operations Manager 安装向导”页面上，单击“完成”。

11. 单击“退出”。

如果正在使用 System Center 2007 R2，可验证已通过依次单击“开始”、“所有程序”、“System Center Operations Manager 2007 R2”和“Operations Manager Shell”创建了该代理。在 Operations Manager Shell 中，键入以下 Windows PowerShell command，然后按 Enter：

    Get-Agent 

一个所有 Operations Manager 代理的列表将出现在屏幕上。

如果正在使用 System Center 2012，请从 Operations 2012 Manager Shell 运行此命令：

    Get-SCOMAgent

