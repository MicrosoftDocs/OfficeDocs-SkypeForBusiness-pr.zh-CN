---
title: 启用呼叫允许控制
TOCTitle: 启用呼叫允许控制
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520942(v=OCS.15)
ms:contentKeyID: 49311806
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用呼叫允许控制

 

_**上一次修改主题：** 2012-11-01_

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。配置 CAC 网络后，必须启用 CAC 以强制实施带宽限制。可以使用 Lync Server 控制面板执行此操作。

## 从 Lync Server 控制面板启用 CAC

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“全局”。

4.  在“全局”页上，单击“全局”配置。
    
    > [!NOTE]  
    > 只能为任何 Microsoft Lync Server 2013 部署配置一个网络，因此列表中最多只有一个网络配置。无法重命名“全局”配置。
    


5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑全局设置”页上，选中“启用呼叫允许控制”复选框，然后单击“提交”。

单击“提交”时，运行配置测试。此时将关闭“编辑全局设置”对话框，并返回到“全局”页。如果在网络配置中发现任何阻止其正常工作的错误或不一致问题（例如，如果每个区域未通过区域间路由连接到其他每个区域），则会收到警告。

如果更改网络配置，则可通过打开“全局”配置并单击“提交”再次运行验证检查。无需先禁用 CAC：保留此复选框的选中状态，并单击“提交”。在未对配置进行任何更改的情况下可随时执行此操作。

## 另请参阅

#### 概念

[Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)  

#### 其他资源

[在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

