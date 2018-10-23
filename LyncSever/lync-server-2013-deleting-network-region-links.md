---
title: 删除网络区域链接
TOCTitle: 删除网络区域链接
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49888489
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除网络区域链接

 

_**上一次修改主题：** 2012-11-01_

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。网络内的区域通过物理广域网 (WAN) 连接进行链接。您可以使用 Lync Server 控制面板删除两个网络区域之间的现有链接。有关创建或修改网络区域链接的详细信息，请参阅[配置网络区域链接](lync-server-2013-configuring-network-region-links.md)

## 删除网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域链接”。

4.  在“区域链接”页上，单击要删除的区域链接。
    
    > [!NOTE]  
    > 可一次性删除多个区域链接。要执行此操作，请按住 Ctrl 键，同时选择多个区域链接。或者，要选择全部区域链接，请单击“编辑”菜单中的“全选”。
    


5.  从“编辑”菜单中选择“删除”。

6.  单击“确定”。

## 另请参阅

#### 任务

[配置网络区域链接](lync-server-2013-configuring-network-region-links.md)

