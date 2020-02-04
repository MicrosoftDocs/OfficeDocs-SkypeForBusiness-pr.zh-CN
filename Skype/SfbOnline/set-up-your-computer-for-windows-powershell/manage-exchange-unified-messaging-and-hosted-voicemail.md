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
description: 在 Skype for business Online 中使用 PowerShell 管理 Exchange 统一消息功能，例如自动助理和订阅者访问以及托管语音邮件。
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692677"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="4853f-103">管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="4853f-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="4853f-104">通过使用一组 cmdlet，可以在 Skype for business Online 中管理 Exchange 统一消息和托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="4853f-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="4853f-105">管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="4853f-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="4853f-106">以下 cmdlet 可用于管理 Exchange 统一消息（UM）和托管语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="4853f-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  

| <span data-ttu-id="4853f-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="4853f-107">**Cmdlet**</span></span>                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="4853f-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="4853f-108">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="4853f-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4853f-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="4853f-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4853f-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="4853f-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4853f-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="4853f-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="4853f-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | <span data-ttu-id="4853f-113">当 Exchange UM 是托管服务时，创建和管理用于自动助理和订阅者访问服务的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="4853f-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="4853f-114">Skype for business Online 适用于 Exchange UM，可提供多个与语音相关的功能，包括自动助理和订阅者访问。</span><span class="sxs-lookup"><span data-stu-id="4853f-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="4853f-115">自动助理提供了一种自动应答和路由到正确人员的通话方式。</span><span class="sxs-lookup"><span data-stu-id="4853f-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="4853f-116">订阅者访问使用户能够连接到 Exchange UM 并检索电子邮件、语音消息、联系人和日历信息。</span><span class="sxs-lookup"><span data-stu-id="4853f-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="4853f-117">当 Exchange UM 作为托管服务提供时，必须使用 Microsoft PowerShell 创建用于自动助理和订阅者访问服务的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="4853f-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="4853f-118">通过使用**CsExUmContact** cmdlet 创建和管理这些对象。</span><span class="sxs-lookup"><span data-stu-id="4853f-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
| [<span data-ttu-id="4853f-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4853f-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="4853f-120">Grant-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4853f-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | <span data-ttu-id="4853f-121">管理组织中使用的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="4853f-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="4853f-122">托管语音邮件策略指定如何将未应答的呼叫路由到 Exchange UM 服务。</span><span class="sxs-lookup"><span data-stu-id="4853f-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="4853f-123">这些策略仅影响已启用 Exchange UM 托管语音邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="4853f-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="4853f-124">若要验证用户是否已启用托管语音邮件，请从 PowerShell 提示符运行类似以下内容的命令。</span><span class="sxs-lookup"><span data-stu-id="4853f-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="4853f-125">\`CsOnlineUser-Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="4853f-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span>                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a><span data-ttu-id="4853f-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="4853f-126">Related topics</span></span>
[<span data-ttu-id="4853f-127">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="4853f-127">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
