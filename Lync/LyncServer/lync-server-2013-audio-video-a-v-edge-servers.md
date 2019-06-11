---
title: 'Lync Server 2013: 音频/视频 (A/V) 边缘服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013 中的音频/视频 (A/V) 边缘服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

A/V 边缘服务为内部用户 (登录到你的组织网络的用户) 提供一种方法, 以便与外部用户 (未登录到你的组织网络的用户) 共享音频和视频。 除了音频和视频, A/V 边缘服务还提供有关桌面共享和文件传输等方面的支持。

A/V 边缘服务主要通过使用 A/V 边缘配置进行管理;使用这些设置, 你可以管理每个端口和每个用户分配的最大带宽量, 并指定在必须续订该令牌之前可以使用身份验证令牌的时间长度。 A/V 边缘配置设置可应用于网站或单个 A/V 边缘服务器。 确定哪个设置集合优先时, 请使用以下指南:

  - 在服务作用域 (即在单个服务器上) 中配置的设置优先于所有内容。

  - 在网站范围内配置的设置优先于在全局范围内配置的设置。 但是, 服务范围设置还将取代网站范围的设置。

  - 只有在单个服务器上没有配置任何服务设置且该服务器所在的网站没有网站设置的情况下, 才会使用全局范围内的设置。

只有使用 Lync Server PowerShell 和 CsAVEdgeConfiguration cmdlet 才能管理 A/V 边缘服务。

<div>

## <a name="in-this-section"></a>本节内容

  - [返回 Lync Server 2013 中的 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

