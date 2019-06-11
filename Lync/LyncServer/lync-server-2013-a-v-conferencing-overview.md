---
title: Lync Server 2013 A/V 会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 A/V 会议概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-13_

A/V 会议支持用户之间的实时音频和视频通信。 部署会议时, 可以选择启用和使用 web 会议和 A/V 会议, 或者仅启用网络会议。

要规划 A/V 会议，需了解组织所需会议媒体类型要求的网络带宽。 这包含音频、视频和全景视频。

在为用户启用 A/V 会议之前, 请确保你的网络可以处理所产生的负载。 如果网络带宽不足，用户体验可能大打折扣。 可以使用呼叫许可控制 (CAC) 管理由 A/V 会议使用的网络带宽。 这对受限网络（例如中央站点和分支站点之间的受限带宽链接）很重要。 有关详细信息, 请参阅[Lync Server 2013 中的呼叫许可控制概述](lync-server-2013-overview-of-call-admission-control.md)。 有关媒体带宽要求的详细信息, 请参阅[Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。

如果在网络中部署音频会议，用户需要耳机等音频设备来参加音频会议。 如果部署视频会议，需要为用户部署视频设备，如网络摄像头。 我们建议你使用由 Microsoft 为所有设备类型认证的统一通信 (UC) 设备, 以确保最佳的用户体验。 有关 UC 认证的设备的详细信息, 请参阅 "Lync 的电话和设备[http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)"。 对于音频或视频设备、设备部署和用户培训是考虑和规划的重要步骤。

以下部分介绍音频和视频会议的功能, 包括有关管理带宽和选择相应客户端的信息。

<div>

## <a name="audio-conferencing-features"></a>音频会议功能

Lync Server 2013 提供了多个可用于为用户配置音频会议体验的功能, 包括以下内容:

  - **观众静音**   演示者可以使用此设置将会议中的所有音频参与者设为静音, 并将会议置于非演示者无法取消静音的状态。

  - **会议进入/退出通知**   如果已启用电话拨入式会议, 演示者可以使用此设置打开或关闭通知, 以便在会议正在进行时最大限度地减少干扰。

  - **通过拨出**   演示者和已授予权限的与会者添加用户, 可以向会议添加 PSTN 号码, 并让会议拨出到这些号码。

</div>

<div>

## <a name="video-conferencing-features"></a>视频会议功能

Lync Server 2013 提供了多个可用于为用户配置视频会议体验的功能, 包括以下内容:

  - **** 在包含两人以上的视频会议中, 用户可自动查看会议中的每个人。    如果与会者超过五名，那么最活跃与会者的视频将显示在最上面一行，并仅对其他与会者显示照片。 默认情况下，已启用多方视频。 有关配置或关闭多方视频的详细信息, 请参阅[在 Lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。

  - **全景视频**   如果在会议室中安装了圆桌会议视频会议设备, 此功能将提供会议室的完整360度视图。 全景视频带只能用于 RoundTable 设备。

  - **演示者仅视频模式**   演示者可以配置会议, 以便仅显示演示者的视频。 如果提供了多个视频流并锁定到不同的源，这可阻止大型会议受到干扰。 此模式还适用于由 RoundTable 设备捕获和提供的视频。

  - **Hd 视频**   用户可以在两方呼叫和多方会议中体验高达 HD 1080p 的分辨率。

  - **视频聚焦**   演示者可以配置会议, 以便会议中的其他参与者只能看到来自所选参与者的视频。 此模式还适用于由 RoundTable 设备针对全景视频捕获和提供的视频。

</div>

</div>

<span> </span>

</div>

</div>

</div>

