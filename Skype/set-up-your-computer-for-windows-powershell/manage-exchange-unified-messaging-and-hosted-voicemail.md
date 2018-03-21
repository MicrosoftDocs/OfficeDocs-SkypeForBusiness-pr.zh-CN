---
title: "管理 Exchange 统一消息和承载语音邮件"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "使用 PowerShell 的在线业务管理 Exchange 统一消息功能，如自动助理和订阅者访问并在 Skype 的承载语音邮件。"
ms.openlocfilehash: 98a7847f6d8ec5bebd1889aef57298bd36696918
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="cfbc8-103">管理 Exchange 统一消息和承载语音邮件</span><span class="sxs-lookup"><span data-stu-id="cfbc8-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="cfbc8-104">您可以管理 Exchange 统一消息并使用 cmdlet 一套在线业务承载在 Skype 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="cfbc8-105">管理 Exchange 统一消息和承载语音邮件</span><span class="sxs-lookup"><span data-stu-id="cfbc8-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="cfbc8-106">以下 cmdlet 可以用于管理 Exchange 统一消息 (UM) 和承载语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="cfbc8-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="cfbc8-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cfbc8-107">**Cmdlet**</span></span>|<span data-ttu-id="cfbc8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cfbc8-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cfbc8-109">获得 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cfbc8-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="cfbc8-110">新 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cfbc8-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="cfbc8-111">删除 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cfbc8-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="cfbc8-112">一组 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="cfbc8-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="cfbc8-113">创建和管理用于自动助理和订阅服务器上访问服务时 UM Exchange 托管的服务的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="cfbc8-114">Skype 的在线业务工作与 UM Exchange 提供几个与语音相关的功能，包括自动助理和订阅者访问。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="cfbc8-115">自动助理提供一种电话自动回答和传送给正确的人。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="cfbc8-116">订阅服务器访问权限允许用户连接到 UM 交换和检索电子邮件、 语音邮件、 联系人和日历信息。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="cfbc8-117">UM Exchange 作为托管服务提供，必须通过使用 Microsoft PowerShell 创建联系人对象用于自动助理和订阅者访问服务。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="cfbc8-118">这些对象的创建和管理使用**CsExUmContact** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="cfbc8-119">获得 CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cfbc8-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="cfbc8-120">授予 CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cfbc8-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="cfbc8-121">管理在组织中使用的承载语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="cfbc8-122">承载语音邮件策略可以指定如何无人应答的呼叫被路由到交换 UM 服务。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="cfbc8-123">这些策略会影响只有已启用 Exchange UM 承载语音邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="cfbc8-124">要验证是否为用户启用了承载语音邮件，请运行与以下内容类似 PowerShell 提示符下的命令。</span><span class="sxs-lookup"><span data-stu-id="cfbc8-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="cfbc8-125">获得 CsOnlineUser-标识"kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="cfbc8-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="cfbc8-126">选择对象 HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="cfbc8-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="cfbc8-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="cfbc8-127">Related topics</span></span>
[<span data-ttu-id="cfbc8-128">设置计算机上的 Skype 业务在线管理使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfbc8-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)