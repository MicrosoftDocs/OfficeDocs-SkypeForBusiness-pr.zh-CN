---
title: 设置Microsoft 365 商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何在中小型企业Microsoft 365 商务语音中设置服务。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534005df5161a69fd64ac94c444046508b9d7fd1
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130359"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="f459d-103">设置Microsoft 365 商务语音</span><span class="sxs-lookup"><span data-stu-id="f459d-103">Set up Microsoft 365 Business Voice</span></span>

<span data-ttu-id="f459d-104">Business Voice 是一个完整的电话系统，可以取代现有的电话提供商。</span><span class="sxs-lookup"><span data-stu-id="f459d-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="f459d-105">无论您是第一次设置电话号码的新企业，还是从旧版本地电话提供商发展的业务，这些文章中的步骤都可以帮助你启动并运行 Business Voice。</span><span class="sxs-lookup"><span data-stu-id="f459d-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="f459d-106">完成 Business Voice 设置后：</span><span class="sxs-lookup"><span data-stu-id="f459d-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="f459d-107">你将能够接听主要公司电话线路上的收费或免费电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="f459d-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="f459d-108">您甚至可以设置呼叫菜单（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="f459d-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="f459d-109">使用 Business Voice 进行设置的用户将具有其自己的直接拨号电话号码，他们可以使用这些号码从任何安装了语音Teams呼叫。</span><span class="sxs-lookup"><span data-stu-id="f459d-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="f459d-110">如果会议参与者无法从客户端加入会议，他们将能够使用常规电话Teams会议。</span><span class="sxs-lookup"><span data-stu-id="f459d-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="f459d-111">如果你有现有电话号码，那么在将电话号码移动到 Business Voice 后，你将能够继续使用它们。</span><span class="sxs-lookup"><span data-stu-id="f459d-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="f459d-112">如果要了解有关 Business Voice 的更多信息，请查看什么是[Microsoft 365 商务语音？。](whats-business-voice.md)</span><span class="sxs-lookup"><span data-stu-id="f459d-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f459d-113">这些文章中的信息仅适用于具有呼叫计划的 Business **Voice。**</span><span class="sxs-lookup"><span data-stu-id="f459d-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="f459d-114">含通话套餐的商业语音仅在所选国家和地区可用。</span><span class="sxs-lookup"><span data-stu-id="f459d-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="f459d-115">在开始设置业务语音之前，请检查 Business [Voice](country-region-availability.md) 的"国家/地区"和"区域可用性"，以查看你的国家/地区是否支持使用呼叫计划使用 Business Voice。</span><span class="sxs-lookup"><span data-stu-id="f459d-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="f459d-116">如果你的租户所在的国家或地区不支持含通话套餐的商务语音，请查看[从 Microsoft 经销商或合作伙伴处获取帮助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="f459d-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="f459d-117">只有在用户的邮箱位于 Microsoft 365 中时，Microsoft Teams 和商务语音才可用。</span><span class="sxs-lookup"><span data-stu-id="f459d-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="f459d-118">不支持本地 Exchange Server 上的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f459d-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="f459d-119">此设置过程不支持Skype for Business部署。</span><span class="sxs-lookup"><span data-stu-id="f459d-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="f459d-120">如果你有 Skype for Business 混合部署，并且想要设置商务语音，请检查[在组织中设置电话系统](../setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="f459d-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f459d-121">开始之前</span><span class="sxs-lookup"><span data-stu-id="f459d-121">Before you begin</span></span>

<span data-ttu-id="f459d-122">在设置 Business Voice 之前，需要执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="f459d-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="f459d-123">以下任务将确保您的组织已准备好使用 Business Voice。</span><span class="sxs-lookup"><span data-stu-id="f459d-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="f459d-124">**购买商业语音许可证** ，如果要获取免费电话号码或进行远程电话呼叫，请购买通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="f459d-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="f459d-125">有关详细信息，请参阅我需要购买哪些产品以[使用Microsoft 365 商务语音？。](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="f459d-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="f459d-126">**请确保 Internet 连接可以支持 Business Voice。**</span><span class="sxs-lookup"><span data-stu-id="f459d-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="f459d-127">有关详细信息，请参阅检查 [Business Voice 的 Internet 连接](get-ready-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="f459d-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="f459d-128">**在Teams** 设备上设置语音信箱，设置语音邮件问候语，并帮助用户了解Teams。</span><span class="sxs-lookup"><span data-stu-id="f459d-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="f459d-129">有关详细信息，请参阅[如何让用户准备好使用Microsoft 365 商务语音？。](prepare-users.md)</span><span class="sxs-lookup"><span data-stu-id="f459d-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="f459d-130">为组织准备 Business Voice 后，选择"下一步 **：开始设置业务语音"。**</span><span class="sxs-lookup"><span data-stu-id="f459d-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f459d-131">下一步：开始设置 Business Voice</span><span class="sxs-lookup"><span data-stu-id="f459d-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
