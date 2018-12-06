---
title: 创建或修改带宽策略配置文件
TOCTitle: 创建或修改带宽策略配置文件
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520945(v=OCS.15)
ms:contentKeyID: 49311919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改带宽策略配置文件

 

_**上一次修改主题：** 2012-10-15_

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。在 Microsoft Lync Server 2013 中，只能为音频和视频形式指定带宽限制。您可以设置总体带宽限制和会话限制。可以使用 Lync Server 控制面板创建、修改或删除这些策略的容器配置文件。每个带宽策略配置文件都可以与一个或多个网络站点相关联。可使用以下过程创建或修改带宽策略配置文件。若要删除带宽策略配置文件，请参阅[删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

## 创建新的带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。

4.  在“带宽策略”页上，单击“新建”。

5.  在“新建带宽策略配置文件”的“名称”字段中键入名称。此名称必须在所有带宽策略配置文件中是唯一的。

6.  在“音频限制”字段中，键入一个数值。此值是要为所有音频连接分配的最大带宽量，以 kbps 为单位表示。

7.  在“音频会话限制”字段中输入一个数值。此值是要为单个音频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 40 或更大。

8.  在“视频限制”字段中输入一个数值。此值是要为所有视频连接分配的最大带宽量，以 kbps 为单位表示。

9.  在“视频会话限制”字段中输入一个数值。此值是要为单个视频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 100 或更大。

10. （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该带宽策略配置文件的信息。

11. 单击“提交”。
    
    > [!NOTE]  
    > 创建新的带宽策略配置文件不会自动强制实施带宽限制。必须先将策略配置文件与站点相关联。有关如何将策略配置文件与站点相关联的详细信息，请参阅<a href="lync-server-2013-creating-or-modifying-network-sites.md">创建或修改网络站点</a>。
    


## 修改带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。

4.  在“带宽策略”页上，单击要修改的带宽策略配置文件。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑带宽策略配置文件”页上，根据需要修改字段（有关详细信息，请参阅本主题前面的“创建带宽策略配置文件”一节）。

7.  单击“提交”。
    
    > [!NOTE]  
    > 修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。
    


## 另请参阅

#### 任务

[删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### 其他资源

[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

