---
title: 在 Skype for Business Server 中配置无 PIN 会议加入
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：了解如何在 Skype for Business Server 中配置无 PIN 会议加入选项。
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827982"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="f2e59-103">在 Skype for Business Server 中配置无 PIN 会议加入</span><span class="sxs-lookup"><span data-stu-id="f2e59-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="f2e59-104">**摘要：** 了解如何在 Skype for Business Server 中配置无 PIN 会议加入选项。</span><span class="sxs-lookup"><span data-stu-id="f2e59-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="f2e59-105">当拨入呼叫者尝试加入会议时，会议 自动助理 (CAA) 服务将呼叫者放在一个与会议厅 &#x2014; 不同的长笔（如果演示者尚未呼叫，并且拨入呼叫者尚未输入主持人 PIN）。</span><span class="sxs-lookup"><span data-stu-id="f2e59-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="f2e59-106">无 PIN 会议加入选项允许拨入呼叫者加入会议，无需输入领导者 PIN，即使他们是第一个呼叫者。</span><span class="sxs-lookup"><span data-stu-id="f2e59-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="f2e59-107">配置此功能时，请牢记以下事项：</span><span class="sxs-lookup"><span data-stu-id="f2e59-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="f2e59-108">仅适用于私人会议。</span><span class="sxs-lookup"><span data-stu-id="f2e59-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="f2e59-109">允许 PSTN 呼叫者在没有经过身份验证的用户的情况下留在私人会议中。</span><span class="sxs-lookup"><span data-stu-id="f2e59-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="f2e59-110">更改设置后，它适用于所有现有和新的私人会议。</span><span class="sxs-lookup"><span data-stu-id="f2e59-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="f2e59-111">可在组织者的站点或全局级别启用。</span><span class="sxs-lookup"><span data-stu-id="f2e59-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="f2e59-112">可以针对以下任一项设置可以绕过大厅的选项：</span><span class="sxs-lookup"><span data-stu-id="f2e59-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="f2e59-113">**来自我的组织的任何人与呼叫者直接进入**</span><span class="sxs-lookup"><span data-stu-id="f2e59-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="f2e59-114">**对 (没有**) 呼叫者的任何用户 (这是默认设置。) </span><span class="sxs-lookup"><span data-stu-id="f2e59-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="f2e59-115">当配置为启用无 PIN 加入时，CAA 服务仍提示输入领导者 PIN。</span><span class="sxs-lookup"><span data-stu-id="f2e59-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="f2e59-116">无论输入了 PIN，用户都可以加入会议。</span><span class="sxs-lookup"><span data-stu-id="f2e59-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="f2e59-117">但是，保留输入领导者 PIN 的能力允许拨入呼叫者以领导者身份进行身份验证，并在必要时管理会议。</span><span class="sxs-lookup"><span data-stu-id="f2e59-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="f2e59-118">配置无 PIN 会议加入</span><span class="sxs-lookup"><span data-stu-id="f2e59-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="f2e59-119">若要为用户启用无 PIN 会议加入，请使用带 AllowAnonymousPstnActivation 参数的 [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2e59-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="f2e59-120">例如，以下命令为站点 Redmond 启用无 PIN 会议加入：</span><span class="sxs-lookup"><span data-stu-id="f2e59-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="f2e59-121">出于安全考虑，当启用无 PIN 会议加入时，您可能希望通过确保 ConferencingPolicy 设置如下来限制匿名用户拨出：</span><span class="sxs-lookup"><span data-stu-id="f2e59-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="f2e59-122">有关详细信息，请参阅 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f2e59-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

