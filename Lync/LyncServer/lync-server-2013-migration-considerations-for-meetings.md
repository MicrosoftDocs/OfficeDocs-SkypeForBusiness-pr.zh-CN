---
title: Lync Server 2013：会议的迁移注意事项
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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中的会议的迁移注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-10_

本节将讨论以下主题：

  - Microsoft Lync Server 2013 中的会议更改

  - 基于用户的会议需求迁移用户

  - 迁移现有会议和会议内容

  - Lync Server 2010 迁移期间的用户体验

  - Office 通信服务器 2007 R2 迁移期间的用户体验

  - Microsoft Lync 2013 与早期服务器版本上的会议兼容

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013 中的会议更改

**Lync Server 2013 功能。**   Lync server 2013 提供新的会议功能，这些功能将在帐户移动到 lync Server 2013 并使用 Lync 2013 客户端登录后向用户提供。 [Lync server 2013 中的新会议功能](lync-server-2013-new-conferencing-features.md)概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

**会议 URL。**   在 lync server 2010 中，lync server 2013 中的所有新计划会议都具有 HTTPS://的 URL 前缀，并且现有会议与用户帐户一起迁移。 但是，Lync Server 2013 不支持 Office 通信服务器 2007 R2 电话会议（conf://URL 前缀）或 web 会议（meet://URL 前缀）。 有关详细信息，请参阅本主题后面部分的 "从 Office 通信服务器迁移会议 2007 R2"。

**客户端支持。**   与 lync server 2010 不同，lync server 2013 不支持用于会议的 Office Communicator 客户端。 无法使用以下客户端加入通过 Lync 2013 的联机会议加载项安排的会议：

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

在迁移期间，Office Communicator 2007 R2 用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议，直到他们的客户升级。 请注意，Office Communicator 2007 R2 用户可以继续使用其现有客户端与 Lync Server 2013 进行状态和 IM 功能，但不支持会议功能。

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>基于用户的会议需求迁移用户

**频繁的会议组织者。**   请考虑在流程早期迁移频繁的会议组织者，以便他们可以利用[lync Server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述的新 Lync server 2013 和 lync 2013 功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。

**Live Meeting 用户。**   如果您从 Office 通信服务器 2007 R2 迁移，并且您有需要特定于 Live Meeting 的 web 会议功能的用户（特别是对大型会议和休息会议室的支持），则可以使用以下选项：

  - 建议组织者使用 Live Meeting 服务（如果在你的组织中可用）。

  - 让组织者驻留在早期版本的 Office 通信服务器上，以便他们可以继续安排基于服务器的 Live Meeting web 会议。

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>从 Lync Server 2010 迁移会议

将用户从 Lync Server 2010 移动到 Lync Server 2013 时，以下信息将与用户帐户一起移动：

  - 已由用户安排的会议。 这包括会议目录和会议数据。

  - 用户的个人识别码（PIN）。 用户的当前 PIN 将继续工作，直到过期或用户请求新的 PIN。

但是，以下用户帐户信息不会移动到新服务器：

  - 会议内容，例如 PowerPoint 演示文稿、白板内容和投票数据

若要移动已在会议中共享的内容，请使用 Move-csuser cmdlet 的 MoveMeetingContent 参数。 有关使用此 cmdlet 的详细信息，请参阅 Lync Server 2013 cmdlet 文档中的[move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>从 Office 通信服务器 2007 R2 迁移会议

Office 通信服务器 2007 R2 会议可以是电话会议（conf://URL 前缀），也可以是 web 会议（meet://URL 前缀）。 Lync Server 2013 不支持这些以前的 conf://和 meet://会议，它们不会与用户帐户一起迁移。 迁移后，应指示用户更新已安排的任何联机会议的链接。 他们可以在安装 Lync 2013 客户端后执行此操作，方法是打开一个计划会议邀请（更新会议 URL），并向参与者重新发送邀请。

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 迁移期间的用户体验

本部分提供从 Lync 2010 迁移时用户会议体验的摘要。 有关 Lync Server 2013 客户端可如何共存以及如何与以前的客户端和服务器版本交互的更多详细信息，请参阅[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>使用 Lync 2013 客户端加入 Lync Server 2010 会议

从 Lync Server 2010 迁移期间，在用户使用 Lync 2013 客户端加入 Lync Server 2010 会议时可能会有一段共存。 这些用户有权访问 Lync 2013 客户端功能，但出现以下异常：

  - 在**参与者**管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，"**无会议即时消息**" 选项不起作用。

  - 库视图在视频会议中不起作用。 用户仅看到活动的扬声器，而不是所有扬声器。 在 "**选择布局**" 选项列表中，"**库视图**" 不可用

  - 参与者列表默认情况下显示在视频会议中。

  - 右键单击参与者列表中的用户时，**锁定视频焦点**和**固定到库**参与者管理选项不可用。

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office 通信服务器 2007 R2 迁移期间的用户体验

本部分提供了在安装 Lync 2013 之前和之后从 Office 通信服务器 2007 R2 迁移时的用户会议体验的摘要。 有关 Lync Server 2013 客户端可如何共存以及如何与以前的客户端和服务器版本交互的更多详细信息，请参阅[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>在迁移用户帐户之后，安装 Lync 2013 之前

将用户迁移到 Lync Server 2013 服务器后，在安装新客户之前，Office Communicator 2007 R2 用户可以继续使用其现有客户端与 Lync Server 2013 的状态和 IM 功能，但会议功能不会能.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>在迁移用户帐户后，安装 Lync 2013 后

当已迁移用户安装 Lync 2013 时，也会安装 Lync 2013 的联机会议外接程序。 这具有以下效果：

  - 所有后续计划的会议都使用新的会议格式，该格式使用 https://地址，而不是旧版 meet://Live 会议地址。

  - 在 Lync 2013 的 IT 托管部署中，管理员可以选择卸载 Microsoft Office Outlook 的会议加载项，该加载项用于安排 Live Meeting 服务器和基于服务的会议。 但是，你可能需要继续安排 Live Meeting 服务会议的用户。 在这种情况下，你可以允许两个外接程序共存。

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>使用以前客户端的联盟组织的会议

在组织中使用 Microsoft Office Communicator 2007 的联盟组织中的用户无法加入您组织中的 Lync Server 2013 会议（如果该会议由组织者锁定）。 您必须在 Lync Server 2013 中重新安排这些会议，以便在联盟参与者使用新的 https://会议 URL 加入会议时，他们可以使用 Lync Web App。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

