---
title: Microsoft Teams 安全指南
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 在工作场所共享计算机上使用 Microsoft Teams 的安全指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117050"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="26c91-103">在共享计算机上安全使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26c91-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="26c91-104">对任何使用设备管理功能、设备运行状况检查、策略执行、设备级加密及其他安全功能的客户端设备，*建议* 企业尽可能采用零信任方案。</span><span class="sxs-lookup"><span data-stu-id="26c91-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="零信任图片蓝色圆圈中，分别显示的是显式验证、最少特权，还有假定泄露（即零信任的核心原则）。":::

<span data-ttu-id="26c91-106">管理员可通过 *始终* 验证、最少特权和假设泄露来创建严格的安全条件（执行这些标准可将用户和数据面临的风险降到最低）。</span><span class="sxs-lookup"><span data-stu-id="26c91-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="26c91-107">要深入了解零信任原则，请查看[这些视频](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)。</span><span class="sxs-lookup"><span data-stu-id="26c91-107">For a deeper examination of Zero Trust principles, see [these videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="26c91-108">在共享计算机上安全使用 Microsoft Teams 的提示</span><span class="sxs-lookup"><span data-stu-id="26c91-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="26c91-109">尽管在某些场景中可能无法执行，但安全管理员在共享计算机或非托管设备上使用 Teams 时，仍应尽量严格按照指南进行操作。</span><span class="sxs-lookup"><span data-stu-id="26c91-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="26c91-110">应尽快根据指南制定计划。</span><span class="sxs-lookup"><span data-stu-id="26c91-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="26c91-111">利用操作系统平台的安全功能。</span><span class="sxs-lookup"><span data-stu-id="26c91-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="26c91-112">确保操作系统已配置为自动安装来自操作系统提供商的更新（ Microsoft 系统可通过 [**Windows 更新**](https://support.microsoft.com/help/12373/windows-update-faq)进行设置）。</span><span class="sxs-lookup"><span data-stu-id="26c91-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    1. <span data-ttu-id="26c91-113">确保已启用设备加密功能，如 [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) 等，并确保访问设备的密匙也受到保护。</span><span class="sxs-lookup"><span data-stu-id="26c91-113">Ensure that any device encryption capabilities such as [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="26c91-114">请注意，大多数新式 [**Windows 10 设备支持 bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="26c91-114">Note that most modern [**Windows 10 devices support bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="26c91-115">使用 [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 等提供的防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="26c91-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="26c91-116">强烈建议每个用户用[单独的用户帐户](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)使用同一系统。</span><span class="sxs-lookup"><span data-stu-id="26c91-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="26c91-117">*不要* 对非管理功能授予或使用管理员特权（例如浏览网页、启动 Teams 等）。</span><span class="sxs-lookup"><span data-stu-id="26c91-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

<span data-ttu-id="26c91-118">如果无法满足上述指南要求，我们建议使用其他浏览器安全最佳方案：</span><span class="sxs-lookup"><span data-stu-id="26c91-118">If the above guidance cannot be met, we recommend making use of additional browser security best practices:</span></span>

1. <span data-ttu-id="26c91-119">利用浏览器的安全功能。</span><span class="sxs-lookup"><span data-stu-id="26c91-119">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="26c91-120">启用隐私浏览模式，尽量减少保留在磁盘上的数据与历史记录。</span><span class="sxs-lookup"><span data-stu-id="26c91-120">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="26c91-121">例如，[在 Microsoft Edge 中以 inPrivate 模式进行浏览](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)， [在Google Chrome 中以无痕模式进行浏览](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)，或使用其他浏览器的隐私浏览功能。</span><span class="sxs-lookup"><span data-stu-id="26c91-121">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="26c91-122">建议将系统行为设置为 *默认使用* 隐私浏览模式。</span><span class="sxs-lookup"><span data-stu-id="26c91-122">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

2. <span data-ttu-id="26c91-123">浏览到并使用 [Teams web 应用](https://teams.microsoft.com) （或称为 *web* 客户端），而不用可下载的 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="26c91-123">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

3. <span data-ttu-id="26c91-124">使用完共享系统后，您必须：</span><span class="sxs-lookup"><span data-stu-id="26c91-124">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="26c91-125">[注销 Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。</span><span class="sxs-lookup"><span data-stu-id="26c91-125">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="26c91-126">关闭所有浏览器选项卡和窗口。</span><span class="sxs-lookup"><span data-stu-id="26c91-126">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="26c91-127">注销此设备。</span><span class="sxs-lookup"><span data-stu-id="26c91-127">Sign out of the device.</span></span>

<span data-ttu-id="26c91-128">上述建议不涵盖所有情况下的最佳实践或安全控制方案，不同环境中您也可能采取其他措施，（例如，如果您购买了 [Office 365 ATP 计划 1 或 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) ，安全管理员可能会选择使用 Teams 中的安全链接或安全附件）。</span><span class="sxs-lookup"><span data-stu-id="26c91-128">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="26c91-129">但这些步骤仍可帮助您开始创建在共享设备上使用 Teams 的安全指南。</span><span class="sxs-lookup"><span data-stu-id="26c91-129">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="26c91-130">详细信息</span><span class="sxs-lookup"><span data-stu-id="26c91-130">More Information</span></span>

[<span data-ttu-id="26c91-131">Configuration Manager 中的 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="26c91-131">Bitlocker in Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="26c91-132">Windows 10 in Intune 版 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="26c91-132">Bitlocker for Windows 10 in Intune</span></span>](/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="26c91-133">Intune 端点安全性</span><span class="sxs-lookup"><span data-stu-id="26c91-133">Endpoint security in Intune</span></span>](/mem/intune/protect/endpoint-security)

<span data-ttu-id="26c91-134">在 Windows 安全中心[启用](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender 防病毒并[运行扫描](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="26c91-134">[Enable](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="26c91-135">Microsoft Defender 安全中心文章</span><span class="sxs-lookup"><span data-stu-id="26c91-135">Microsoft Defender security center article</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="26c91-136">Teams web 客户端/teams web 应用</span><span class="sxs-lookup"><span data-stu-id="26c91-136">Teams web client/teams web app</span></span>](./get-clients.md#web-client)

[<span data-ttu-id="26c91-137">安全性与 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26c91-137">Security and Microsoft Teams</span></span>](./teams-security-guide.md)