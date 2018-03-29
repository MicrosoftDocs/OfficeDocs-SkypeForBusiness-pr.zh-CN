---
title: Skype for Business Server 2015 中的企业语音安全性和配置先决条件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 摘要： 了解的业务服务器 2015 Skype 在企业语音的安全和配置的前提条件。
ms.openlocfilehash: 400af6d42026007315e30a7706e9730901f90708
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="e8e54-103">Skype for Business Server 2015 中的企业语音安全性和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="e8e54-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8e54-104">**摘要：**对于业务服务器 2015年了解在 Skype 的企业语音的安全和配置的前提条件。</span><span class="sxs-lookup"><span data-stu-id="e8e54-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e8e54-105">在部署之前企业语音，请验证您的基础结构符合下列安全、 用户配置和特定于方案的硬件系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="e8e54-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="e8e54-106">管理权限和证书基础结构</span><span class="sxs-lookup"><span data-stu-id="e8e54-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="e8e54-107">部署前，请检查以下几点：</span><span class="sxs-lookup"><span data-stu-id="e8e54-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="e8e54-108">管理员部署企业语音应该是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="e8e54-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="e8e54-109">执行配置任务的管理员必须具有足够的权限：</span><span class="sxs-lookup"><span data-stu-id="e8e54-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="e8e54-110">**CsVoiceAdministrator：**此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。</span><span class="sxs-lookup"><span data-stu-id="e8e54-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="e8e54-p101">**CsUserAdministrator：**此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="e8e54-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="e8e54-113">**CsAdministrator：**此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="e8e54-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="e8e54-114">使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。</span><span class="sxs-lookup"><span data-stu-id="e8e54-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8e54-115">在 Skype 业务服务器的证书要求的详细信息，请参阅[有关业务服务器 2015年的 Skype 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e54-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="e8e54-116">用户配置</span><span class="sxs-lookup"><span data-stu-id="e8e54-116">User configuration</span></span>

<span data-ttu-id="e8e54-117">如果在前端部署期间搭配中介服务器与每个前端池或标准版服务器，用户设置所需的企业语音自动配置文件对这些服务器角色的安装过程。</span><span class="sxs-lookup"><span data-stu-id="e8e54-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="e8e54-118">如果这一次，然后再开始部署过程新部署的企业语音工作负载，将指定计划启用企业语音为每个用户的主要电话的号码。</span><span class="sxs-lookup"><span data-stu-id="e8e54-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="e8e54-119">作为管理员，应确保此号码是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e8e54-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="e8e54-120">之前实施，所有主电话号码必须标准化 （正确地格式化），并复制到每个用户的**行 URI**属性对业务服务器控件面板使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e8e54-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8e54-121">有关企业语音部署所需的主电话号码示例，请参阅[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。</span><span class="sxs-lookup"><span data-stu-id="e8e54-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="e8e54-122">后续步骤：安装文件或配置 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="e8e54-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="e8e54-123">验证软件和企业语音的环境先决条件后您可以：</span><span class="sxs-lookup"><span data-stu-id="e8e54-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="e8e54-124">所述[部署在拓扑生成器在 Skype 业务服务器 2015年的中介服务器](deploy-a-mediation-server.md)，但只有在您希望部署独立的中介服务器或池，因为中介服务器作为前端的一部分安装安装中介服务器，池或标准版服务器部署过程时多结束。</span><span class="sxs-lookup"><span data-stu-id="e8e54-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="e8e54-125">或者，开始配置设置应用于企业语音用户的路由呼叫[配置中继业务服务器 2015年的 Skype 中](configure-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="e8e54-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server 2015](configure-trunks.md).</span></span>
    

