---
title: 阻止特定用户对 SharePoint 的访问
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何阻止特定用户对 SharePoint 的访问
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135926"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="c8942-103">阻止特定用户对 SharePoint 的访问</span><span class="sxs-lookup"><span data-stu-id="c8942-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="c8942-104">在 Microsoft 365 中的 SharePoint 上 (CA) 策略应用任何条件访问也将应用于团队。</span><span class="sxs-lookup"><span data-stu-id="c8942-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="c8942-105">但是，某些组织希望阻止对 SharePoint 文件的访问 (上载、下载、查看、编辑、创建) 但允许其员工在非托管设备上使用团队桌面、移动和 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="c8942-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="c8942-106">在 CA 策略规则下，阻止 Sharepoint 也会导致阻止团队。</span><span class="sxs-lookup"><span data-stu-id="c8942-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="c8942-107">本文介绍如何解决此限制，并允许员工在完全阻止访问存储在 SharePoint 中的文件的同时继续使用团队。</span><span class="sxs-lookup"><span data-stu-id="c8942-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="c8942-108">阻止或限制非托管设备上的访问依赖于 Azure AD 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="c8942-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="c8942-109">了解 [AZURE AD 授权](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="c8942-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="c8942-110">有关 Azure AD 中的条件访问的概述，请参阅 [Azure Active Directory 中的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="c8942-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="c8942-111">有关推荐的 SharePoint Online 访问策略的信息，请参阅 [保护 sharepoint 网站和文件的策略建议](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="c8942-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="c8942-112">如果你限制非托管设备上的访问权限，则托管设备上的用户必须使用 [受支持的操作系统和浏览器组合](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)之一，否则它们也将具有有限的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c8942-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="c8942-113">您可以阻止或限制访问：</span><span class="sxs-lookup"><span data-stu-id="c8942-113">You can block or limit access for:</span></span>

- <span data-ttu-id="c8942-114">组织中的用户或仅部分用户或安全组。</span><span class="sxs-lookup"><span data-stu-id="c8942-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="c8942-115">组织中的所有网站或仅部分网站。</span><span class="sxs-lookup"><span data-stu-id="c8942-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="c8942-116">当访问被阻止时，用户将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c8942-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="c8942-117">阻止访问有助于提供安全性和保护安全数据。</span><span class="sxs-lookup"><span data-stu-id="c8942-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="c8942-118">当访问被阻止时，用户将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c8942-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="c8942-119">打开 "SharePoint [管理中心](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)"。</span><span class="sxs-lookup"><span data-stu-id="c8942-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="c8942-120">展开 "**策略**  >  **访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="c8942-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="c8942-121">在 " **非托管设备** " 部分中，选择 " **阻止访问** "，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c8942-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![策略的 "非托管设备" 部分](media/no-sharepoint-access1.png)

4. <span data-ttu-id="c8942-123">打开 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 门户并导航到 " **条件访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="c8942-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="c8942-124">你将看到 SharePoint 创建了一个类似于此示例的新策略：</span><span class="sxs-lookup"><span data-stu-id="c8942-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![新的名为 "使用应用强制的浏览器访问限制" 的策略](media/no-sharepoint-access2.png)

5. <span data-ttu-id="c8942-126">将策略更新为仅面向特定用户或组。</span><span class="sxs-lookup"><span data-stu-id="c8942-126">Update the policy to target only specific users or a group.</span></span>

    ![已突出显示 "选择用户" 部分的 Sharepoint 管理中心。](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="c8942-128">设置此策略将减少你对 SharePoint 管理门户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c8942-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="c8942-129">我们建议你配置排除策略，并选择全局管理员和 SharePoint 管理员。</span><span class="sxs-lookup"><span data-stu-id="c8942-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="c8942-130">验证仅将 SharePoint 选为目标云应用</span><span class="sxs-lookup"><span data-stu-id="c8942-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    !["Sharepoint" 被选作目标应用。](media/no-sharepoint-access3.png)

7. <span data-ttu-id="c8942-132">也可更新 **条件** 以包括桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="c8942-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![桌面和移动应用突出显示。](media/no-sharepoint-access4.png)

8. <span data-ttu-id="c8942-134">确保已启用 " **授权访问** "</span><span class="sxs-lookup"><span data-stu-id="c8942-134">Make sure that **Grant access** is enabled</span></span>

    ![已启用 "授予访问权限"。](media/no-sharepoint-access5.png)

9. <span data-ttu-id="c8942-136">请确保启用 " **使用应用强制实施限制** "。</span><span class="sxs-lookup"><span data-stu-id="c8942-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="c8942-137">启用你的策略，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c8942-137">Enable your policy and select **Save**.</span></span>

    ![应用强制实施限制已启用。](media/no-sharepoint-access6.png)

<span data-ttu-id="c8942-139">若要测试你的策略，你需要从任何客户端（如团队桌面应用或 OneDrive for business 同步客户端）注销，然后再次登录以查看策略是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="c8942-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="c8942-140">如果您的访问已被阻止，则会在团队中看到一条消息，指出该项目可能不存在。</span><span class="sxs-lookup"><span data-stu-id="c8942-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 !["找不到项目" 消息。](media/access-denied-sharepoint.png)

<span data-ttu-id="c8942-142">在 Sharepoint 中，你将收到 "拒绝访问" 消息。</span><span class="sxs-lookup"><span data-stu-id="c8942-142">In Sharepoint, you'll receive an access denied message.</span></span>

!["拒绝访问" 消息。](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="c8942-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="c8942-144">Related topics</span></span>

[<span data-ttu-id="c8942-145">控制 SharePoint 中非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="c8942-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
