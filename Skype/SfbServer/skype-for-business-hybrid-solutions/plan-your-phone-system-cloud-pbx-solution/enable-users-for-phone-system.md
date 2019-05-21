---
title: 使用 Skype for Business Server 中的本地 PSTN 连接在 Office 365 中启用电话系统的用户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
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
description: 本主题介绍了如何使用本地 PSTN 连接在 Office 365 中启用电话系统的用户。 按照本主题中的步骤操作之前, 应阅读以下内容:。
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287459"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="900ce-104">使用 Skype for Business Server 中的本地 PSTN 连接在 Office 365 中启用电话系统的用户</span><span class="sxs-lookup"><span data-stu-id="900ce-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="900ce-105">本主题介绍了如何使用本地 PSTN 连接在 Office 365 中启用电话系统的用户。</span><span class="sxs-lookup"><span data-stu-id="900ce-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="900ce-106">按照本主题中的步骤操作之前, 应阅读以下内容:。</span><span class="sxs-lookup"><span data-stu-id="900ce-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="900ce-107">若要了解如何设置混合连接, 请参阅[在 skype for Business 服务器与 skype for Business online 之间规划混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[在 Skype for Business server 和 Skype for Business online 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="900ce-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="900ce-108">若要了解有关规划部署的信息, 请参阅[通过 Skype For Business 服务器中的本地 PSTN 连接在 Office 365 中规划电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="900ce-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="900ce-109">若要了解有关 Office 365 中的电话系统的详细信息 (包括许可和计划), 请参阅[Skype for business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="900ce-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="900ce-110">通过本地 PSTN 连接将用户移动到 Office 365 中的电话系统</span><span class="sxs-lookup"><span data-stu-id="900ce-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="900ce-111">将用户移动到 Skype for business Online 之前, 建议你在 Skype for business Server 或 Lync Server 2013 中的本地用户启用用户, 然后将其联机。</span><span class="sxs-lookup"><span data-stu-id="900ce-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="900ce-112">有关详细信息, 请参阅[规划 skype for Business 服务器与 skype for Business Online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md), 以及在用户[启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)时的特殊注意事项部分 (在用户托管时执行)本地)。</span><span class="sxs-lookup"><span data-stu-id="900ce-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="900ce-113">所有用户都必须在本地 Active Directory 中创建, 并使用受支持的 Azure AD 连接器版本同步到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="900ce-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="900ce-114">不能在 Office 365 中为直接在 Azure AD 中创建的用户启用电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="900ce-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="900ce-115">如果你想要在 Office 365 中为在 Azure AD 中创建的用户启用本地 PSTN 连接, 你需要在本地广告中为该用户创建一个新帐户, 配置本地帐户, 然后使用 "同步帐户"受支持的 Azure AD Connector 工具版本。</span><span class="sxs-lookup"><span data-stu-id="900ce-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="900ce-116">通过本地 PSTN 连接使用户可以使用 Office 365 中的电话系统, 然后将其移动到 Skype for Business Online, 需要执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="900ce-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="900ce-117">[为企业内部部署的用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)(在用户托管本地时执行)。</span><span class="sxs-lookup"><span data-stu-id="900ce-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="900ce-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md)（当用户驻留在本地时执行）。</span><span class="sxs-lookup"><span data-stu-id="900ce-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="900ce-119">[将用户同步到云并分配许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)(使用 Office 365 执行)。</span><span class="sxs-lookup"><span data-stu-id="900ce-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="900ce-120">[将本地用户移动到 Skype For Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)(使用 Windows PowerShell 内部部署, 但使用 Office 365 管理员凭据)。</span><span class="sxs-lookup"><span data-stu-id="900ce-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="900ce-121">[在 Office 365 语音邮件中启用企业语音在线和手机系统用户](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(使用远程 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="900ce-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

