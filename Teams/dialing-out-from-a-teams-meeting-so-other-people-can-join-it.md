---
title: 从会议拨出，以便其他人可以加入
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
description: 会议组织者可以了解如何使用 "团队" 应用拨出，让其他人可以使用他们的电话加入同一会议。
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788756"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="62e04-103">从 Microsoft Teams 会议拨出，以便其他人可以加入会议</span><span class="sxs-lookup"><span data-stu-id="62e04-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="62e04-104">作为会议组织者，您可以使用 "团队" 应用拨出，让其他人使用他们的电话加入同一会议。</span><span class="sxs-lookup"><span data-stu-id="62e04-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="62e04-105">当您拨出给某人时，我们建议您使用其完整的电话号码， (包括国家/地区代码-164 格式) 。</span><span class="sxs-lookup"><span data-stu-id="62e04-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="62e04-106">请注意：</span><span class="sxs-lookup"><span data-stu-id="62e04-106">Please note that:</span></span>

- <span data-ttu-id="62e04-107">只有在使用团队加入会议时，才可以拨出。</span><span class="sxs-lookup"><span data-stu-id="62e04-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="62e04-108">会议组织者已启用音频会议，或者在未分配音频会议许可证的情况下，允许通过在线呼叫计划或直接路由拨打公共交换电话网络。</span><span class="sxs-lookup"><span data-stu-id="62e04-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="62e04-109">为会议组织者 [授予了允许从会议拨出的联机拨出策略](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="62e04-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="62e04-110">下面介绍了如何使用拨出功能：</span><span class="sxs-lookup"><span data-stu-id="62e04-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="62e04-111">**步骤1：** 在会议中，使用 "添加人员" 按钮选项的 " **添加人员**" ![ 屏幕截图 ](media/add-people-button.png) 拨出电话号码。</span><span class="sxs-lookup"><span data-stu-id="62e04-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="62e04-112">**步骤2：** 输入完整的电话号码，包括 " **邀请他人或拨打号码** " 框中的国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="62e04-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
!["邀请某人或拨打号码" 框的屏幕截图](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="62e04-114">支持的国家和地区</span><span class="sxs-lookup"><span data-stu-id="62e04-114">Supported countries and regions</span></span>

<span data-ttu-id="62e04-115">拨出功能仅适用于某些国家/地区。</span><span class="sxs-lookup"><span data-stu-id="62e04-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="62e04-116">有关完整列表，请参阅 [音频会议和通话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="62e04-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="62e04-117">允许用户拨入</span><span class="sxs-lookup"><span data-stu-id="62e04-117">Allow users to dial in</span></span>

<span data-ttu-id="62e04-118">如果你正在查找有关如何让你的用户拨入团队会议的说明，请参阅 [Microsoft 团队中的音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="62e04-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="62e04-119">想要了解有关音频会议的详细信息？</span><span class="sxs-lookup"><span data-stu-id="62e04-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="62e04-120">试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="62e04-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="62e04-121">Microsoft Teams 附加许可</span><span class="sxs-lookup"><span data-stu-id="62e04-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
