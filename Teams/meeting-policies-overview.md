---
title: 管理会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理会议策略设置，并使用它们来控制可供会议参与者用于用户安排的会议的功能。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598700"
---
# <a name="manage-meeting-policies-in-teams"></a>管理 Teams 中的会议策略

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。 可以使用全局策略 (组织范围的默认) 自动创建或创建和分配自定义策略的策略。 在 Microsoft Teams 管理中心中或通过使用 [PowerShell 管理会议策略](teams-powershell-overview.md)。

> [!NOTE]
> 有关使用角色管理会议演示者和与会者的权限的信息，请参阅 [Teams 会议中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以通过以下方式实施策略，这会影响用户在会议开始、会议期间或会议后的会议体验。

|实现类型  |说明  |
|---------|---------|
|每个组织者    |实施按组织者的策略时，所有会议参与者将继承组织者的策略。 例如 **，"自动** 允许人员"是按组织者的策略，用于控制用户是直接加入会议，还是等待分配有该策略的用户安排的会议。          |
|按用户    |实施每用户策略时，仅应用按用户策略来限制组织者和/或会议参与者的某些功能。 例如 **，"允许现在在频道中开会** "是按用户的策略。     |
|按组织者和按用户     |实施按组织者策略和按用户策略的组合时，某些功能会基于会议参与者的策略和组织者的策略进行限制。 例如， **允许云录制** 是按组织者和按用户的策略。 打开此设置以允许会议组织者和参与者开始和停止录制。

可以在全局策略中编辑设置，也可以创建并分配一个或多个自定义策略。 除非创建并分配自定义策略，否则用户将获取全局策略。

> [!NOTE]
> 如果用户已启用音频会议许可证或用户允许音频会议，则会议详细信息按钮将可用，否则会议详细信息将不可用。

## <a name="create-a-custom-meeting-policy"></a>创建自定义会议策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**
2. 单击“**添加**”。
3. 输入策略的名称和说明。 名称不能包含特殊字符或超过 64 个字符。
4. 选择想要的设置。
5. 单击“**保存**”。

例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。 你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：

在“音频和视频”中：

- 禁用“允许云录制”。
- 禁用“允许 IP 视频”。

在“内容共享”中：

- 禁用屏幕共享模式。
- 禁用“允许白板”。
- 禁用“允许共享笔记”。

然后将此策略分配给用户。

## <a name="edit-a-meeting-policy"></a>编辑会议策略

可以编辑全局策略和创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 在此处根据需要进行更改。
4. 单击“**保存**”。

> [!NOTE]
> 一次只能为用户分配一个会议策略。

## <a name="assign-a-meeting-policy-to-users"></a>将会议策略分配给用户

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果将用户分配到策略，则不能删除该策略。 必须先将不同的策略分配给所有受影响的用户，然后可以删除原始策略。

## <a name="meeting-policy-settings"></a>会议策略设置

在"会议策略"页面上选择现有策略或选择"添加"以添加新策略时，可以配置以下设置。

- [常规](meeting-policies-in-teams-general.md)
- [音频&视频](meeting-policies-audio-and-video.md)
- [内容共享](meeting-policies-content-sharing.md)
- [来宾&参与者](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户中删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)