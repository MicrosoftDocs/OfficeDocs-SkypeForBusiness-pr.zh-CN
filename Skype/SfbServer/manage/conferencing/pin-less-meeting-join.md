---
title: 在 Skype for Business Server 中配置无 PIN 会议加入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要： 了解如何配置 PIN 小于会议加入业务服务器中 Skype 选项。
ms.openlocfilehash: c865d234b58b29890957a2c895a91d84b9a31bb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888105"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="59040-103">在 Skype for Business Server 中配置无 PIN 会议加入</span><span class="sxs-lookup"><span data-stu-id="59040-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="59040-104">**摘要：** 了解如何配置 PIN 小于会议加入业务服务器中 Skype 选项。</span><span class="sxs-lookup"><span data-stu-id="59040-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="59040-105">当电话拨入式呼叫者尝试加入会议时，会议自动助理 (CAA) 服务会将呼叫者放在不同于会议厅 & #x 2014; 保持笔如果演示者已不在呼叫，请与电话拨入式呼叫者未进入主持人 PIN。</span><span class="sxs-lookup"><span data-stu-id="59040-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="59040-106">无 PIN 会议加入选项使拨入呼叫方无需输入主持人 PIN 就能加入会议，即使他们是第一个从加入通话的人也是如此。</span><span class="sxs-lookup"><span data-stu-id="59040-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="59040-107">配置此功能时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="59040-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="59040-108">仅适用于秘密会议。</span><span class="sxs-lookup"><span data-stu-id="59040-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="59040-109">允许 PSTN 呼叫方保持在不包含经过身份验证的用户的私密会议中。</span><span class="sxs-lookup"><span data-stu-id="59040-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="59040-110">在设置发生更改后，它适用于所有现有和新的私密会议。</span><span class="sxs-lookup"><span data-stu-id="59040-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="59040-111">既可以在组织者网站也可以在全局级别启用。</span><span class="sxs-lookup"><span data-stu-id="59040-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="59040-112">可以为以下各项设置能够绕过大厅的人员的选项：</span><span class="sxs-lookup"><span data-stu-id="59040-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="59040-113">**我的组织中的任何人和呼叫者都可以直接参加**</span><span class="sxs-lookup"><span data-stu-id="59040-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="59040-114">**任何人（没有限制）和呼叫者可以直接参加**（这是默认设置。）</span><span class="sxs-lookup"><span data-stu-id="59040-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="59040-115">当配置为启用无 PIN 加入时，CAA 服务仍会提示提供主持人 PIN。</span><span class="sxs-lookup"><span data-stu-id="59040-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="59040-116">无论是否输入 PIN，用户都可以加入会议。</span><span class="sxs-lookup"><span data-stu-id="59040-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="59040-117">但是，保留能够输入 PIN 主持人允许拨入呼叫者可以作为主持人身份验证和管理会议必要。</span><span class="sxs-lookup"><span data-stu-id="59040-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="59040-118">配置无 PIN 会议加入</span><span class="sxs-lookup"><span data-stu-id="59040-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="59040-119">若要为您的用户的 PIN 小于与会，请使用[Set-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet AllowAnonymousPstnActivation 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59040-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="59040-120">例如，以下命令可为站点 Redmond 启用无 PIN 会议加入：</span><span class="sxs-lookup"><span data-stu-id="59040-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="59040-121">为安全起见，当启用无 PIN 会议加入时，你可能需要通过确保 ConferencingPolicy 设置如下来限制匿名用户拨出：</span><span class="sxs-lookup"><span data-stu-id="59040-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="59040-122">有关详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="59040-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

