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
description: 本主题介绍如何为具有本地 PSTN 连接的电话系统启用用户。 在按照本主题中的步骤操作之前，应阅读以下内容：。
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120864"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="0a335-104">在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户</span><span class="sxs-lookup"><span data-stu-id="0a335-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="0a335-105">本主题介绍如何为具有本地 PSTN 连接的电话系统启用用户。</span><span class="sxs-lookup"><span data-stu-id="0a335-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="0a335-106">在按照本主题中的步骤操作之前，应阅读以下内容：。</span><span class="sxs-lookup"><span data-stu-id="0a335-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="0a335-107">若要了解如何设置混合连接，请参阅规划 Skype for Business Server 和 [Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 之间的混合连接和部署 Skype for Business Server 和 Skype for Business Online 之间的混合 [连接](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="0a335-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
    
- <span data-ttu-id="0a335-108">若要了解有关规划部署的信息，请参阅在 Skype for Business Server 中使用本地 [PSTN 连接规划电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="0a335-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="0a335-109">若要了解有关电话系统（包括许可和计划）的更多信息，请参阅[PSTN Calling plans for Skype for Business。](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="0a335-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="0a335-110">Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0a335-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="0a335-111">此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="0a335-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="0a335-112">了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="0a335-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="0a335-113">将用户移动到具有本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="0a335-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="0a335-114">在将用户迁移到 Skype for Business Online 之前，建议在 Skype for Business Server 或 Lync Server 2013 中在本地启用用户，然后联机移动用户。</span><span class="sxs-lookup"><span data-stu-id="0a335-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="0a335-115">有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 和 Enable the users for 企业语音 on premises [ (](enable-the-users-for-enterprise-voice-on-premises.md) performed while the users are homed on-premises) 的特殊注意事项部分。</span><span class="sxs-lookup"><span data-stu-id="0a335-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="0a335-116">所有用户都必须在本地 Active Directory 中创建，并且使用受支持的 Azure AD 连接器版本同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0a335-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="0a335-117">无法为直接在 Azure AD 中创建的 Office 365 电话系统启用用户。</span><span class="sxs-lookup"><span data-stu-id="0a335-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="0a335-118">如果要为在 Azure AD 中创建的用户启用具有本地 PSTN 连接的电话系统，则需要在本地 AD 中为该用户创建新帐户，在本地配置帐户，然后使用受支持的 Azure AD 连接器工具版本同步该帐户。</span><span class="sxs-lookup"><span data-stu-id="0a335-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="0a335-119">为具有本地 PSTN 连接的电话系统启用用户，然后将他们移动到 Skype for Business Online 需要以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0a335-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="0a335-120">[为用户启用企业语音本地](enable-the-users-for-enterprise-voice-on-premises.md) (，而用户位于本地) 。</span><span class="sxs-lookup"><span data-stu-id="0a335-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="0a335-121">[分配在用户](assign-a-voice-routing-policy.md) (内部部署服务器时执行的语音路由) 。</span><span class="sxs-lookup"><span data-stu-id="0a335-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="0a335-122">[将用户同步到云，并分配 (](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="0a335-122">[Synchronize users to the cloud and assign licenses](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (performed using Office 365).</span></span>
    
- <span data-ttu-id="0a335-123">[将本地用户移动到 Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (使用本地Windows PowerShell，但使用 Office 365 管理员凭据) 。</span><span class="sxs-lookup"><span data-stu-id="0a335-123">[Move on-premises users to Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="0a335-124">[为用户启用企业语音远程 PowerShell](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 执行的电话 (语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="0a335-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
