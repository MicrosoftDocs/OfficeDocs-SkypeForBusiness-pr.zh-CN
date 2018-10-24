---
title: 查看网络范围路由信息
TOCTitle: 查看网络范围路由信息
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49888375
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看网络范围路由信息

 

_**上一次修改主题：** 2013-02-23_

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。使用以下过程可在 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中查看现有网络区域路由。有关创建或修改网络区域路由的详细信息，请参阅[创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

## 在 Lync Server 控制面板中查看网络区域路由信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域路由”。

4.  在“区域路由”页上，单击要查看的区域路由。
    
    > [!NOTE]
    > 您一次只能查看一个区域路由。


5.  在“编辑”菜单上，单击“显示详细信息”。

## 使用 Lync Server PowerShell Cmdlet 查看网络区域路由信息

还可以使用 Lync Server PowerShell 和 Get-CsNetworkInterRegionRoute cmdlet 查看网络区域路由信息。此 cmdlet 可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看网络区域路由信息

  - 若要查看有关您的所有网络区域路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsNetworkInterRegionRoute
    
    将返回如下信息：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

有关详细信息，请参阅 [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)

