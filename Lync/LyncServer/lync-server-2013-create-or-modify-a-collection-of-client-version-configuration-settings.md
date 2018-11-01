---
title: 创建或修改客户端版本配置设置的集合
TOCTitle: 创建或修改客户端版本配置设置的集合
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ898477(v=OCS.15)
ms:contentKeyID: 52061020
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改客户端版本配置设置的集合

 

_**上一次修改主题：** 2013-02-23_

客户端版本配置设置用于启用或禁用客户端版本控制。全局客户端版本配置随 Lync Server 一起安装，用于启用或禁用整个服务器部署的客户端版本控制。您还可以为单个网站配置客户端版本配置设置。可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改客户端版本配置设置。

> [!NOTE]  
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。



## 使用 Lync Server 控制面板创建或修改客户端版本配置设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本配置”导航按钮。

4.  在“客户端版本配置”页上，执行下列操作：
    
      - 若要创建新配置，请单击“新建”，选择网站，单击“确定”名称，然后更新设置。
    
      - 若要修改配置，请选择配置，单击“编辑”，单击“显示详细信息”，然后对设置进行更改。

## 使用 Windows PowerShell Cmdlet 创建或修改客户端版本配置设置

您可以使用 **New-CsClientVersionConfiguration** cmdlet 创建客户端版本配置设置，并使用 **Set-CsClientVersionConfiguration** cmdlet 修改它们。这些 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建新的客户端版本配置设置集合

  - 下面的命令创建应用于 Redmond 网站的新的客户端版本配置设置集合。在此示例中，为 Redmond 网站禁用了客户端版本控制。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

## 为网站启用客户端版本控制

  - 此命令为 Redmond 网站启用客户端版本控制。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## 在整个组织中禁用客户端版本控制

  - 在此示例中，为组织中使用的所有客户端版本配置设置禁用了客户端版本控制。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

有关详细信息，请参阅 [New-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionConfiguration) 和 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet 的帮助主题。

