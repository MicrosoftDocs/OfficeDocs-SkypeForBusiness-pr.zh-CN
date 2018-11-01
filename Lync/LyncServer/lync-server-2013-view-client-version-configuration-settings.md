---
title: 查看客户端版本配置设置
TOCTitle: 查看客户端版本配置设置
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ923062(v=OCS.15)
ms:contentKeyID: 52061117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看客户端版本配置设置

 

_**上一次修改主题：** 2013-02-23_

客户端版本配置设置用于启用或禁用客户端版本控制。全局客户端版本配置随 Lync Server 2013 一起安装，可用于对整个服务器部署实施或取消客户端版本控制。在启用全局配置时，您的所有现有客户端版本策略将在用户尝试登录时生效。您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序查看客户端版本配置设置。

> [!NOTE]  
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。


## 使用 Lync Server 控制面板查看客户端版本配置设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本配置”导航按钮。

4.  双击要查看的客户端版本配置的名称。

## 使用 Windows PowerShell Cmdlet 查看客户端版本配置设置

您可以使用 **Get-CsClientVersionConfiguration** cmdlet 查看客户端版本配置设置。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看客户端版本配置信息

  - 若要查看有关您的所有客户端版本配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsClientVersionConfiguration
    
    将返回如下信息：
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

有关详细信息，请参阅 [Get-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet 的帮助主题。

