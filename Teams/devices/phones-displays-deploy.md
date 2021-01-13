---
title: 使用 Intune 部署 Teams 手机和 Teams 显示
ms.author: v-cichur
author: cichur
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
description: 本文概述了 Microsoft Teams 显示器支持的功能。
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825412"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="65c57-103">使用 Intune 部署 Teams 手机和 Teams 显示</span><span class="sxs-lookup"><span data-stu-id="65c57-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="65c57-104">本文概述了如何使用 Intune 部署 Teams 手机和 Teams 显示。</span><span class="sxs-lookup"><span data-stu-id="65c57-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="65c57-105">条件访问</span><span class="sxs-lookup"><span data-stu-id="65c57-105">Conditional Access</span></span>

<span data-ttu-id="65c57-106">条件访问是 Azure AD (Azure Active Directory) 功能，可帮助确保正确管理访问 Office 365 资源的设备并确保其安全。</span><span class="sxs-lookup"><span data-stu-id="65c57-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="65c57-107">如果将条件访问策略应用到 Teams 服务，则 Android 设备 (包括 Teams 手机和 Teams) 将显示需要将 Teams 注册到 Intune 中并且其设置需要符合策略的组。</span><span class="sxs-lookup"><span data-stu-id="65c57-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="65c57-108">如果设备未注册到 Intune，或者设备已注册，但其设置不符合策略，则条件访问将阻止用户登录或使用该设备上 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="65c57-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="65c57-109">通常，在 Intune 中定义的符合性策略将分配给用户组。</span><span class="sxs-lookup"><span data-stu-id="65c57-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="65c57-110">这意味着，如果将 Android 符合性策略分配给 user@contoso.com，该策略将同样适用于其 Android 智能手机以及任何登录user@contoso.com Android 的 Teams 设备。</span><span class="sxs-lookup"><span data-stu-id="65c57-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="65c57-111">如果使用需要强制实施 Intune 注册的条件性访问，则需要在组织中设置一些操作，以便成功进行 Intune 注册：</span><span class="sxs-lookup"><span data-stu-id="65c57-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="65c57-112">**Intune 许可证** 登录 Teams 设备的用户必须获得 Intune 许可。</span><span class="sxs-lookup"><span data-stu-id="65c57-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="65c57-113">只要 Teams 设备登录到具有有效 Intune 许可证的用户帐户，该设备就会在登录过程中自动注册到 Microsoft Intune 中。</span><span class="sxs-lookup"><span data-stu-id="65c57-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="65c57-114">**配置 Intune** 必须为 Android 设备管理员注册设置正确配置的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="65c57-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="65c57-115">配置 Intune 以注册基于 Teams Android 的设备</span><span class="sxs-lookup"><span data-stu-id="65c57-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="65c57-116">基于 Teams Android 的设备在 Intune 中通过 Android 设备管理员和 DA () 进行管理。</span><span class="sxs-lookup"><span data-stu-id="65c57-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="65c57-117">在将设备注册到 Intune 之前，需要执行几个基本步骤。</span><span class="sxs-lookup"><span data-stu-id="65c57-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="65c57-118">如果当前已在使用 Intune 管理设备，则很可能已完成所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="65c57-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="65c57-119">如果没有，下面是要执行哪些工作：</span><span class="sxs-lookup"><span data-stu-id="65c57-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="65c57-120">将 Intune MDM (移动设备管理) 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="65c57-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="65c57-121">如果以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。</span><span class="sxs-lookup"><span data-stu-id="65c57-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="65c57-122">有关详细信息，请参阅"[设置移动设备管理机构"。](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="65c57-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="65c57-123">这是一个一次步骤，在创建新的 Intune 租户时必须完成。</span><span class="sxs-lookup"><span data-stu-id="65c57-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="65c57-124">启用 Android 设备管理员注册。</span><span class="sxs-lookup"><span data-stu-id="65c57-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="65c57-125">使用 Intune 将基于 Android 的 Teams 设备作为设备管理员设备进行管理。</span><span class="sxs-lookup"><span data-stu-id="65c57-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="65c57-126">默认情况下，对于新创建的租户，设备管理员注册已关闭。</span><span class="sxs-lookup"><span data-stu-id="65c57-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="65c57-127">有关详细信息，请参阅 [Android 设备管理员注册](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="65c57-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="65c57-128">向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="65c57-128">Assign licenses to users.</span></span> <span data-ttu-id="65c57-129">必须为注册到 Intune 的 Teams 设备的用户分配有效的 Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="65c57-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="65c57-130">有关详细信息，请参阅["向用户分配许可证，以便他们可以在 Intune 中注册设备"。](https://docs.microsoft.com/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="65c57-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="65c57-131">分配设备管理员符合性策略。</span><span class="sxs-lookup"><span data-stu-id="65c57-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="65c57-132">创建 Android 设备管理员符合性策略，并将其分配给包含将登录 Teams 设备的用户的 Azure Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="65c57-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="65c57-133">有关详细信息，请参阅 ["使用符合性策略"为使用 Intune 管理的设备设置规则](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="65c57-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="65c57-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65c57-134">See also</span></span>

[<span data-ttu-id="65c57-135">Teams 电话</span><span class="sxs-lookup"><span data-stu-id="65c57-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="65c57-136">Microsoft Teams 认证的 IP 电话</span><span class="sxs-lookup"><span data-stu-id="65c57-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="65c57-137">Teams 显示</span><span class="sxs-lookup"><span data-stu-id="65c57-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="65c57-138">在 Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="65c57-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="65c57-139">Teams 市场</span><span class="sxs-lookup"><span data-stu-id="65c57-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
