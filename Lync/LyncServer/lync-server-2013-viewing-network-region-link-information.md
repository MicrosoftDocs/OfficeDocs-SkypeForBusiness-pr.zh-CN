---
title: 查看网络区域链接信息
TOCTitle: 查看网络区域链接信息
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49888475
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络区域链接信息

 

_**上一次修改主题：** 2013-02-23_

您可以查看两个网络区域之间作为呼叫允许控制 (CAC) 的一部分的链接。网络内的区域通过物理广域网 (WAN) 连接进行链接。您可以使用 Lync Server 控制面板查看两个网络区域之间的现有链接。有关创建或修改网络区域链接的详细信息，请参阅[配置网络区域链接](lync-server-2013-configuring-network-region-links.md)。

## 在 Lync Server 控制面板中查看网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域链接”。

4.  在“区域链接”页上，单击要查看的区域链接。
    
    > [!NOTE]
    > 您一次只能查看一个区域链接的相关信息。


5.  从“编辑”菜单中选择“显示详细信息”。

## 使用 Lync Server 命令行管理程序 Cmdlet 查看网络区域链接信息

还可以使用 Lync Server 命令行管理程序和 **Get-CsNetworkRegionLink** cmdlet 查看网络区域链接。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsNetworkRegionLink
    
    此命令返回与以下内容类似的信息：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

有关详细信息，请参阅[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)。

## 另请参阅

#### 任务

[配置网络站点链接](lync-server-2013-configuring-network-site-links.md)

