---
title: Lync Server 2013 中的公共区域电话
TOCTitle: Lync Server 2013 中的公共区域电话
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994076(v=OCS.15)
ms:contentKeyID: 52061138
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的公共区域电话

 

_**上一次修改主题：** 2016-12-08_

公用区域电话是不与个别用户关联的 IP 电话，通常不是位于某人的办公室，而是位于建筑物大厅、餐厅、员工休息室、会议室和其他可能有大量人员聚集的位置。与 Lync Server 中的其他电话不同（这些电话通常使用分配给个别用户的语音策略和拨号计划维护），不会为公用区域电话分配个别用户。这意味着必须以与其他电话不同的方式管理公用区域电话。

若要管理公用区域电话，请为所有可为其分配策略和语音计划的公用区域电话创建 Active Directory 域服务 联系对象，例如用户帐户。此方法使您能够保持对公用区域电话的控制，即使这些电话未与个别用户关联也是如此。

使用本节中的主题了解如何为公用区域电话创建联系对象，修改和删除这些对象，以及配置和查看有关您的部署中的公用区域电话的配置信息。

> [!NOTE]  
> 有三种公用区域电话可供您选择：Aastra 6721ip 公用区域电话、HP 4110 IP Phone 和 Polycom CX500 IP 公用区域电话。Polycom CX3000 IP 会议电话是另一种公用区域电话变体，但其专门用于会议室。有关公用区域电话的详细信息，请参阅<a href="http://technet.microsoft.com/zh-cn/library/gg398958(v=ocs.14).aspx">选择新设备</a>的“公用区域电话”一节。



## 本部分内容

  - [查看公共区域电话信息](lync-server-2013-view-common-area-phone-information.md)

  - [创建或修改公共区域电话联系对象](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [启用或禁用公用办公桌](lync-server-2013-enable-or-disable-hot-desking.md)

  - [删除公共区域电话联系对象](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [向公共区域电话分配策略](lync-server-2013-assign-policies-to-a-common-area-phone.md)

