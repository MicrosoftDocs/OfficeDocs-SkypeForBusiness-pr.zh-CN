---
title: 在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何为使用本地 PSTN 连接的电话系统启用用户。 在执行本主题中的步骤之前，您应阅读以下内容：。
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221092"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="ce78e-104">在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户</span><span class="sxs-lookup"><span data-stu-id="ce78e-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="ce78e-105">本主题介绍如何为使用本地 PSTN 连接的电话系统启用用户。</span><span class="sxs-lookup"><span data-stu-id="ce78e-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="ce78e-106">在执行本主题中的步骤之前，您应阅读以下内容：。</span><span class="sxs-lookup"><span data-stu-id="ce78e-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="ce78e-107">若要了解如何设置混合连接，请参阅[规划 skype For Business server 和 skype for Business online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)，以及[在 Skype for Business server 和 Skype for Business online 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="ce78e-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="ce78e-108">若要了解如何规划部署，请参阅在[Skype For Business Server 中规划具有本地 PSTN 连接的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="ce78e-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="ce78e-109">若要了解有关电话系统的详细信息（包括许可和计划），请参阅[适用于 Skype For business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="ce78e-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="ce78e-110">将用户移动到具有本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="ce78e-110">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="ce78e-111">在将用户迁移到 Skype for business Online 之前，建议您在 Skype for Business Server 或 Lync Server 2013 中的本地启用用户，然后将其联机移动。</span><span class="sxs-lookup"><span data-stu-id="ce78e-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="ce78e-112">有关详细信息，请参阅[规划 skype For Business Server 和 skype for Business Online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和为[用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)（在用户托管本地时执行）的特殊注意事项部分。</span><span class="sxs-lookup"><span data-stu-id="ce78e-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="ce78e-113">所有用户都必须在本地 Active Directory 中创建，并使用受支持的 Azure AD 连接器版本同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ce78e-113">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="ce78e-114">您无法在 Office 365 中为直接在 Azure AD 中创建的 Office 中的用户启用电话系统。</span><span class="sxs-lookup"><span data-stu-id="ce78e-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="ce78e-115">如果要为在 Azure AD 中创建的用户启用具有本地 PSTN 连接的电话系统，你需要在本地 AD 中为该用户创建一个新帐户，在本地配置帐户，然后使用受支持的 Azure AD 连接器工具版本同步该帐户。</span><span class="sxs-lookup"><span data-stu-id="ce78e-115">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="ce78e-116">为具有本地 PSTN 连接的电话系统启用用户，然后将其移动到 Skype for Business Online 需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ce78e-116">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="ce78e-117">[为用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)（在用户托管本地时执行）。</span><span class="sxs-lookup"><span data-stu-id="ce78e-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ce78e-118">[分配语音路由策略](assign-a-voice-routing-policy.md)（在用户驻留在本地时执行）。</span><span class="sxs-lookup"><span data-stu-id="ce78e-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ce78e-119">[将用户同步到云并分配许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)（使用 Office 365 执行）。</span><span class="sxs-lookup"><span data-stu-id="ce78e-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="ce78e-120">[将本地用户移动到 Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) （使用本地 Windows PowerShell 执行，但使用 Office 365 管理员凭据）。</span><span class="sxs-lookup"><span data-stu-id="ce78e-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="ce78e-121">[为用户启用企业语音在线和电话系统语音邮件](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（使用远程 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="ce78e-121">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

