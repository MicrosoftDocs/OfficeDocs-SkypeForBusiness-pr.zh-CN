---
title: 为用户启用 Office 365 中的电话系统与 Skype 中的内部部署 PSTN 连接的业务服务器
ms.reviewer: ''
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接。 在执行本主题中的步骤之前，您应阅读以下文章:。
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889215"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="0085e-104">为用户启用 Office 365 中的电话系统与 Skype 中的内部部署 PSTN 连接的业务服务器</span><span class="sxs-lookup"><span data-stu-id="0085e-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="0085e-105">本主题介绍如何为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="0085e-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="0085e-106">在执行本主题中的步骤之前，您应阅读以下文章:。</span><span class="sxs-lookup"><span data-stu-id="0085e-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="0085e-107">若要了解如何设置混合连接性，请参阅[规划业务服务器和 Skype 业务 online Skype 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署之间 Skype 业务服务器和 Skype 业务 online 的混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="0085e-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="0085e-108">若要了解有关规划您的部署，请参阅[规划与业务服务器 Skype 中的内部部署 PSTN 连接的 Office 365 中的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="0085e-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="0085e-109">若要了解有关在 Office 365 中，包括许可和计划的电话系统的详细信息，请参阅[PSTN 呼叫 for Business 的 Skype 的计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="0085e-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="0085e-110">将用户迁移到 Office 365 中的电话系统与内部部署 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="0085e-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="0085e-111">之前为业务 Online 将用户移动到 Skype，建议您在 Skype 本地用户启用企业服务器或 Lync Server 2013 和联机移动它们。</span><span class="sxs-lookup"><span data-stu-id="0085e-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="0085e-112">有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[为本地的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)（执行时用户都驻留的特殊注意事项部分内部部署）。</span><span class="sxs-lookup"><span data-stu-id="0085e-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="0085e-113">必须在本地 Active Directory 中创建并同步到 Office 365 使用 Azure AD 连接器的受支持的版本的所有用户。</span><span class="sxs-lookup"><span data-stu-id="0085e-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="0085e-114">用户不能启用用户直接在 Azure AD 中创建 Office 365 中的电话系统。</span><span class="sxs-lookup"><span data-stu-id="0085e-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="0085e-115">如果您想要启用与 Azure AD 中创建的用户的内部部署 PSTN 连接的 Office 365 中的电话系统，您将需要在您的内部部署中创建新的用户帐户 AD，配置帐户内部部署，，，然后将同步帐户使用受支持的 Azure AD 连接器工具版本。</span><span class="sxs-lookup"><span data-stu-id="0085e-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="0085e-116">为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接，然后为业务 Online 将它们移动到 Skype 需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0085e-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="0085e-117">[为本地的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)（执行驻留在内部部署用户时）。</span><span class="sxs-lookup"><span data-stu-id="0085e-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="0085e-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md)（当用户驻留在本地时执行）。</span><span class="sxs-lookup"><span data-stu-id="0085e-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="0085e-119">[将用户同步到云和分配许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)（执行使用 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="0085e-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="0085e-120">[在本地将用户移动到业务 online Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)（执行使用 Windows PowerShell 在本地，但使用 Office 365 管理员凭据）。</span><span class="sxs-lookup"><span data-stu-id="0085e-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="0085e-121">[为用户启用企业语音 online 和 Office 365 语音邮件中的电话系统](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（使用远程 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="0085e-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

