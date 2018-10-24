---
title: Lync Server 2013 中的音频/视频 (A/V) 边缘服务器
TOCTitle: Lync Server 2013 中的音频/视频 (A/V) 边缘服务器
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49888566
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的音频/视频 (A/V) 边缘服务器

 

_**上一次修改主题：** 2012-11-01_

A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。除了音频和视频以外，A/V 边缘服务还提供对诸如桌面共享和文件传输等内容的支持。

A/V 边缘服务主要通过使用 A/V 边缘配置进行管理；通过这些设置，您可以管理针对每个端口和每个用户要分配的最大带宽量，并指定在必须续订身份验证令牌之前可以使用该令牌的时间长度。A/V 边缘配置设置可以应用到站点或个别 A/V 边缘服务器。在确定哪个设置集合将取得优先权时，请使用以下指南：

  - 在服务范围（也就是，在个别服务器上）配置的设置的优先于一切。

  - 在站点范围配置的设置的优先于在全局范围配置的设置。然而，服务范围设置还将取代站点范围设置。

  - 只有未在个别服务器上配置任何服务设置，并且在服务器所在的站点没有站点设置时，才会使用全局范围的设置。

A/V 边缘服务只能通过使用 Lync Server PowerShell 和 CsAVEdgeConfiguration cmdlet 进行管理。

## 本部分内容

  - [返回 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

