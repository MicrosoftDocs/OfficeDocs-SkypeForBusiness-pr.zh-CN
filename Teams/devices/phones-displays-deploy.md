---
title: 部署团队使用 Intune 显示的电话和团队
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文提供 Microsoft 团队显示所支持的和功能的概述。
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787607"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="366fa-103">部署团队使用 Intune 显示的电话和团队</span><span class="sxs-lookup"><span data-stu-id="366fa-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="366fa-104">本文简要介绍了如何使用 Intune 部署团队电话和团队。</span><span class="sxs-lookup"><span data-stu-id="366fa-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="366fa-105">条件访问</span><span class="sxs-lookup"><span data-stu-id="366fa-105">Conditional Access</span></span>

<span data-ttu-id="366fa-106">条件访问是 Azure Active Directory (Azure AD) 功能，可帮助你确保访问 Office 365 资源的设备正确管理且安全。</span><span class="sxs-lookup"><span data-stu-id="366fa-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="366fa-107">如果你将条件访问策略应用到团队服务，Android 设备 (包括团队电话和团队显示访问团队需要注册到 Intune 的) ，其设置需要符合你的策略。</span><span class="sxs-lookup"><span data-stu-id="366fa-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="366fa-108">如果设备未注册到 Intune，或者它已注册，但其设置不符合你的策略，则条件访问将阻止用户登录或使用设备上的 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="366fa-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="366fa-109">通常，在 Intune 中定义的合规性策略将分配给用户组。</span><span class="sxs-lookup"><span data-stu-id="366fa-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="366fa-110">这意味着，如果你将 Android 合规性策略分配给 user@contoso.com，该策略将同等地应用于其 Android 智能手机和 user@contoso.com 登录的任何基于 Android 的团队设备。</span><span class="sxs-lookup"><span data-stu-id="366fa-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="366fa-111">如果使用条件访问（需要强制执行 Intune 注册），则需要设置以下几项才能允许成功完成 Intune 注册：</span><span class="sxs-lookup"><span data-stu-id="366fa-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="366fa-112">**Intune 许可证** 登录到团队设备的用户必须获得 Intune 许可。</span><span class="sxs-lookup"><span data-stu-id="366fa-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="366fa-113">只要团队设备登录到具有有效 Intune 许可证的用户帐户，该设备将在登录过程中自动注册到 Microsoft Intune 中。</span><span class="sxs-lookup"><span data-stu-id="366fa-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="366fa-114">**配置 Intune** 你必须为 Android 设备管理员注册设置正确配置的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="366fa-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="366fa-115">将 Intune 配置为基于 Android 的设备注册团队</span><span class="sxs-lookup"><span data-stu-id="366fa-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="366fa-116">基于 Android 的团队设备通过 Android 设备管理员 (DA) 管理在 Intune 中管理。</span><span class="sxs-lookup"><span data-stu-id="366fa-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="366fa-117">在设备可以注册到 Intune 之前，需要执行一些基本步骤。</span><span class="sxs-lookup"><span data-stu-id="366fa-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="366fa-118">如果你现在已使用 Intune 管理设备，你可能已经完成了所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="366fa-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="366fa-119">如果不是，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="366fa-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="366fa-120">将 Intune MDM (移动设备管理) 机构。</span><span class="sxs-lookup"><span data-stu-id="366fa-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="366fa-121">如果你以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。</span><span class="sxs-lookup"><span data-stu-id="366fa-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="366fa-122">有关详细信息，请参阅 [设置移动设备管理机构](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="366fa-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="366fa-123">这是在创建新的 Intune 租户时必须执行的一次性步骤。</span><span class="sxs-lookup"><span data-stu-id="366fa-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="366fa-124">启用 Android 设备管理员注册。</span><span class="sxs-lookup"><span data-stu-id="366fa-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="366fa-125">基于 Android 的团队设备通过 Intune 作为设备管理员设备进行管理。</span><span class="sxs-lookup"><span data-stu-id="366fa-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="366fa-126">默认情况下，对于新创建的租户，设备管理员注册处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="366fa-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="366fa-127">有关详细信息，请参阅 [Android 设备管理员注册](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="366fa-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="366fa-128">为用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="366fa-128">Assign licenses to users.</span></span> <span data-ttu-id="366fa-129">必须为要注册到 Intune 的团队设备用户分配一个有效的 Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="366fa-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="366fa-130">有关详细信息，请参阅 [为用户分配许可证，以便他们可以在 Intune 中注册设备](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="366fa-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="366fa-131">分配设备管理员合规性策略。</span><span class="sxs-lookup"><span data-stu-id="366fa-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="366fa-132">创建一个 Android 设备管理员合规性策略，并将其分配给 Azure Active Directory 组，其中包含将登录到团队设备的用户。</span><span class="sxs-lookup"><span data-stu-id="366fa-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="366fa-133">有关详细信息，请参阅 [使用合规性策略为使用 Intune 管理的设备设置规则](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="366fa-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="366fa-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="366fa-134">See also</span></span>

[<span data-ttu-id="366fa-135">Teams 电话</span><span class="sxs-lookup"><span data-stu-id="366fa-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="366fa-136">适用于 Microsoft 团队的 IP 手机认证</span><span class="sxs-lookup"><span data-stu-id="366fa-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="366fa-137">团队显示</span><span class="sxs-lookup"><span data-stu-id="366fa-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="366fa-138">在 Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="366fa-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="366fa-139">团队市场</span><span class="sxs-lookup"><span data-stu-id="366fa-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
