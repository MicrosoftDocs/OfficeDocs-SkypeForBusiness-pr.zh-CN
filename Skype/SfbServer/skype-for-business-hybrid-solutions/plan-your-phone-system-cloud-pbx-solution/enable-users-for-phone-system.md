---
title: 允许用户使用 Office 365 中的电话系统内部在 Skype 的 PSTN 连接业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何启用用户的 Office 365 中的电话系统与内部的 PSTN 连接性。 本主题中的步骤操作之前，应阅读以下:。
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="489c8-104">允许用户使用 Office 365 中的电话系统内部在 Skype 的 PSTN 连接业务服务器</span><span class="sxs-lookup"><span data-stu-id="489c8-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="489c8-105">本主题介绍如何启用用户的 Office 365 中的电话系统与内部的 PSTN 连接性。</span><span class="sxs-lookup"><span data-stu-id="489c8-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="489c8-106">本主题中的步骤操作之前，应阅读以下:。</span><span class="sxs-lookup"><span data-stu-id="489c8-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="489c8-107">若要了解如何设置混合连接，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署混合来临 Skype 业务服务器和 Skype 的在线业务](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="489c8-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="489c8-108">若要了解如何规划您的部署，请参阅[计划内部 Skype 业务服务器中的 PSTN 连接与 Office 365 中的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="489c8-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="489c8-109">若要了解有关 Office 365，包括授权和计划中的电话系统看到[PSTN 调用 Skype 业务的计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="489c8-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="489c8-110">将用户移动到 Office 365 中的电话系统，与内部的 PSTN 连接性</span><span class="sxs-lookup"><span data-stu-id="489c8-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="489c8-111">在移动之前用户到 Skype 的在线业务，建议为业务服务器或 Lync Server 2013，启用部署在 Skype 上的用户，然后将它们联机移动。</span><span class="sxs-lookup"><span data-stu-id="489c8-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="489c8-112">有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[内部部署的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)的特殊注意事项一节。</span><span class="sxs-lookup"><span data-stu-id="489c8-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="489c8-113">所有用户必须在内部部署 Active Directory 中创建和同步到使用 Azure AD 连接器的受支持的版本的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="489c8-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="489c8-114">在 Azure AD 中直接创建 Office 365 中的电话系统，不能启用用户。</span><span class="sxs-lookup"><span data-stu-id="489c8-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="489c8-115">如果您想要使用内部部署 PSTN 连接在 Azure AD 中创建的用户启用 Office 365 中的电话系统，您需要在您在部署中创建一个新的帐户，该用户的广告，配置帐户内部，然后同步帐户Azure AD 连接器工具的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="489c8-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="489c8-116">使用户在 Office 365 的电话系统内部的 PSTN 连接，然后移动到 Skype 的在线业务需要执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="489c8-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="489c8-117">[内部部署的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)（执行时用户是穴内部部署）。</span><span class="sxs-lookup"><span data-stu-id="489c8-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="489c8-118">[指定语音路由策略](assign-a-voice-routing-policy.md)（执行时用户是穴内部部署）。</span><span class="sxs-lookup"><span data-stu-id="489c8-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="489c8-119">[同步用户对云和分派许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)（执行使用 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="489c8-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="489c8-120">[移动内部用户 Skype 的在线业务](move-on-premises-users-to-skype-for-business-online.md)（使用 Windows PowerShell 内部，但使用 Office 365 提供管理员凭据执行）。</span><span class="sxs-lookup"><span data-stu-id="489c8-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="489c8-121">[允许用户在线企业语音和 Office 365 语音邮件中的电话系统](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（执行使用远程 PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="489c8-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

