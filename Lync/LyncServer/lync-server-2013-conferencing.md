---
title: Lync Server 2013 会议
description: Lync Server 2013 会议。
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
ms.openlocfilehash: 7d4a5f1ca1edc6246aace56c8a4bfa5b5215c4bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555948"
---
# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-11_

借助 Lync Server 2013 中的统一会议，用户可以进行协作、共享信息，并实时协调其努力。 所有用户都可以使用广泛的自发协作、预定会议和会议工具。 可以从任何有 Internet 连接的位置使用语音和视频会议功能，不在计算机旁边的用户可以通过公用电话交换网 (PSTN ) 电话拨入来参加音频会议。

在 Outlook 中集成的会议工具使组织者能够通过一次单击安排会议或启动即席会议，同时使与会者更容易加入。 Web 客户端将丰富的会议功能扩展到未运行桌面版 Lync 的参与者。

<div>

## <a name="audio-and-video-conferencing"></a>音频和视频会议

Lync Server 提供了传统音频桥接服务用户熟悉的用户体验，其中包括带有触摸音呼叫控制命令的 PSTN 电话拨入式服务。 同时，还融合了仅由集成的统一通信平台提供的强大的安排、加入和管理功能。

通过一次单击，用户可以从 Outlook 安排会议。 详细信息，如会议时间、位置和与会者，请遵循熟悉的 Outlook 模板。 此外，还会自动填充特定于电话会议的信息，如拨入号码、会议 ID 和个人标识号 (PIN) 提醒。

为了帮助确保只有授权用户参与呼叫，Lync Server 为参与者提供了多个级别的身份验证。 通过使用 Lync 加入的用户已通过 Active Directory 域服务进行身份验证，无需输入 PIN、传递代码或会议 ID。

Lync 通过将视频集成到统一客户端来简化视频会议用户体验，以便通过视频或快速升级到视频来安排会议，并无缝轻松。

Lync Server 使您只需单击一次即可轻松地将视频添加到标准电话呼叫中。 当视频呼叫或会议中有多个参与者时，每个用户最多能同时观看来自五个其他用户的视频，或者演示者只能选择一个要被所有人以独占方式观看的视频源。

高清晰度视频 (分辨率 1270 x 720;纵横比 16:9) 和 VGA 视频 (分辨率 640 x 480;对于在高端计算机上运行 Lync 的用户之间的对等呼叫，支持纵横比 4:3) 。 单次对话中每个参与者所查看的分辨率可能有所不同，具体取决于每个用户的相应硬件的视频功能。

IT 管理员可以设置策略，限制或禁止在客户端上使用高清或 VGA 视频，具体取决于计算机功能、网络带宽以及可提供所需分辨率的摄像机的状态。通过带内设置实施这些策略。

</div>

<div>

## <a name="web-conferencing"></a>Web 会议

Lync Server 将会议共享功能（如桌面、应用程序、附件、白板、投票和 PowerPoint）集成到简化的 Lync 中。 通过与音频或视频会议结合使用，会话变得更加生动，协作更加顺畅。

为了改进演示或查看 PowerPoint 演示文稿的用户的整体体验，Lync Server 2013 使用 Office Web Apps 来处理 PowerPoint 演示文稿。 用户可以在 Lync 会议中使用白板共享图片或复制和粘贴文本。 演示者可以在 Lync 会议中进行轮询，以征求与会者的反馈意见。

桌面共享使演示者能够实时将任何视觉对象、应用程序、网页、文档、软件或桌面的一部分广播到远程参与者，从 Lync 直接广播。 观众成员可以通过鼠标移动和键盘输入予以跟进。 演示者可以选择共享整个屏幕或仅共享部分屏幕。 通过共享桌面，演示者可以从任何位置与其受众进行产品或软件互动演示。

应用程序共享使演示者可以共享其桌面上的软件的控制权，同时还可兼顾参与者的反馈或文本问题。演示者还可以将应用程序的控制权委派给会议参与者。

</div>

<div>

## <a name="dial-in-conferencing"></a>电话拨入式会议

对于没有使用个人计算机的用户，有几种方法可用于加入 Lync Server 会议呼叫。 PSTN 用户可以拨打访问号码，访问会议桥，然后输入会议 ID。 对于安全性更高的会议，还可以要求用户输入其 PIN 以针对 Active Directory 进行身份验证。 Lync Server 还支持 Lync Phone Edition 设备，这是由 Microsoft 合作伙伴提供的独立 IP 电话设备。

</div>

</div>

<span> </span>

</div>

</div>

</div>

