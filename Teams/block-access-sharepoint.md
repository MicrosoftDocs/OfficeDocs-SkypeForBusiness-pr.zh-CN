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
ms.openlocfilehash: e3cda9d6443c41abc7dfa736be03555690a3b0f1
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615078"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="83a84-103">阻止特定用户对 SharePoint 的访问</span><span class="sxs-lookup"><span data-stu-id="83a84-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="83a84-104">在 Microsoft 365 中对 SharePoint 应用任何条件访问 (CA) 策略也会应用到 Teams。</span><span class="sxs-lookup"><span data-stu-id="83a84-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="83a84-105">但是，有些组织希望阻止对 SharePoint 文件的访问（上载、下载、查看、编辑、创建），但允许其员工在非托管设备上使用Teams 桌面、移动设备和 web 客户端。</span><span class="sxs-lookup"><span data-stu-id="83a84-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="83a84-106">根据 CA 策略规则，阻止 SharePoint 将会导致阻止 Teams。</span><span class="sxs-lookup"><span data-stu-id="83a84-106">Under the CA policy rules, blocking SharePoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="83a84-107">本文将解释如何克服这一限制，允许员工继续使用 Teams，同时完全阻止对存储在 SharePoint 中的文件的访问。</span><span class="sxs-lookup"><span data-stu-id="83a84-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="83a84-108">阻止或限制对非托管设备的访问取决于 Azure AD 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="83a84-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="83a84-109">了解 [Azure AD 许可](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="83a84-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="83a84-110">有关 Azure AD 中条件访问的概述，请参阅 [Azure Active Directory 中的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="83a84-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="83a84-111">有关推荐的 SharePoint Online 访问策略的信息，请参阅 [用于保护 SharePoint 网站和文件的策略建议](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="83a84-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="83a84-112">如果限制非托管设备上的访问，则托管设备上的用户必须使用其中一个[受支持的操作系统和浏览器组合](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)，否则他们的访问权限也将受到限制。</span><span class="sxs-lookup"><span data-stu-id="83a84-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="83a84-113">可以阻止或限制对以下内容的访问：</span><span class="sxs-lookup"><span data-stu-id="83a84-113">You can block or limit access for:</span></span>

- <span data-ttu-id="83a84-114">组织中的用户，或仅部分用户或安全组。</span><span class="sxs-lookup"><span data-stu-id="83a84-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="83a84-115">组织中的所有网站，或仅部分网站。</span><span class="sxs-lookup"><span data-stu-id="83a84-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="83a84-116">访问被阻止时，用户将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="83a84-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="83a84-117">阻止访问有助于提供安全性并保护安全数据。</span><span class="sxs-lookup"><span data-stu-id="83a84-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="83a84-118">访问被阻止时，用户将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="83a84-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="83a84-119">打开 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="83a84-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="83a84-120">展开“**策略**” > “**访问策略**”。</span><span class="sxs-lookup"><span data-stu-id="83a84-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="83a84-121">在“**非托管设备**”部分，选择 **“阻止访问**”，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="83a84-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![策略的“未托管设备”部分](media/no-sharepoint-access1.png)

4. <span data-ttu-id="83a84-123">打开 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 门户并导航到 **条件访问策略**。</span><span class="sxs-lookup"><span data-stu-id="83a84-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="83a84-124">您将看到 SharePoint 创建了新策略，与此示例类似：</span><span class="sxs-lookup"><span data-stu-id="83a84-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![名为“使用应用程序强制限制浏览器访问”的新策略](media/no-sharepoint-access2.png)

5. <span data-ttu-id="83a84-126">更新策略以仅针对特定用户或组。</span><span class="sxs-lookup"><span data-stu-id="83a84-126">Update the policy to target only specific users or a group.</span></span>

    ![突出显示“选择用户”部分的 SharePoint 管理中心。](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="83a84-128">设置此策略将切断您对 SharePoint 管理门户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="83a84-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="83a84-129">我们建议您配置排除策略并选择全局管理员和 SharePoint 管理员。</span><span class="sxs-lookup"><span data-stu-id="83a84-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="83a84-130">验证是否仅选择 SharePoint 作为目标云应用</span><span class="sxs-lookup"><span data-stu-id="83a84-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![选择 Sharepoint 作为目标应用程序。](media/no-sharepoint-access3.png)

7. <span data-ttu-id="83a84-132">更新 **条件** 以包括桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="83a84-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![桌面和移动应用突出显示。](media/no-sharepoint-access4.png)

8. <span data-ttu-id="83a84-134">确保已启用 **授予访问权限**</span><span class="sxs-lookup"><span data-stu-id="83a84-134">Make sure that **Grant access** is enabled</span></span>

    ![已启用授予访问权限。](media/no-sharepoint-access5.png)

9. <span data-ttu-id="83a84-136">请确保已启用“**使用应用强制限制**”。</span><span class="sxs-lookup"><span data-stu-id="83a84-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="83a84-137">启用策略并选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="83a84-137">Enable your policy and select **Save**.</span></span>

    ![已启用应用强制限制。](media/no-sharepoint-access6.png)

<span data-ttu-id="83a84-139">若要测试您的策略，您需要从任何客户端（如 Teams 桌面应用程序或 OneDrive for Business 同步客户端）注销，然后重新登录以查看策略是否有效。</span><span class="sxs-lookup"><span data-stu-id="83a84-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="83a84-140">如果你的访问已被阻止，你将在 Teams 中看到指出该项目可能不存在的消息。</span><span class="sxs-lookup"><span data-stu-id="83a84-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![“找不到项”消息。](media/access-denied-sharepoint.png)

<span data-ttu-id="83a84-142">在 Sharepoint 中，您将收到拒绝访问的消息。</span><span class="sxs-lookup"><span data-stu-id="83a84-142">In SharePoint, you'll receive an access denied message.</span></span>

![拒绝访问消息。](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="83a84-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="83a84-144">Related topics</span></span>

[<span data-ttu-id="83a84-145">在 SharePoint 中控制对非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="83a84-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
