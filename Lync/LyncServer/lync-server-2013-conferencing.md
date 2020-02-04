---
title: Lync Server 2013 会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-11_

利用 Lync Server 2013 中的统一会议，用户可以进行协作、共享信息和实时协调工作。 所有用户都可以使用完全广泛的自发协作、计划会议和会议工具。 语音和视频会议功能可通过 Internet 连接在任何位置使用，并且离开计算机的用户可以通过使用公共交换电话网络（PSTN）电话拨入来参与音频会议。

Outlook 中集成的会议工具使组织者可以通过一次单击来安排会议或开始即席会议，还可以使与会者轻松加入会议。 Web 客户端将丰富的会议功能扩展到未运行桌面版本 Lync 的参与者。

<div>

## <a name="audio-and-video-conferencing"></a>音频和视频会议

Lync 服务器提供了传统音频桥服务用户所熟悉的用户体验，其中包括带有按键式呼叫控制命令的 PSTN 拨入式服务。 同时，它会将功能强大的计划、加入和管理功能合并到一个集成的统一通信平台。

只是单击一次，用户就可以从 Outlook 安排会议。 详细信息（如会议时间、位置和与会者）请按照熟悉的 Outlook 模板操作。 此外，将自动填充特定于会议呼叫的信息，如拨入号码、会议 Id 和个人识别码（PIN）提醒。

为了帮助确保只有授权用户参与呼叫，Lync 服务器为参与者提供了多个级别的身份验证。 使用 Lync 加入的用户已通过 Active Directory 域服务进行身份验证，并且无需输入 PIN、传递代码或会议 ID。

Lync 通过将视频合并到统一的客户端来简化视频会议用户体验，以便使用视频安排会议或流畅地升级到视频。

Lync Server 使您只需单击一次即可轻松地将视频添加到标准电话呼叫。 当视频通话或会议中有多个参与者时，每个用户可以同时查看多达五个其他用户的视频，或者演示者只能选择一个视频源供每个人独占查看。

高清晰度视频（分辨率 1270 x 720; 纵横比16:9）和 VGA 视频（分辨率 640 x 480; 纵横比4:3）支持在高端计算机上运行 Lync 的用户之间进行对等呼叫。 由单个对话中的每个参与者查看的分辨率可能会有所不同，具体取决于每个用户各自硬件的视频功能。

IT 管理员可以设置策略来限制或禁用客户端上的高清视频，具体取决于计算机功能、网络带宽以及相机是否能够提供所需的解决方案。 这些策略通过带内配置强制实施。

</div>

<div>

## <a name="web-conferencing"></a>Web 会议

Lync Server 将会议共享功能（如桌面、应用程序、附件、白板、投票和 PowerPoint）集成到简化的 Lync 中。 与音频或视频会议结合使用时，结果是一种非常方便、便于协作的会议。

为了改善演示或查看 PowerPoint 演示文稿的用户的整体体验，Lync Server 2013 使用 Office Web Apps 处理 PowerPoint 演示文稿。 用户可以在 Lync 会议中使用白板共享图片或复制和粘贴文本。 演示者可以在 Lync 会议中进行投票，征求与会者的反馈意见。

桌面共享使演示者能够在 Lync 中实时向远程参与者广播任何视觉对象、应用程序、网页、文档、软件或部分桌面。 受众成员可与鼠标移动和键盘输入一起关注。 演示者可以选择共享整个屏幕或仅共享部分。 通过共享其桌面，演示者可以从任何位置与交互式产品或软件演示中的受众进行沟通。

应用程序共享使演示者能够在其桌面上共享软件的控制，而不会失去参与者反馈或文本问题。 演示者还可以将应用程序的控制权委派给会议参与者。

</div>

<div>

## <a name="dial-in-conferencing"></a>电话拨入式会议

对于没有使用个人计算机的用户，有几种方法可用于加入 Lync Server 会议呼叫。 PSTN 用户可以拨打接入号码，访问 "会议桥"，然后输入会议 ID。 对于更安全的会议，还可能需要用户输入其 PIN 才能对 Active Directory 进行身份验证。 Lync 服务器还支持 Lync Phone Edition 设备，这些设备是由 Microsoft 合作伙伴提供的独立的 IP 电话设备。

</div>

</div>

<span> </span>

</div>

</div>

</div>

