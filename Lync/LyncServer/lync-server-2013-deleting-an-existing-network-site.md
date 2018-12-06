---
title: 删除现有网络站点
TOCTitle: 删除现有网络站点
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49888338
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有网络站点

 

_**上一次修改主题：** 2012-11-01_

网络站点是指在呼叫允许控制服务 (CAC) 或增强型 9-1-1 部署的每个区域中配置的办公室或位置。您可以使用 Lync Server 2013 控制面板配置站点并将其与区域相关联。例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 等网络站点相关联。必须为组织中的每个站点创建 CAC 网络站点，即使该站点没有带宽限制也应如此。从 Lync Server 控制面板中，可以创建、修改和删除网络站点。使用以下过程可删除现有网络站点。有关创建或修改网络站点的详细信息，请参阅[创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)

## 删除网络站点

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“站点”。

4.  在“站点”页上，单击要删除的站点。
    
    > [!NOTE]  
    > 可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”菜单中的“全选”。
    


5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。
    
    > [!WARNING]
    > 不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”菜单中的“显示详细信息”。

