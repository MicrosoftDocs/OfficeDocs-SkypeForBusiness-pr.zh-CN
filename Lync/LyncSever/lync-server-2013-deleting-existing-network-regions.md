---
title: 删除现有的网络区域
TOCTitle: 删除现有的网络区域
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49888603
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有的网络区域

 

_**上一次修改主题：** 2013-02-21_

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。您可以使用 Lync Server 控制面板配置网络区域。网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。在 Lync Server 控制面板中，可以创建、修改或删除网络区域。使用此主题可删除现有网络区域。有关创建或修改现有网络区域的详细信息，请参阅[创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)

## 删除网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域”。

4.  在“区域”页上，单击要删除的区域。
    
    > [!NOTE]  
    > 可一次性删除多个区域。要执行此操作，请按住 Ctrl 键，同时选择多个区域。或者，要选择全部区域，请单击“编辑”菜单中的“全选”。
    


5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。
    
    > [!WARNING]
    > 如果网络区域与某个网络站点关联，则不能删除该网络区域。如果尝试删除与某个站点关联的区域，您将收到错误消息。要查看区域是否与任何站点关联，请选择相应的区域，然后单击“编辑”菜单中的“显示详细信息”。


## 另请参阅

#### 任务

[创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)

