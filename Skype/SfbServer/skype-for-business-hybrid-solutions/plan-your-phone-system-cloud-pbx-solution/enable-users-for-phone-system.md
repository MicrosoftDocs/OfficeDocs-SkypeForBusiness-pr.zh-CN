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
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359138"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="63bac-104">在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户</span><span class="sxs-lookup"><span data-stu-id="63bac-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="63bac-105">本主题介绍如何为使用本地 PSTN 连接的电话系统启用用户。</span><span class="sxs-lookup"><span data-stu-id="63bac-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="63bac-106">在执行本主题中的步骤之前，您应阅读以下内容：。</span><span class="sxs-lookup"><span data-stu-id="63bac-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="63bac-107">若要了解如何设置混合连接，请参阅 [规划 skype For Business server 和 skype for Business online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) ，以及 [在 Skype for Business server 和 Skype for Business online 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="63bac-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="63bac-108">若要了解如何规划部署，请参阅在 [Skype For Business Server 中规划具有本地 PSTN 连接的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="63bac-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="63bac-109">若要了解有关电话系统的详细信息（包括许可和计划），请参阅 [适用于 Skype For business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="63bac-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="63bac-110">Skype for Business Online 将于2021年7月31日终止，之后服务将无法再访问。</span><span class="sxs-lookup"><span data-stu-id="63bac-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="63bac-111">此外，在本地环境中是否通过 Skype for Business Server 或云连接器版本以及 Skype for Business Online 的 PSTN 连接将不再受支持。</span><span class="sxs-lookup"><span data-stu-id="63bac-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="63bac-112">了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。</span><span class="sxs-lookup"><span data-stu-id="63bac-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="63bac-113">将用户移动到具有本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="63bac-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="63bac-114">在将用户迁移到 Skype for business Online 之前，建议您在 Skype for Business Server 或 Lync Server 2013 中的本地启用用户，然后将其联机移动。</span><span class="sxs-lookup"><span data-stu-id="63bac-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="63bac-115">有关详细信息，请参阅 [规划 skype For Business Server 和 skype for Business Online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) ，以及在用户托管本地) 时，" [启用企业语音的用户](enable-the-users-for-enterprise-voice-on-premises.md) " (执行的特殊注意事项部分。</span><span class="sxs-lookup"><span data-stu-id="63bac-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="63bac-116">所有用户都必须在本地 Active Directory 中创建，并使用受支持的 Azure AD 连接器版本同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="63bac-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="63bac-117">您无法在 Office 365 中为直接在 Azure AD 中创建的 Office 中的用户启用电话系统。</span><span class="sxs-lookup"><span data-stu-id="63bac-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="63bac-118">如果要为在 Azure AD 中创建的用户启用具有本地 PSTN 连接的电话系统，你需要在本地 AD 中为该用户创建一个新帐户，在本地配置帐户，然后使用受支持的 Azure AD 连接器工具版本同步该帐户。</span><span class="sxs-lookup"><span data-stu-id="63bac-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="63bac-119">为具有本地 PSTN 连接的电话系统启用用户，然后将其移动到 Skype for Business Online 需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63bac-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="63bac-120">在用户托管本地) 的情况下[，为用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md) (执行的用户。</span><span class="sxs-lookup"><span data-stu-id="63bac-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="63bac-121">分配在用户托管本地) 时执行[的语音路由策略](assign-a-voice-routing-policy.md) (。</span><span class="sxs-lookup"><span data-stu-id="63bac-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="63bac-122">[将用户同步到云并分配](synchronize-users-to-the-cloud-and-assign-licenses.md) (使用 Office 365) 执行的许可证。</span><span class="sxs-lookup"><span data-stu-id="63bac-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="63bac-123">[将本地用户迁移到 Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (使用本地 Windows PowerShell 执行，但使用 Office 365 管理员凭据) 。</span><span class="sxs-lookup"><span data-stu-id="63bac-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="63bac-124">使用远程 PowerShell[为用户启用企业语音在线和电话系统语音邮件](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (执行。</span><span class="sxs-lookup"><span data-stu-id="63bac-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

