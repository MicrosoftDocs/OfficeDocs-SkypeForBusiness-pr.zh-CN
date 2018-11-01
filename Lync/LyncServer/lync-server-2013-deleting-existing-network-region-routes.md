---
title: 删除现有网络区域路由
TOCTitle: 删除现有网络区域路由
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49888440
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有网络区域路由

 

_**上一次修改主题：** 2012-11-01_

呼叫允许控制 (CAC) 配置中的每个区域必须具有访问其他每个区域的方式。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。您可以使用 Lync Server 控制面板配置网络区域路由。在 Lync Server 控制面板中，可以创建、修改或删除网络区域路由。使用本主题可删除现有网络区域路由。有关创建或修改网络区域路由的详细信息，请参阅[创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

## 删除网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域路由”。

4.  在“区域路由”页上，单击要删除的区域路由。
    
    > [!NOTE]  
    > 可一次性删除多个区域路由。要执行此操作，请按住 Ctrl 键，同时选择多个区域路由。或者，要选择全部区域路由，请单击“编辑”菜单中的“全选”。
    


5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。

## 另请参阅

#### 任务

[创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### 概念

[配置网络区域路由](https://technet.microsoft.com/zh-cn/library/gg133706\(v=ocs.15\))  

#### 其他资源

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

