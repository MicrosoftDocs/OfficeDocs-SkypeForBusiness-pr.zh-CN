---
title: 管理会议Microsoft Teams
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
description: 了解如何在会议中管理会议策略Teams并使用它们来控制可供会议参与者用于用户安排的会议的功能。
ms.openlocfilehash: 4db3b935526daad03d3d51281944422b597cbc00
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234757"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>管理会议Microsoft Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。 可以使用自动创建的全局 (默认整个组织) 策略，也可以创建和分配自定义策略。 可以在 Microsoft Teams 管理中心内或使用 [PowerShell](teams-powershell-overview.md) 管理会议策略。

> [!NOTE]
> 有关使用角色管理会议演示者和与会者权限的信息，请参阅 [Teams 会议角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

可以通过以下方式实施策略，这些策略会在会议开始前、会议期间或会议结束后影响用户的会议体验。

|实施类型  |说明  |
|---------|---------|
|按组织者    |如果你实现按组织者策略，所有会议参加者都会继承组织者的策略。 例如 **，"自动** 允许人员"是按组织者的策略，用于控制用户是直接加入会议，还是等待分配有该策略的用户安排的会议。          |
|按用户    |实施按用户策略时，只有每用户策略适用于限制组织者和/或会议参与者的某些功能。 例如， **“在频道中允许立即开会”** 是按用户策略。     |
|按组织者和按用户     |当实施按组织者和按用户策略的组合时，会根据会议参与者的策略和组织者的策略对其进行某些功能限制。 例如，**“允许云录制”** 是按组织者和按用户策略。 打开此设置以允许会议组织者和参与者开始和停止录制。

可编辑全局策略中的设置，或创建和分配一个或多个自定义策略。 除非创建并指定一个自定义策略，否则用户将获得全局策略。

> [!NOTE]
> 如果用户启用了音频会议许可或允许用户进行音频会议，则会议详情按钮将可用，否则，会议详情将不可用。

## <a name="create-a-custom-meeting-policy"></a>创建自定义会议策略

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。
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

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 在此处根据需要进行更改。
4. 单击“**保存**”。

> [!NOTE]
> 一次只能向一个用户分配一个会议策略。

## <a name="assign-a-meeting-policy-to-users"></a>将会议策略分配给用户

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果已将它分配给用户，则无法删除该策略。 必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。

## <a name="meeting-policy-settings"></a>会议策略设置

在"会议策略"页面上选择现有策略或选择"添加"以添加新策略时，可以配置以下设置。

- [常规](meeting-policies-in-teams-general.md)
- [音频和视频](meeting-policies-audio-and-video.md)
- [内容共享](meeting-policies-content-sharing.md)
- [参与者和来宾](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)