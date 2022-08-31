---
title: 管理谁可以开始即时会议和安排会议
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 了解如何使用 Teams 会议策略设置来控制谁可以启动即时会议和安排会议。
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466284"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>管理谁可以开始即时会议和安排会议

作为管理员，你可以限制哪些用户可以在 Teams 中启动即时会议和安排会议。 出于隐私和安全原因，这可能特别有用，因为你可能不希望特定用户设置会议。

默认情况下，会打开会议策略设置。 这些设置可以在 Teams 管理中心中根据 **会议** > **会议策略** 找到。

- **立即在频道中开会**：控制用户是否可以在频道中启动即时会议。
- **频道会议日程安排**：控制用户是否可以在频道中安排会议。
- **私人会议计划**：控制用户是否可以在 Teams 中安排私人会议。 当会议未发布到团队中的某个频道时，这个会议就是私人的。
- **Outlook 加载** 项：控制用户是否可以从 Outlook 安排私人会议。 当会议未发布到团队中的某个频道时，这个会议就是私人的。
- **立即在私人会议中开会**：控制用户是否可以启动即时私人会议。

> [!NOTE]
> 如果会议是由代理人发送的，该代表有权代表另一个人（例如经理）发送会议邀请，则会议策略设置将应用于 (经理) 授予权限的人员。

## <a name="channel-meetings"></a>频道会议

如果符合性要求仅要求特定人员启动即时频道会议和安排频道会议，则可以创建或更新会议策略以限制这些设置。 然后，可以创建一个单独的策略，该策略归于想要启动即时频道会议和安排频道会议的用户。

1. 在 Teams 管理中心，转到 **会议** > **会议策略** 并选择要更新的策略。 若要创建新策略，请单击 **“添加**”。
1. 在 **“常规**”下切换以下内容：
    1. 如果要限制可在频道中启动即时会议的人员， **请立即在频道中将“会议** ”切换为 **“关闭**”。
    1. 如果要限制谁可以在频道中安排会议，请将 **频道会议安排** 切换为 **“关闭**”。
1. 点击页面底部的 **“保存** ”。

## <a name="private-meetings"></a>私人会议

如果符合性要求仅要求特定人员启动即时私人会议并安排私人会议，则可以创建或更新会议策略以限制这些设置。 然后，可以创建一个单独的策略，该策略归于想要启动即时会议和安排私人会议的用户。

1. 在 Teams 管理中心，转到 **会议** > **会议策略** 并选择要更新的策略。 若要创建新策略，请单击 **“添加**”。
1. 在 **“常规**”下切换以下内容：
    1. 如果要限制谁可以启动即时私人会议，请 **将私人会议中的“立即开会** ”切换为 **“关闭**”。
    1. 如果要限制谁可以在频道中安排私人会议，请将 **“私人会议计划** ”和 **“Outlook 外接** 程序”切换为 **“关闭**”。
1. 点击页面底部的 **“保存** ”。

## <a name="turning-off-meeting-policy-settings"></a>关闭会议策略设置

关闭这些会议策略设置后，分配给该策略的任何用户将无法启动或安排此类会议。 用户以前启动或计划的所有现有会议的会议加入链接和会议 ID 将不起作用。  (会话、文件、白板、录音、脚本和其他与会议相关的内容被保留，用户仍然可以访问它们。) 

如果会议策略设置已关闭，然后再次为用户打开，则用户组织的所有以前安排的会议将变为活动状态，用户可以使用会议加入链接或电话加入这些会议。

## <a name="related-topics"></a>相关主题

[更改会议到期日期 - 最终用户控件](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[管理 Teams 中的会议策略](meeting-policies-overview.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[Microsoft Teams 的限制和规范](/microsoftteams/limits-specifications-teams)
