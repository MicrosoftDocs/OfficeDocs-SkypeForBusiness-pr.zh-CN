---
title: 在"会议"中为用户设置会议拨出Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置Teams以请求拨出确认，以防止当被呼叫者无法接听呼叫时语音邮件系统连接到会议。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117090"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="23aae-103">在"会议"中为用户设置会议拨出Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23aae-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="23aae-104">会议拨出和呼叫我是邀请参与者加入会议以及让现有参与者使用传统或移动电话加入会议非常有用的方法。</span><span class="sxs-lookup"><span data-stu-id="23aae-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="23aae-105">但是，当被呼叫者无法接听呼叫并且呼叫由语音邮件系统应答时，语音邮件系统将连接到会议，参与者将能够收听它，直到它从会议中删除。</span><span class="sxs-lookup"><span data-stu-id="23aae-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="23aae-106">若要防止在将会议拨出发送到电话号码且被呼叫者无法接听呼叫时，语音邮件系统连接到会议，您可以设置 Teams 以请求被呼叫者确认他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="23aae-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="23aae-107">如果被呼叫者无法接听呼叫并且呼叫由语音邮件系统应答，则语音邮件系统不会连接到会议，因为它不会提供加入会议确认。</span><span class="sxs-lookup"><span data-stu-id="23aae-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="23aae-108">启用此功能后，收到拨出或呼叫我呼叫的人必须通过在传统电话或移动电话上按 1 确认他们想要加入会议。</span><span class="sxs-lookup"><span data-stu-id="23aae-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="23aae-109">若要为组织的所有会议启用此功能，将 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数设置为 ```true``` 。</span><span class="sxs-lookup"><span data-stu-id="23aae-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="23aae-110">要执行此操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23aae-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="23aae-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="23aae-111">Related topics</span></span>

- [<span data-ttu-id="23aae-112">为用户设置“致电我”功能</span><span class="sxs-lookup"><span data-stu-id="23aae-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="23aae-113">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="23aae-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)