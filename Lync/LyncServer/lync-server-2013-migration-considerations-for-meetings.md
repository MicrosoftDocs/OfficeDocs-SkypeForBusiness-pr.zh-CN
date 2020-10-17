---
title: Lync Server 2013：会议的迁移注意事项
description: Lync Server 2013：会议的迁移注意事项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560938"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的会议的迁移注意事项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-10_

本节讨论下列主题：

  - 在 Microsoft Lync Server 2013 中对会议所做的更改

  - 根据会议需要迁移用户

  - 迁移现有会议和会议内容

  - Lync Server 2010 迁移期间的用户体验

  - Office 通信服务器 2007 R2 迁移期间的用户体验

  - Microsoft Lync 2013 与早期版本的服务器上的会议兼容性

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>对 Lync Server 2013 中的会议所做的更改

**Lync Server 2013 功能。**    Lync Server 2013 提供新的会议功能，这些功能在其帐户移动到 Lync Server 2013 并使用 Lync 2013 客户端登录后可供用户使用。 [Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

**会议 URL。**    与在 Lync Server 2010 中一样，Lync Server 2013 中的所有新安排的会议都具有 URL 前缀 https://和现有会议与用户帐户一起迁移。 但是，Lync Server 2013 不支持 Office 通信服务器 2007 R2 会议呼叫 (conf://URL 前缀) 或 web 会议 (meet://URL 前缀) 。 有关详细信息，请参阅本主题后面部分中的 "从 Office 通信服务器 2007 R2 迁移会议"。

**客户端支持。**    与 Lync Server 2010 不同，Lync Server 2013 不支持用于会议的 Office Communicator 客户端。 您不能使用以下客户端加入通过 Lync 2013 的联机会议外接程序安排的会议：

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

在迁移过程中，Office Communicator 2007 R2 用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议，直到他们的客户端升级。 请注意，Office Communicator 2007 R2 用户可以继续对 Lync Server 2013 使用其现有客户端，了解状态和 IM 功能，但不支持会议功能。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>根据会议需要迁移用户

**会议组织者频繁。**    请考虑在该过程的早期阶段迁移频繁的会议组织者，以便他们能够利用[lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述的新 Lync server 2013 和 lync 2013 功能，以及[lync server 2013 中的客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

**Live Meeting 用户。**    如果要从 Office 通信服务器 2007 R2 进行迁移，并且您的用户需要特定于 Live Meeting 的 web 会议功能，尤其是对大型会议和出在会议室的支持，您可以选择以下选项：

  - 建议组织者使用 Live Meeting 服务（如果在组织中可用）。

  - 让组织者驻留在 Office 通信服务器的早期版本上，以便他们可以继续安排基于服务器的 Live Meeting web 会议。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>从 Lync Server 2010 迁移会议

将用户从 Lync Server 2010 移动到 Lync Server 2013 时，以下信息将随用户帐户一起移动：

  - 先前由用户安排的会议。 这包括会议目录和会议数据。

  - 用户的个人标识号 (PIN)。 用户的当前 PIN 在到期或用户请求新 PIN 之前仍然有效。

但是，以下用户帐户信息不会移动到新服务器：

  - 会议内容，例如 PowerPoint 演示文稿、白板内容和轮询数据

若要移动会议中已共享的内容，请使用 Move-CsUser cmdlet 的 MoveMeetingContent 参数。 有关使用此 cmdlet 的详细信息，请参阅 Lync Server 2013 cmdlet 文档中的 [get-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>从 Office 通信服务器 2007 R2 迁移会议

Office 通信服务器 2007 R2 会议可以是会议呼叫 (conf://URL 前缀) 或 web 会议 (meet://URL 前缀) 。 Lync Server 2013 不支持这些早期的 conf://和 meet://会议，它们不会与用户帐户一起迁移。 迁移后，应指示用户为他们安排的任何联机会议更新链接。 在安装 Lync 2013 客户端后，他们可以通过打开计划会议邀请（更新会议 URL）并将邀请重新发送给参与者来执行此操作。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 迁移期间的用户体验

本节提供从 Lync 2010 迁移时用户的会议体验的摘要。 有关 Lync Server 2013 客户端如何共存以及如何与以前的客户端和服务器版本交互的详细信息，请参阅 [Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>将 Lync Server 2010 会议与 Lync 2013 客户端加入

在从 Lync Server 2010 迁移过程中，当用户加入 lync Server 2010 会议和 Lync 2013 客户端时，可能会有一段共存时间。 这些用户有权访问 Lync 2013 客户端功能，但有以下例外：

  - 在 **参与者** 管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，" **无会议即时消息** " 选项不起作用。

  - 库视图在视频会议中不起作用。 用户仅看到活动的扬声器，而不是所有扬声器。 在 " **选取布局** " 选项列表中，" **库视图** " 不可用

  - 默认情况下，参与者列表在视频会议中显示。

  - 右键单击 "参与者" 列表中的用户时，" **锁定视频焦点** 并 **固定到库** 参与者管理" 选项不可用。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office 通信服务器 2007 R2 迁移期间的用户体验

本部分提供了在安装 Lync 2013 之前和之后从 Office 通信服务器 2007 R2 迁移时用户的会议体验摘要。 有关 Lync Server 2013 客户端如何共存以及如何与以前的客户端和服务器版本交互的详细信息，请参阅 [Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>在迁移用户帐户之后，安装 Lync 2013 之前

将用户迁移到 Lync Server 2013 服务器，但在安装新客户端之前，Office Communicator 2007 R2 用户可以继续使用其现有客户端，使其与 Lync Server 2013 相关的状态和 IM 功能，但不支持会议功能。

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>在迁移用户帐户后，安装 Lync 2013 之后

当已迁移的用户安装 Lync 2013 时，将同时安装 Lync 2013 的联机会议外接程序。 这具有以下效果：

  - 以后安排的所有会议都使用新会议格式，即使用 https:// 地址，而不是旧 meet:// Live Meeting 地址。

  - 在 Lync 2013 的 IT 托管部署中，管理员可以选择卸载 Microsoft Office Outlook 的会议外接程序，该外接程序用于安排 Live Meeting 服务器和基于服务的会议。 然而，您的用户可能需要继续安排 Live Meeting 服务会议。 在这种情况下，您可以允许两个外接程序共存。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>与使用早期客户端的联盟组织召开的会议

联合组织中使用 Microsoft Office Communicator 2007 的用户无法加入组织中的 Lync Server 2013 会议（如果组织已锁定这些会议）。 您必须在 Lync Server 2013 中重新安排这些会议，以便在联合参与者使用新的 https://会议 URL 加入会议时，他们可以使用 Lync Web App。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

