---
title: 删除网络带宽策略配置文件
TOCTitle: 删除网络带宽策略配置文件
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49888412
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除网络带宽策略配置文件

 

_**上一次修改主题：** 2012-11-01_

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。在 Microsoft Lync Server 2013 中，只能为音频和视频形式指定带宽限制。您可以设置总体带宽限制和会话限制。可以使用 Lync Server 控制面板创建、修改或删除这些策略的容器配置文件。请使用下列过程删除网络带宽策略配置文件。有关创建或修改网络带宽策略配置文件的详细信息，请参阅[创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

## 删除带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。

4.  在“带宽策略”页上，单击要删除的带宽策略配置文件。
    
    > [!NOTE]  
    > 可一次性删除多个配置文件。要执行此操作，请按住 Ctrl 键，同时选择多个配置文件。或者，要选择全部配置文件，请单击“编辑”菜单中的“全选”。
    


5.  在“编辑”菜单上，单击“删除”。
    
    > [!WARNING]
    > 不能删除与网络站点关联的带宽策略配置文件。只有先删除配置文件与网络站点之间的关联，然后才能将配置文件删除。有关如何修改网络站点的详细信息，请参阅<a href="lync-server-2013-creating-or-modifying-network-sites.md">创建或修改网络站点</a>。


## 另请参阅

#### 任务

[创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[查看网络带宽策略配置文件信息](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  

#### 其他资源

[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

