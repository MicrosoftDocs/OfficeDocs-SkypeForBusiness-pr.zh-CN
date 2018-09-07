---
title: 管理 Exchange 统一消息和托管语音邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 PowerShell 管理业务 online 的 Exchange 统一消息功能，如自动助理和订阅者访问和 Skype 中的托管语音邮件。
ms.openlocfilehash: 10c1891272a81731c94e5f0f459bb91e532e8387
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849790"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="1eba7-103">管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="1eba7-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="1eba7-104">您可以管理 Exchange 统一消息，并通过使用一组的 cmdlet 来业务 online 承载 Skype 中的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="1eba7-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="1eba7-105">管理 Exchange 统一消息和承载语音邮件</span><span class="sxs-lookup"><span data-stu-id="1eba7-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="1eba7-106">以下 cmdlet 可用于管理 Exchange 统一消息 (UM) 和托管语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="1eba7-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="1eba7-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1eba7-107">**Cmdlet**</span></span>|<span data-ttu-id="1eba7-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1eba7-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1eba7-109">Get-csexumcontact</span><span class="sxs-lookup"><span data-stu-id="1eba7-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="1eba7-110">新 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="1eba7-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="1eba7-111">删除 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="1eba7-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="1eba7-112">Set-csexumcontact</span><span class="sxs-lookup"><span data-stu-id="1eba7-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="1eba7-113">创建和管理 Exchange UM 托管的服务时使用的自动助理和订阅者访问服务的联系对象。</span><span class="sxs-lookup"><span data-stu-id="1eba7-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="1eba7-114">Skype 业务 online 适用于 Exchange UM 以提供多个语音相关的功能，包括自动助理和订阅者访问。</span><span class="sxs-lookup"><span data-stu-id="1eba7-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="1eba7-115">自动助理提供了一种呼叫自动回答和路由至正确的人的方法。</span><span class="sxs-lookup"><span data-stu-id="1eba7-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="1eba7-116">订阅者访问使用户能够连接到 Exchange UM 和检索电子邮件、 语音邮件、 联系人和日历信息。</span><span class="sxs-lookup"><span data-stu-id="1eba7-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="1eba7-117">如果 Exchange UM 作为承载的服务，则必须使用 Microsoft PowerShell 创建自动助理和订阅者访问服务中使用的联系对象。</span><span class="sxs-lookup"><span data-stu-id="1eba7-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="1eba7-118">创建和使用**CsExUmContact** cmdlet 管理这些对象。</span><span class="sxs-lookup"><span data-stu-id="1eba7-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="1eba7-119">Get-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="1eba7-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="1eba7-120">授予 CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1eba7-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="1eba7-121">管理组织中使用的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="1eba7-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="1eba7-122">托管语音邮件策略指定如何未应答的呼叫路由到 Exchange UM 服务。</span><span class="sxs-lookup"><span data-stu-id="1eba7-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="1eba7-123">这些策略影响已启用 Exchange UM 承载语音邮件的唯一用户。</span><span class="sxs-lookup"><span data-stu-id="1eba7-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="1eba7-124">若要验证是否为用户启用承载语音邮件，请运行从 PowerShell 提示符类似于下面的命令。</span><span class="sxs-lookup"><span data-stu-id="1eba7-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="1eba7-125">Get-csonlineuser-Identity"kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="1eba7-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="1eba7-126">选择对象 HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="1eba7-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="1eba7-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="1eba7-127">Related topics</span></span>
[<span data-ttu-id="1eba7-128">设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype</span><span class="sxs-lookup"><span data-stu-id="1eba7-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 