---
title: 运算符连接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解操作员连接，例如要求和部署规划。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694537"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="9571e-103">规划操作员连接</span><span class="sxs-lookup"><span data-stu-id="9571e-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="9571e-104">运算符连接目前仅在公共 **预览版中可用**。</span><span class="sxs-lookup"><span data-stu-id="9571e-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="9571e-105">公共预览版允许测试即将推出的功能并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="9571e-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="9571e-106">公共预览版中包含的功能可能不完整，可能发生更改，在云中不受Office 365 政府版支持。</span><span class="sxs-lookup"><span data-stu-id="9571e-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="9571e-107">运营商连接是提供 PSTN 公用电话交换 (PSTN) 连接Teams和电话系统。</span><span class="sxs-lookup"><span data-stu-id="9571e-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="9571e-108">本文介绍权益和要求，并列出参与操作员和连接的操作员。</span><span class="sxs-lookup"><span data-stu-id="9571e-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="9571e-109">如果确定"操作员连接是适合组织的解决方案，阅读本文后，请参阅配置运算符[连接。](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9571e-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="9571e-110">优点</span><span class="sxs-lookup"><span data-stu-id="9571e-110">Benefits</span></span>

<span data-ttu-id="9571e-111">使用接线连接，如果现有运营商是 Microsoft 接线员连接参与者，他们可管理将 PSTN 呼叫引入 Teams。</span><span class="sxs-lookup"><span data-stu-id="9571e-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="9571e-112">操作员连接计划提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="9571e-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="9571e-113">**利用现有合同，或查找新的操作员。**</span><span class="sxs-lookup"><span data-stu-id="9571e-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="9571e-114">保留首选的操作员和合同，或者从一系列参与的运营商中选择一个新的，以满足业务需求。</span><span class="sxs-lookup"><span data-stu-id="9571e-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="9571e-115">**操作员管理的基础结构。**</span><span class="sxs-lookup"><span data-stu-id="9571e-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="9571e-116">运营商管理 PSTN 呼叫服务和会话边界控制器 (SDC) ，从而节省硬件购买和管理费用。</span><span class="sxs-lookup"><span data-stu-id="9571e-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="9571e-117">**更快、更轻松地部署。**</span><span class="sxs-lookup"><span data-stu-id="9571e-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="9571e-118">你可以快速连接到接线员并将电话号码分配给用户 -- 全部Teams管理中心。</span><span class="sxs-lookup"><span data-stu-id="9571e-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="9571e-119">**增强的支持和可靠性。**</span><span class="sxs-lookup"><span data-stu-id="9571e-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="9571e-120">操作员提供技术支持和共享服务级别协议来改善支持服务，而由 Azure 提供支持的直接对等互连则创建一对一网络连接以提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="9571e-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="9571e-121">要求</span><span class="sxs-lookup"><span data-stu-id="9571e-121">Requirements</span></span>

 <span data-ttu-id="9571e-122">如果连接，操作员管理可能是适合组织的解决方案：</span><span class="sxs-lookup"><span data-stu-id="9571e-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="9571e-123">Microsoft 呼叫计划在你的地理位置不可用。</span><span class="sxs-lookup"><span data-stu-id="9571e-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="9571e-124">首选操作员是 Microsoft Operator 连接参与者。</span><span class="sxs-lookup"><span data-stu-id="9571e-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="9571e-125">您希望查找新的接线员，以在 Teams。</span><span class="sxs-lookup"><span data-stu-id="9571e-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="9571e-126">若要使用"接线员"连接电话号码分配，请确保你的用户：</span><span class="sxs-lookup"><span data-stu-id="9571e-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="9571e-127">Teams 电话许可。</span><span class="sxs-lookup"><span data-stu-id="9571e-127">Teams Phone licensed.</span></span> <span data-ttu-id="9571e-128">有关详细信息，请参阅[什么是电话系统？和Teams](what-is-phone-system-in-office-365.md)[向用户分配附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="9571e-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="9571e-129">在 TeamsOnly 模式下。</span><span class="sxs-lookup"><span data-stu-id="9571e-129">In TeamsOnly mode.</span></span> <span data-ttu-id="9571e-130">若要了解有关详细信息，[请参阅了解Microsoft Teams Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="9571e-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="9571e-131">可用运算符</span><span class="sxs-lookup"><span data-stu-id="9571e-131">Available Operators</span></span>

<span data-ttu-id="9571e-132">以下运算符是 Microsoft Operator 连接参与者：</span><span class="sxs-lookup"><span data-stu-id="9571e-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="9571e-133">接线员</span><span class="sxs-lookup"><span data-stu-id="9571e-133">Operator</span></span> | <span data-ttu-id="9571e-134">功能</span><span class="sxs-lookup"><span data-stu-id="9571e-134">Capability</span></span> | <span data-ttu-id="9571e-135">国家/地区覆盖范围</span><span class="sxs-lookup"><span data-stu-id="9571e-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="9571e-136">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-136">Calling</span></span> | <span data-ttu-id="9571e-137">比利时、丹麦、芬兰、法国、德国、爱尔兰、意大利、卢森堡、荷兰、挪威、波兰、南非、西班牙、瑞典、瑞士、英国</span><span class="sxs-lookup"><span data-stu-id="9571e-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="9571e-138">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-138">Calling</span></span> | <span data-ttu-id="9571e-139">比利时、加拿大、丹麦、法国、德国、爱尔兰、卢森堡、荷兰、西班牙、瑞典、英国、美国</span><span class="sxs-lookup"><span data-stu-id="9571e-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="9571e-140">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-140">Calling</span></span> | <span data-ttu-id="9571e-141">奥地利、比利时、巴西、加拿大、捷克、丹麦、芬兰、法国、德国、爱尔兰、意大利、卢森堡、墨西哥、荷兰、挪威、波兰、葡萄牙、波多黎各、罗马尼亚、南非、西班牙、瑞典、瑞士、英国、美国</span><span class="sxs-lookup"><span data-stu-id="9571e-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="9571e-142">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-142">Calling</span></span> | <span data-ttu-id="9571e-143">奥地利、比利时、加拿大、丹麦、法国、德国、爱尔兰、意大利、荷兰、葡萄牙、西班牙、瑞典、瑞士、英国、美国</span><span class="sxs-lookup"><span data-stu-id="9571e-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="9571e-144">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-144">Calling</span></span> | <span data-ttu-id="9571e-145">奥地利、比利时、捷克、丹麦、芬兰、法国、法属 Guiana、德国、瓜德罗普、爱尔兰、意大利、卢森堡、马提克隆、马约特、荷兰、挪威、波兰、葡萄牙、留尼西亚、圣巴塞勒米、圣马丁、西班牙、斯瓦巴德、瑞典、瑞士、英国</span><span class="sxs-lookup"><span data-stu-id="9571e-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="9571e-146">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-146">Calling</span></span> | <span data-ttu-id="9571e-147">澳大利亚、奥地利、比利时、巴西、保加利亚、加拿大、智利、哥伦比亚、克罗地亚、塞浦路斯、捷克、丹麦、芬兰、法国、德国、希腊、香港特别行政区、爱尔兰、意大利、日本、立陶宛、卢森堡、马来西亚、墨西哥、荷兰、新西兰、挪威、秘鲁、波兰、葡萄牙、波多黎各、罗马尼亚、新加坡、斯洛伐克、斯洛文尼亚、南非、西班牙、瑞典、瑞士、英国、美国</span><span class="sxs-lookup"><span data-stu-id="9571e-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="9571e-148">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-148">Calling</span></span> | <span data-ttu-id="9571e-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="9571e-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="9571e-150">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-150">Calling</span></span> | <span data-ttu-id="9571e-151">澳大利亚、奥地利、比利时、加拿大、捷克、丹麦、法国、德国、香港特别行政区、匈牙利、爱尔兰、意大利、马来西亚、墨西哥、荷兰、新西兰、波兰、葡萄牙、罗马尼亚、新加坡、韩国、西班牙、瑞典、瑞士、泰国、英国、美国</span><span class="sxs-lookup"><span data-stu-id="9571e-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="9571e-152">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-152">Calling</span></span> | <span data-ttu-id="9571e-153">德国</span><span class="sxs-lookup"><span data-stu-id="9571e-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="9571e-154">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-154">Calling</span></span> | <span data-ttu-id="9571e-155">丹麦、芬兰、挪威、瑞典</span><span class="sxs-lookup"><span data-stu-id="9571e-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="9571e-156">通话</span><span class="sxs-lookup"><span data-stu-id="9571e-156">Calling</span></span> | <span data-ttu-id="9571e-157">美国</span><span class="sxs-lookup"><span data-stu-id="9571e-157">United States</span></span> |
