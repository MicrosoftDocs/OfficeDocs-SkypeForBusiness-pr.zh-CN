---
title: 使用 intune Teams手机Teams和显示器
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
description: 本文概述了屏幕屏幕支持的功能Microsoft Teams功能。
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420817"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="4772f-103">使用 intune Teams手机Teams和显示器</span><span class="sxs-lookup"><span data-stu-id="4772f-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="4772f-104">本文概述了如何部署。</span><span class="sxs-lookup"><span data-stu-id="4772f-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="4772f-105">Teams Intune Teams手机和显示器。</span><span class="sxs-lookup"><span data-stu-id="4772f-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="4772f-106">条件访问</span><span class="sxs-lookup"><span data-stu-id="4772f-106">Conditional Access</span></span>

<span data-ttu-id="4772f-107">条件访问Azure Active Directory (Azure AD) 功能，可帮助确保访问资源的设备Office 365管理正确且安全。</span><span class="sxs-lookup"><span data-stu-id="4772f-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="4772f-108">如果将条件访问策略应用到 Teams 服务，则 Android 设备 (（包括 Teams 手机和 Teams）将显示需要将访问 Teams 注册到 Intune 的) ，并且其设置需要符合策略。</span><span class="sxs-lookup"><span data-stu-id="4772f-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="4772f-109">如果设备未注册到 Intune，或者设备已注册，但其设置不符合策略，则条件访问将阻止用户登录或使用该设备上 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="4772f-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="4772f-110">通常，Intune 中定义的符合性策略将分配给用户组。</span><span class="sxs-lookup"><span data-stu-id="4772f-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="4772f-111">这意味着，如果将 Android 符合性策略分配给 user@contoso.com，该策略同样适用于其 Android 智能手机和任何登录Teams Android user@contoso.com 应用。</span><span class="sxs-lookup"><span data-stu-id="4772f-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="4772f-112">如果使用条件访问（要求强制使用 Intune 注册）在组织中，需要设置一些操作，以允许成功进行 Intune 注册：</span><span class="sxs-lookup"><span data-stu-id="4772f-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="4772f-113">**Intune 许可证** 登录设备的用户Teams Intune 许可。</span><span class="sxs-lookup"><span data-stu-id="4772f-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="4772f-114">只要Teams登录到具有有效 Intune 许可证的用户帐户，该设备就会在 Microsoft Intune 中作为登录过程的一部分自动注册。</span><span class="sxs-lookup"><span data-stu-id="4772f-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="4772f-115">**配置 Intune** 必须为 Android 设备管理员注册设置正确配置的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="4772f-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="4772f-116">配置 Intune 以Teams基于 Android 的设备</span><span class="sxs-lookup"><span data-stu-id="4772f-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="4772f-117">Teams基于 Android 的设备由 Intune 通过 Android 设备管理员 (DA) 管理。</span><span class="sxs-lookup"><span data-stu-id="4772f-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="4772f-118">在将设备注册到 Intune 之前，需要执行几个基本步骤。</span><span class="sxs-lookup"><span data-stu-id="4772f-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="4772f-119">如果当前已在使用 Intune 管理设备，可能已完成所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="4772f-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="4772f-120">如果没有，下面是要执行哪些工作：</span><span class="sxs-lookup"><span data-stu-id="4772f-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="4772f-121">如果租户管理员希望将公用区域电话注册到 Intune，则需要将 Intune 许可证添加到帐户，并按照 Intune 注册的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="4772f-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="4772f-122">如果用于登录到 Teams 设备的用户帐户未获得 Intune 的许可，则需要为帐户禁用 Intune 符合性策略和注册限制。</span><span class="sxs-lookup"><span data-stu-id="4772f-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="4772f-123">将 Intune MDM (设置为") 管理"。</span><span class="sxs-lookup"><span data-stu-id="4772f-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="4772f-124">如果以前从未使用过 Intune，则需要先设置 MDM 机构，然后才能注册设备。</span><span class="sxs-lookup"><span data-stu-id="4772f-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="4772f-125">有关详细信息，请参阅 [设置移动设备管理机构](/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="4772f-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="4772f-126">这是一个一步，在创建新的 Intune 租户时必须完成。</span><span class="sxs-lookup"><span data-stu-id="4772f-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="4772f-127">启用 Android 设备管理员注册。</span><span class="sxs-lookup"><span data-stu-id="4772f-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="4772f-128">使用 Intune Teams基于 Android 的设备作为设备管理员设备进行管理。</span><span class="sxs-lookup"><span data-stu-id="4772f-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="4772f-129">默认情况下，对于新建的租户，设备管理员注册已关闭。</span><span class="sxs-lookup"><span data-stu-id="4772f-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="4772f-130">请参阅 [Android 设备管理员注册](/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="4772f-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="4772f-131">向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4772f-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="4772f-132">必须Teams注册到 Intune 的设备的用户分配有效的 Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="4772f-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="4772f-133">有关详细信息，请参阅 [向用户分配许可证，以便他们可以在 Intune 中注册设备](/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="4772f-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="4772f-134">分配设备管理员符合性策略。</span><span class="sxs-lookup"><span data-stu-id="4772f-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="4772f-135">a.</span><span class="sxs-lookup"><span data-stu-id="4772f-135">a.</span></span> <span data-ttu-id="4772f-136">创建 Android 设备管理员符合性策略。</span><span class="sxs-lookup"><span data-stu-id="4772f-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="4772f-137">b.</span><span class="sxs-lookup"><span data-stu-id="4772f-137">b.</span></span> <span data-ttu-id="4772f-138">将其分配给Azure Active Directory用户组，该组包含要登录 Teams设备。</span><span class="sxs-lookup"><span data-stu-id="4772f-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="4772f-139">请参阅 [使用符合性策略为使用 Intune 管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="4772f-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="4772f-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4772f-140">See also</span></span>

[<span data-ttu-id="4772f-141">Teams 电话</span><span class="sxs-lookup"><span data-stu-id="4772f-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="4772f-142">经认证的 IP 电话Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4772f-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="4772f-143">Teams显示器</span><span class="sxs-lookup"><span data-stu-id="4772f-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="4772f-144">在 Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="4772f-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="4772f-145">Teams市场</span><span class="sxs-lookup"><span data-stu-id="4772f-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)