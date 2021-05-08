---
title: 从会议拨出以便其他人可以加入
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 会议组织者可以了解如何使用 Teams 应用拨出，以允许其他人使用其电话加入同一会议。
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119281"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="f69b0-103">从 Microsoft Teams 会议拨出，以便其他人可以加入会议</span><span class="sxs-lookup"><span data-stu-id="f69b0-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="f69b0-104">作为会议组织者，您可以使用会议Teams拨出，让其他人使用其电话加入同一会议。</span><span class="sxs-lookup"><span data-stu-id="f69b0-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="f69b0-105">当你向某人拨出时，我们建议你使用其完整电话号码 (包括国家/地区代码 - E.164 格式) 。</span><span class="sxs-lookup"><span data-stu-id="f69b0-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="f69b0-106">请注意：</span><span class="sxs-lookup"><span data-stu-id="f69b0-106">Please note that:</span></span>

- <span data-ttu-id="f69b0-107">只有当使用会议加入会议时，才能拨出Teams。</span><span class="sxs-lookup"><span data-stu-id="f69b0-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="f69b0-108">会议组织者已启用音频会议，或者，如果没有分配音频会议许可证，则允许通过在线呼叫计划或直接路由向公共电话交换网络拨打电话。</span><span class="sxs-lookup"><span data-stu-id="f69b0-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="f69b0-109">为会议组织者授予启用从会议拨出 [的联机拨出策略](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f69b0-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="f69b0-110">下面将了解如何拨出以工作：</span><span class="sxs-lookup"><span data-stu-id="f69b0-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="f69b0-111">**步骤 1：** 在会议中，使用"添加人员"按钮选项的"添加人员"屏幕截图 ![ ](media/add-people-button.png) 拨打电话号码。</span><span class="sxs-lookup"><span data-stu-id="f69b0-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="f69b0-112">**步骤 2：** 在"邀请某人或拨打号码"框中输入完整的电话号码，包括国家/ **地区** 代码。</span><span class="sxs-lookup"><span data-stu-id="f69b0-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
!["邀请某人或拨打号码"框的屏幕截图](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="f69b0-114">支持的国家和地区</span><span class="sxs-lookup"><span data-stu-id="f69b0-114">Supported countries and regions</span></span>

<span data-ttu-id="f69b0-115">拨出功能仅适用于某些国家/地区。</span><span class="sxs-lookup"><span data-stu-id="f69b0-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="f69b0-116">有关完整列表，请参阅音频会议和通话计划的"国家[/地区"和"区域可用性"。](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="f69b0-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="f69b0-117">允许用户拨入</span><span class="sxs-lookup"><span data-stu-id="f69b0-117">Allow users to dial in</span></span>

<span data-ttu-id="f69b0-118">如果你正在寻找有关如何让用户拨入 Teams 会议的说明，请参阅 Microsoft Teams 中的音频电话[号码](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f69b0-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="f69b0-119">想要了解有关音频会议更多信息？</span><span class="sxs-lookup"><span data-stu-id="f69b0-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="f69b0-120">尝试或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="f69b0-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="f69b0-121">Microsoft Teams 附加许可</span><span class="sxs-lookup"><span data-stu-id="f69b0-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)