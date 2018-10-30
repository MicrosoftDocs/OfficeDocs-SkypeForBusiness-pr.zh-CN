---
title: 查看位置策略信息
TOCTitle: 查看位置策略信息
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520954(v=OCS.15)
ms:contentKeyID: 49312090
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看位置策略信息

 

_**上一次修改主题：** 2012-11-01_

在 Lync Server 2013 中，可以使用位置策略应用与增强型 9-1-1 (E9-1-1) 功能相关和与用户或联系人的位置设置相关的设置。位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，在美国为 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

您可以在 Lync Server 2013 控制面板中的“网络配置”组中配置位置策略。在 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。可使用以下过程查看位置策略的信息。有关创建或修改位置策略的详细信息，请参阅[创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

## 查看位置策略的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“位置策略”。

4.  在“位置策略”页上，选择要修改的位置策略。

5.  在“编辑”菜单上，单击“显示详细信息”。
    
    > [!NOTE]
    > 一次只能查看一个位置策略的信息。


默认情况下，存在一个名为“全局”的策略，无法将其删除或进行重命名。但是，您可以修改“全局”策略。该策略将应用于所有用户和联系人，除非您创建站点策略或每用户策略。每用户策略必须应用于特定用户。

## 另请参阅

#### 任务

[创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)  
[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)  

#### 其他资源

[New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsLocationPolicy)

