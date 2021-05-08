---
title: 管理 Exchange 统一消息和托管语音邮件
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 PowerShell 在 Exchange Online 中管理统一消息自动助理以及托管的语音邮件等Skype for Business功能。
ms.openlocfilehash: 1a841b377fbc84d85f085dc9d479fa05cc0b2be4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238735"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="cca1e-103">管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="cca1e-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="cca1e-104">可以使用一Exchange cmdlet 在 Skype for Business Online 中管理统一消息和托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="cca1e-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="cca1e-105">管理Exchange统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="cca1e-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="cca1e-106">以下 cmdlet 可用于管理统一消息Exchange UM (和) 策略：</span><span class="sxs-lookup"><span data-stu-id="cca1e-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  

| <span data-ttu-id="cca1e-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cca1e-107">**Cmdlet**</span></span>                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="cca1e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cca1e-108">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="cca1e-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cca1e-109">Get-CsExUmContact</span></span>](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [<span data-ttu-id="cca1e-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cca1e-110">New-CsExUmContact</span></span>](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[<span data-ttu-id="cca1e-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cca1e-111">Remove-CsExUmContact</span></span>](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[<span data-ttu-id="cca1e-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cca1e-112">Set-CsExUmContact</span></span>](/powershell/module/skype/Set-CsExUmContact) <br/> | <span data-ttu-id="cca1e-113">当 UM 是托管服务自动助理时，创建和管理用于 Exchange 和订阅者访问服务的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="cca1e-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="cca1e-114">Skype for BusinessOnline 与 Exchange UM 一起提供多个语音相关功能，包括自动助理和订户访问。</span><span class="sxs-lookup"><span data-stu-id="cca1e-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="cca1e-115">自动助理提供了一种自动应答呼叫并路由到正确人员的方法。</span><span class="sxs-lookup"><span data-stu-id="cca1e-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="cca1e-116">订户访问允许用户连接到 UM Exchange检索电子邮件、语音消息、联系人和日历信息。</span><span class="sxs-lookup"><span data-stu-id="cca1e-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="cca1e-117">当Exchange UM 作为托管服务提供时，必须使用 Microsoft PowerShell 创建用于 自动助理 和订阅者访问服务的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="cca1e-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="cca1e-118">这些对象是使用 **CsExUmContact** cmdlet 创建和管理的。</span><span class="sxs-lookup"><span data-stu-id="cca1e-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
| [<span data-ttu-id="cca1e-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cca1e-119">Get-CSHostedVoicemailPolicy</span></span>](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[<span data-ttu-id="cca1e-120">Grant-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cca1e-120">Grant-CSHostedVoicemailPolicy</span></span>](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | <span data-ttu-id="cca1e-121">管理组织中使用的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="cca1e-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="cca1e-122">托管语音邮件策略指定如何将未接听的呼叫路由到Exchange UM 服务。</span><span class="sxs-lookup"><span data-stu-id="cca1e-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="cca1e-123">这些策略仅影响已启用 UM 托管语音邮件Exchange用户。</span><span class="sxs-lookup"><span data-stu-id="cca1e-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="cca1e-124">若要验证用户是否启用了托管语音邮件，请从 PowerShell 提示符运行如下所示的命令。</span><span class="sxs-lookup"><span data-stu-id="cca1e-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="cca1e-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="cca1e-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span>                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a><span data-ttu-id="cca1e-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="cca1e-126">Related topics</span></span>
[<span data-ttu-id="cca1e-127">使用 Skype for business Online 管理设置计算机Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cca1e-127">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
