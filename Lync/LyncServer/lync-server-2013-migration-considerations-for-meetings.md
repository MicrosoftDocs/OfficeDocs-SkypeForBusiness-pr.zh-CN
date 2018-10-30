---
title: 针对会议的迁移注意事项
TOCTitle: 针对会议的迁移注意事项
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61115128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 针对会议的迁移注意事项

 

_**上一次修改主题：** 2014-02-10_

本部分讨论以下主题：

  - Microsoft Lync Server 2013 中对会议的更改

  - 基于用户的会议需求迁移用户

  - 迁移现有会议和会议内容

  - 迁移 Lync Server 2010 期间的用户体验

  - 迁移 Office Communications Server 2007 R2 期间的用户体验

  - Microsoft Lync 2013 与早期版本中的会议的兼容性

## Lync Server 2013 中对会议的更改

**Lync Server 2013 功能。**   Lync Server 2013 向用户提供了新的会议功能，这些功能在用户的帐户迁移到 Lync Server 2013 且用户使用 Lync 2013 客户端登录后对用户可用。[Lync Server 2013 中新的会议功能](lync-server-2013-new-conferencing-features.md)和[Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)中列出了这些新功能。

**会议 URL。**   与在 Lync Server 2010 中一样，在 Lync Server 2013 中所有新计划的会议都有 URL 前缀 https://，现有会议与用户帐户一起迁移。但是，Lync Server 2013 不支持 Office Communications Server 2007 R2 电话会议（conf:// URL 前缀） 或 Web 会议（meet:// URL 前缀）。有关详细信息，请参阅本主题后面部分中的”从 Office Communications Server 2007 R2 迁移会议”。

**客户端支持。**   与 Lync Server 2010 不同，Lync Server 2013 不支持对会议使用 Office Communicator 客户端。您无法通过 Lync 2013 联机会议外接程序 使用下列客户端加入计划的会议：

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

在迁移期间，Office Communicator 2007 R2 用户在其客户端升级之前应使用 Lync Web App 2013 加入 Lync Server 2013 会议。注意，Office Communicator 2007 R2 用户可以继续使用其现有客户端（相对于 Lync Server 2013）使用联机状态和 IM 功能，但会议功能不受支持。


## 基于用户的会议需求迁移用户

**常用会议组织者。**   考虑在迁移过程早期迁移常用会议组织者，以便他们能利用[Lync Server 2013 中新的会议功能](lync-server-2013-new-conferencing-features.md)和[Lync Server 2013 中面向客户端的新内容](lync-server-2013-what-s-new-for-clients.md)中列出的新的 Lync Server 2013 和 Lync 2013 功能。

**Live Meeting 用户。**   如果您正要从 Office Communications Server 2007 R2 迁移，而且您的用户需要使用特定于 Live Meeting 的 Web 会议功能（针对大型会议和分支房间提供的特别支持），您可选择以下选项：

  - 建议组织者使用 Live Meeting 服务（如果您的组织中提供该服务）。

  - 保持组织者留在早期版本的 Office Communications Server 中，以便他们可以继续计划基于服务器的 Live Meeting Web 会议。

## 迁移现有会议和会议内容

## 从 Lync Server 2010 迁移会议

将用户从 Lync Server 2010 迁移到 Lync Server 2013 时，以下信息随用户的帐户一起迁移：

  - 用户已计划的会议。这包括会议目录和会议数据。

  - 用户的个人标识号 (PIN)。用户当前的 PIN 在到期或用户请求新 PIN 之前仍然有效。

但是，以下用户帐户信息不回迁移到新服务器：

  - 会议内容（例如 PowerPoint 演示文稿）、白板内容、投票数据

要迁移已在会议中共享的内容，请使用 Move-CsUser cmdlet 的 MoveMeetingContent 参数。有关使用此 cmdlet 的详细信息，请参阅 Lync Server 2013 cmdlet 文档中的 [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)。

## 从 Office Communications Server 2007 R2 迁移会议

Office Communications Server 2007 R2 会议要么是电话会议（conf:// URL 前缀），要么是 Web 会议（meet:// URL 前缀）。Lync Server 2013 不支持这些早期版本的 conf:// 和 meet:// 会议，这些会议与用户帐户一起迁移。迁移后，您应指导用户更新他们已计划的所有联机会议的链接。他们可以在安装 Lync 2013 客户端后通过以下操作执行此更新：打开已计划的会议的邀请 - 这会更新会议 URL - 并重新发送给参与者。

## 迁移 Lync Server 2010 期间的用户体验

本部分概要介绍从 Lync 2010 迁移时的用户体验。有关 Lync Server 2013 客户端怎样可以与以前版本的客户端和服务器共存并与之交互的详细信息，请参阅 [Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

## 使用 Lync 2013 客户端加入 Lync Server 2010 会议

从 Lync Server 2010 迁移期间，可能有一段共存期，在此期间用户可以使用 Lync 2013 客户端加入 Lync Server 2010 会议。这些用户可以访问 Lync 2013 客户端功能，但存在以下例外：

  - 在“参与者”管理选项（可通过指向会议窗口中的人员访问这些选项）中，“关闭会议即时消息”选项不起作用。

  - 在视频会议中，“库视图”不起作用。用户只能看到当前发言人，而不是看到所有发言人。在“选择布局”选项中，“库视图”不可用。

  - 在视频会议中，默认情况下显示参与者列表。

  - 在参与者列表中右键单击用户时，“锁定视频焦点”和“固定至库”参与者管理选项不可用。

## 迁移 Office Communications Server 2007 R2 期间的用户体验

部分概要介绍从 Office Communications Server 2007 R2 迁移时的用户体验，安装 Lync 2013 之前和之后的用户体验都包括。有关 Lync Server 2013 客户端怎样可以与以前版本的客户端和服务器共存并与之交互的详细信息，请参阅[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。

## 在迁移用户帐户后，安装 Lync 2013 之前

将用户迁移到 Lync Server 2013 服务器之后，安装新的客户端之前，Office Communicator 2007 R2 用户可以继续使用其现有客户端（相对于 Lync Server 2013） 使用联机状态和 IM 功能，但会议功能不受支持。

## 在迁移用户帐户后，安装 Lync 2013 之后

当迁移的用户安装 Lync 2013 时，Lync 2013 的联机会议外接程序会同时安装。这有以下影响：

  - 所有后续计划的会议都使用新的会议格式，新格式使用 https:// 地址，而不是以前的 meet:// Live Meeting 地址。

  - 在 Lync 2013 的 IT 托管的部署中，管理员可以选择不安装 Microsoft Office Outlook 会议外接程序 （用于计划 Live Meeting 服务器和基于服务的会议）。然而，您可能有一些用户需要继续计划 Live Meeting 服务会议。在这种情况下，您可以允许两个外接程序共存。

## 会议与使用以前的客户端的联盟组织

如果您的组织中的 Lync Server 2013 会议被组织者锁定，则使用 Microsoft Office Communicator 2007 的联盟组织中的用户无法加入这些会议。您必须在 Lync Server 2013 中重新计划这些会议，以便联盟参与者在使用新的 https:// meeting URL 加入会议时能够使用 Lync Web App。

