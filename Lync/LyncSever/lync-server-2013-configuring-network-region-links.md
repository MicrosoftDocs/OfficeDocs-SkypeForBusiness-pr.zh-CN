---
title: 配置网络区域链接
TOCTitle: 配置网络区域链接
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182551(v=OCS.15)
ms:contentKeyID: 49313631
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置网络区域链接

 

_**上一次修改主题：** 2012-11-01_

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。网络内的区域通过物理广域网 (WAN) 连接进行链接。可以使用 Lync Server 控制面板在两个网络区域之间定义链接，并设置这些区域之间音频和视频连接的带宽限制。有关删除现有网络区域链接的详细信息，请参阅[删除网络区域链接](lync-server-2013-deleting-network-region-links.md)。

## 创建网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域链接”。

4.  在“区域链接”页上，单击“新建”。

5.  在“新建区域链接”的“名称”字段中键入值。
    
    > [!NOTE]  
    > 该值必须在 Lync Server 2013 部署中是唯一的。
    


6.  从“网络区域 \#1”下拉列表中，选择要链接的两个区域之一。

7.  从“网络区域 \#2”下拉列表中，选择要链接的另一个区域。此区域必须不同于为“网络区域 \#1”所选的区域。

8.  （可选）如果要对这些区域之间的音频或视频呼叫设置带宽限制，请从“带宽策略”下拉列表中选择带宽策略配置文件。

9.  单击“提交”。

## 修改网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“区域链接”。

4.  在“区域链接”页上，单击要修改的区域链接。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑区域链接”中，可以修改已链接的区域或该链接的带宽策略配置文件。

7.  单击“提交”。

## 另请参阅

#### 任务

[删除网络区域链接](lync-server-2013-deleting-network-region-links.md)  

#### 其他资源

[New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

