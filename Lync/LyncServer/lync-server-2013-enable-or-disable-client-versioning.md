---
title: 启用或禁用客户端版本控制
TOCTitle: 启用或禁用客户端版本控制
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ898475(v=OCS.15)
ms:contentKeyID: 52060986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用客户端版本控制

 

_**上一次修改主题：** 2013-02-23_

客户端版本配置设置用于全局或针对特定站点打开或关闭客户端版本控制。全局客户端版本配置随 Lync Server 2013 一起安装，用于启用或禁用整个服务器部署的客户端版本控制。在启用全局配置时，您的所有现有客户端版本策略将在用户尝试登录时生效。如果不希望进行任何客户端版本控制，则可以禁用全局客户端版本配置。您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中启用或禁用客户端版本控制。

> [!NOTE]  
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。



## 使用 Lync Server 控制面板启用或禁用客户端版本控制

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本配置”导航按钮。

4.  执行以下操作：
    
      - 若要全局启用或禁用客户端版本控制，请双击“全局”配置，然后修改设置。
    
      - 若要启用或禁用特定站点的客户端版本控制，请单击“新建”，选择该站点，单击“确定”，然后修改该站点的设置。

## 使用 Windows PowerShell Cmdlet 启用或禁用客户端版本控制

您可以使用 **Set-CsClientVersionConfiguration** cmdlet 启用或禁用客户端版本控制。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用客户端版本控制

  - 您可以通过将 **Enabled** 属性设置为 True ($True) 来启用客户端版本控制。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## 禁用客户端版本控制

  - 您可以通过将 **Enabled** 属性设置为 False ($False) 来禁用客户端版本控制。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

有关详细信息，请参阅 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet 的帮助主题。

