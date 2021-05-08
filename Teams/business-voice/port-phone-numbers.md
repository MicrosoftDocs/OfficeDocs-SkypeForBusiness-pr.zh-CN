---
title: 将电话号码转移到商务语音
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何将现有电话号码从当前提供商移动到 Microsoft 365 商务语音。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26f686197963f53f20477ccd9a16935c86a16d9f
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282609"
---
# <a name="step-7-port-phone-numbers-to-business-voice-optional"></a><span data-ttu-id="a1c5d-103">步骤 7：将电话号码端口为业务语音（可选）</span><span class="sxs-lookup"><span data-stu-id="a1c5d-103">Step 7: Port phone numbers to Business Voice (optional)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1c5d-104">本文中的信息仅适用于 **包含** 通话套餐的商务语音。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-104">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="a1c5d-105">含通话套餐的商业语音仅在所选国家和地区可用。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-105">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="a1c5d-106">阅读本文前，请查看[商务语音的国家和地区可用性](country-region-availability.md)，查看你所在的国家或地区是否支持使用包含通话套餐的商务语音。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-106">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="a1c5d-107">如果你的租户所在的国家或地区不支持含通话套餐的商务语音，请查看[从 Microsoft 经销商或合作伙伴处获取帮助](reseller-partner-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-107">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="a1c5d-108">在此设置指南之前，你获取公司主要行和已分配了企业语音许可证的任何用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-108">Earlier in this setup guide, you acquired phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="a1c5d-109">**如果你是新企业，且没有任何想要引入 Business Voice 的现有电话号码，可以跳过此步骤。**</span><span class="sxs-lookup"><span data-stu-id="a1c5d-109">**If you're a new business and don't have any existing phone numbers that you want to bring to Business Voice, you can skip this step.**</span></span>

<span data-ttu-id="a1c5d-110">如果你希望在移动到商务语音时保留已有的电话号码，则可以使用称为“携号转网”的过程将电话号码携转到商务语音。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-110">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="a1c5d-111">将电话号码转到商务语音后，即可将这些号码分配给用户和业务部门。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-111">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="a1c5d-112">旧数字将替换你在此设置指南中早期获取的临时数字。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-112">The old numbers replace the temporary numbers that you acquired earlier in this setup guide.</span></span>

<span data-ttu-id="a1c5d-113">在将号码转到商务语音之前，请查看[转移电话号码常见问题](../phone-number-calling-plans/port-order-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-113">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="a1c5d-114">这篇文章介绍了一些问题的解答，包括受支持的国家和地区、可以转移和无法转移的号码、你需要的信息。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-114">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="a1c5d-115">准备好将电话号码转到商务语音后，请按照[将电话号码转移到 Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 中的步骤创建转网订单。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-115">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="a1c5d-116">该订单包含将号码从当前手机服务运营商转移到商务语音所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-116">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="a1c5d-117">电话号码移动到“商务语音”后，需要将其分配给人员。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-117">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="a1c5d-118">为此，请按照[更改用户的电话号码](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-118">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="a1c5d-119">执行这些步骤时，临时分配给用户的电话号码将替换为你转网过来的原有电话号码。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-119">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="a1c5d-120">如果需要帮助，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="a1c5d-120">If you need help, let us know!</span></span> <span data-ttu-id="a1c5d-121">我们可随时帮助你尽可能轻松地将电话号码移动到商务语音。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-121">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="a1c5d-122">务必包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a1c5d-122">Be sure to include the following information:</span></span>

- <span data-ttu-id="a1c5d-123">你的组织 ID（例如 ***contoso***.onmicrosoft.com）</span><span class="sxs-lookup"><span data-stu-id="a1c5d-123">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="a1c5d-124">需要得到帮助的类型和电话号码数量</span><span class="sxs-lookup"><span data-stu-id="a1c5d-124">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="a1c5d-125">你帐户的授权人</span><span class="sxs-lookup"><span data-stu-id="a1c5d-125">The authorizing person on your account</span></span>
- <span data-ttu-id="a1c5d-126">问题的相关描述</span><span class="sxs-lookup"><span data-stu-id="a1c5d-126">A description of the issue or question that you have</span></span>

<span data-ttu-id="a1c5d-127">有关加拿大和美国电话号码的帮助，请将请求发送到 [ptn@microsoft.com](mailto:ptn@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-127">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="a1c5d-128">有关欧洲电话号码的帮助，请将请求发送到 [ptneu@microsoft.com](mailto:ptneu@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a1c5d-128">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a1c5d-129">下一步：完成业务语音设置</span><span class="sxs-lookup"><span data-stu-id="a1c5d-129">Next step: Finish Business Voice setup</span></span>](set-up-finish.md)
