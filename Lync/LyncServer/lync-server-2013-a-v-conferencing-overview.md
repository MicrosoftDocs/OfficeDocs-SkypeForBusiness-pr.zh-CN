---
title: Lync Server 2013 A/V 会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d77d39cfa1483db9251d038f876f8e91428ae23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 A/V 会议概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-13_

A/V 会议在您的用户之间实现实时音频和视频通信。 在部署会议时，可以选择同时启用并使用 Web 会议和 A/V 会议，也可以仅启用并使用 Web 会议。

要规划 A/V 会议，需了解组织所需会议媒体类型要求的网络带宽。 这可能包括音频、视频和全景视频。

在为用户启用 A/V 会议之前，请确保您的网络能够处理生成的负载。 如果没有足够的网络带宽，用户体验可能会受到严重降低。 可以使用呼叫允许控制（CAC）管理由 A/V 会议使用的网络带宽。 对于受限制的网络（例如中央网站和分支网站之间的有限带宽链接），这一点非常重要。 有关详细信息，请参阅[Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)。 有关媒体带宽要求的详细信息，请参阅[Lync Server 2013 中媒体流量的网络带宽要求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。

如果在网络中部署音频会议，用户将需要音频设备（如耳机）参加音频会议。 如果您部署视频会议，则需要部署视频设备，例如用户的网络摄像机。 我们建议您使用 Microsoft 针对所有设备类型认证的统一通信（UC）设备，以确保获得最佳用户体验。 有关 UC 认证设备的详细信息，请参阅位于[https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)的 "电话和设备（Lync）"。 对于音频或视频设备、设备部署和用户培训是考虑和规划的重要步骤之一。

以下各节介绍了音频和视频会议的功能，其中包括有关管理带宽和选择相应客户端的信息。

<div>

## <a name="audio-conferencing-features"></a>音频会议功能

Lync Server 2013 提供了几个可用于为用户配置音频会议体验的功能，其中包括以下内容：

  - **访问群体静音**   演示者可以使用此设置将会议中的所有音频参与者静音，并将会议置于非演示者无法自行取消静音的状态中。

  - **会议进入/退出通知**   如果您已启用电话拨入式会议，演示者可以使用此设置打开或关闭 "进入和退出通知"，以在会议进行过程中最大限度地减少打扰。

  - **通过拨出**   演示者和已授予权限的与会者添加用户，可以向会议中添加 PSTN 号码，并让会议拨出到这些号码。

</div>

<div>

## <a name="video-conferencing-features"></a>视频会议功能

Lync Server 2013 提供了几个可用于为用户配置视频会议体验的功能，其中包括以下内容：

  - ****   包含两人以上的视频会议中的库视图，用户可自动查看会议中的所有人。 如果会议具有五个以上的参与者，则最活跃的参与者的视频显示在顶部行中，并且只有照片显示给其他参与者。 默认情况下，多方视频处于打开状态。 有关配置或关闭多方视频的详细信息，请参阅[在 Lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。

  - **全景视频**   如果在会议室中安装了圆桌会议视频会议设备，此功能将提供会议室的完整360度视图。 全景视频条仅适用于圆桌会议设备。

  - **演示者仅视频模式**   演示者可以对会议进行配置，以便仅显示演示者的视频。 当多个视频流可用且锁定到不同的源时，这将阻止大型会议中的打扰。 此模式还适用于由圆桌会议设备捕获和提供的视频。

  - **Hd 视频**   用户可在两方呼叫和多方会议中体验高达 HD 1080p 的分辨率。

  - **视频聚焦**   演示者可以对会议进行配置，以便会议中的其他参与者只能看到来自所选参与者的视频源中的视频。 此模式还适用于由圆桌会议设备为全景视频捕获和提供的视频。

</div>

</div>

<span> </span>

</div>

</div>

</div>

