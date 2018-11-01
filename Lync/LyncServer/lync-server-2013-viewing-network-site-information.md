---
title: 查看网络站点信息
TOCTitle: 查看网络站点信息
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49888346
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络站点信息

 

_**上一次修改主题：** 2013-02-23_

网络站点是指在呼叫允许控制服务 (CAC) 或增强型 9-1-1 部署的每个区域中配置的办公室或位置。可以在 Lync Server 2013 控制面板或 Lync Server 命令行管理程序 中查看网络站点信息。有关创建或修改网络站点的详细信息，请参阅[创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)。

## 在 Lync Server 控制面板中查看网络站点信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“站点”。

4.  在“站点”页上，单击要查看的站点。
    
    > [!NOTE]
    > 一次只能查看一个站点的信息。


5.  在“编辑”菜单上，单击“显示详细信息”。

## 使用 Lync Server 命令行管理程序 cmdlet 查看网络站点信息

可使用 Get-CsNetworkSite cmdlet 查看网络站点信息。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络站点信息

  - 若要查看有关您的所有网络站点的信息，请在 Lync Server 命令行管理程序中键入以下命令然后按 Enter：
    
        Get-CsNetworkSite
    
    将返回如下信息：
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

有关详细信息，请参阅 [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)  
[删除现有网络站点](lync-server-2013-deleting-an-existing-network-site.md)

