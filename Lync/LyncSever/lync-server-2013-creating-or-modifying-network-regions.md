---
title: 创建或修改网络区域
TOCTitle: 创建或修改网络区域
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182579(v=OCS.15)
ms:contentKeyID: 49314083
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改网络区域

 

_**上一次修改主题：** 2012-11-01_

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。您可以使用 Lync Server 控制面板配置网络区域。网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。在 Lync Server 控制面板中，可以创建、修改或删除网络区域。请使用本主题创建并修改网络区域。有关删除现有网络区域的详细信息，请参阅[删除现有的网络区域](lync-server-2013-deleting-existing-network-regions.md)。

## 创建网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域”。

4.  在“区域”页上，单击“新建”。

5.  在“新建区域”页的“名称”字段中键入值。该值必须在 Microsoft Lync Server 2013 部署中是唯一的。

6.  在“中央站点”下拉列表中，选择此网络区域的中央站点。

7.  “启用音频备用路径”复选框默认情况下处于选中状态。此字段确定音频呼叫是否在主要路径带宽不足时通过备用路径路由。只有在需要关闭对 Internet 的卸载时才能清除此复选框。如果您有任何呼叫是 Internet 呼叫，那么不管带宽设置如何，您都必须选中该复选框。

8.  “启用视频备用路径”复选框默认情况下处于选中状态。此字段确定视频呼叫是否在主要路径带宽不足时通过备用路径路由。只有在需要关闭对 Internet 的卸载时才能清除此复选框。如果您有任何呼叫是 Internet 呼叫，那么不管带宽设置如何，您都必须选中该复选框。

9.  （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该区域的信息。

10. 单击“提交”。

创建网络区域时不使用“关联站点”表。创建或修改站点时，会将站点与区域相关联。有关详细信息，请参阅[创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)。

## 修改网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域”。

4.  在“区域”页上，单击要修改的区域。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑区域”页上，可以修改启用和禁用音频和视频备用路径的设置，并更改说明（有关详细信息，请参阅本主题前面的“创建网络区域”一节）。

7.  单击“提交”。

不能修改此页面中的“关联站点”。关联站点列表仅供参考，以便让您注意修改区域设置时将影响的站点。

## 另请参阅

#### 任务

[删除现有的网络区域](lync-server-2013-deleting-existing-network-regions.md)  
[为 CAC 配置网络区域](lync-server-2013-configure-network-regions-for-cac.md)  

#### 其他资源

[New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

