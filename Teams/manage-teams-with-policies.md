---
title: 使用策略管理 Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解 Teams 策略。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574181"
---
# <a name="manage-teams-with-policies"></a>使用策略管理 Teams

策略是管理 Teams 的重要部分。 使用本文导航如何使用策略为组织带来好处。

## <a name="what-you-use-policies-for"></a>策略用于什么

策略用于在组织中跨不同领域（如消息传递、会议和应用程序）完成许多任务。 你可以执行一些操作，包括允许用户在团队频道中安排会议、允许用户编辑已发送的消息，以及控制用户是否可以将应用固定到 Teams 应用栏。

## <a name="how-to-assign-policies"></a>如何分配策略

根据组织要尝试完成的任务，可以通过多种不同方式分配策略。 可以在 Teams 管理中心进行作业和查看作业。

![组策略分配的屏幕截图。](media/group-policy-assignment.png)

在此处详细了解如何分配 [策略](policy-assignment-overview.md)。

## <a name="how-to-manage-policies"></a>如何管理策略

策略通过 Microsoft Teams 管理中心或 [PowerShell 进行管理](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。

例如，应用设置策略允许你允许用户上传自定义应用、代表用户安装应用，以及将应用固定到 Teams 应用栏。 这些策略在 Teams 管理中心配置。

![应用设置策略的屏幕截图。](media/app-setup-policy.png)

此外，会议策略可用于控制 Teams 会议中的音频和视频设置，例如听录、云录制和 IP 音频/视频。

![会议策略的屏幕截图。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>Teams 教育版

还可使用 Teams [教育策略向导](easy-policy-setup-edu.md) 轻松设置和管理学习环境的策略。

![Teams 教育策略向导的屏幕截图。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>策略类型

可以使用 Microsoft Teams 管理以下策略。

策略类型 | 说明
------------|------------
[策略包](manage-policy-packages.md) | Microsoft Teams 中的策略包是一组预定义的策略和设置，可以分配给组织中具有类似角色的用户。
[会议策略](meeting-policies-in-teams.md) | 会议策略用于控制可用于组织中用户安排的会议的会议参与者的功能。 会议策略包括以下主题。<br> - 音频和视频策略<br> - 内容和屏幕共享策略<br> - 参与者、来宾和访问策略<br> - 常规策略
[语音和呼叫策略](voice-and-calling-policies.md)| 语音和呼叫策略通过紧急呼叫、呼叫路由和呼叫者 ID 等团队管理这些设置。
[应用策略](app-policies.md)| 应用策略用于控制 Microsoft Teams 中的应用程序。 管理员可以允许或阻止用户可以安装哪些应用，将应用程序固定到用户的 Teams 应用栏，并代表用户安装应用程序。
[消息策略](messaging-policies-in-teams.md)| 消息传送策略控制聊天和频道功能的可用性。

## <a name="related-topics"></a>相关主题

* [在 Teams 中分配策略 - 入门](policy-assignment-overview.md)
* [在 Microsoft Teams 中管理反馈策略](manage-feedback-policies-in-teams.md)
* [在 Microsoft Teams 中管理团队策略](teams-policies.md)
* [在 Microsoft Teams 中为实时事件进行设置](teams-live-events/set-up-for-teams-live-events.md)
* [Teams 教育策略和策略包](policy-packages-edu.md)