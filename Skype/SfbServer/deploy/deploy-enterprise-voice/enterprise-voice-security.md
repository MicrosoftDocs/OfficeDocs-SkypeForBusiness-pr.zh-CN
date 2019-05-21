---
title: Skype for business 服务器中的企业语音的安全和配置先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '摘要: 了解 Skype for business 服务器中的企业语音的安全和配置先决条件。'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294156"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="37007-103">Skype for business 服务器中的企业语音的安全和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="37007-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="37007-104">**摘要:** 了解 Skype for business 服务器中的企业语音的安全和配置先决条件。</span><span class="sxs-lookup"><span data-stu-id="37007-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="37007-105">部署企业语音之前, 请验证你的基础结构是否满足以下安全性、用户配置以及特定于方案的硬件先决条件。</span><span class="sxs-lookup"><span data-stu-id="37007-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="37007-106">管理权限和证书基础结构</span><span class="sxs-lookup"><span data-stu-id="37007-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="37007-107">部署前，请检查以下几点：</span><span class="sxs-lookup"><span data-stu-id="37007-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="37007-108">部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="37007-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="37007-109">执行配置任务的管理员必须具有足够的权限：</span><span class="sxs-lookup"><span data-stu-id="37007-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="37007-110">**CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。</span><span class="sxs-lookup"><span data-stu-id="37007-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="37007-p101">**CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="37007-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="37007-113">**CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。</span><span class="sxs-lookup"><span data-stu-id="37007-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="37007-114">使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。</span><span class="sxs-lookup"><span data-stu-id="37007-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37007-115">有关 Skype for Business Server 中的证书要求的详细信息, 请参阅 skype for business server [2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37007-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="37007-116">用户配置</span><span class="sxs-lookup"><span data-stu-id="37007-116">User configuration</span></span>

<span data-ttu-id="37007-117">如果在前端部署期间使用每个前端池或标准版服务器 collocated 中介服务器, 则在安装这些服务器角色的文件期间会自动配置企业语音所需的用户设置。</span><span class="sxs-lookup"><span data-stu-id="37007-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="37007-118">如果此时你新部署企业语音工作负荷, 则在开始部署过程之前, 请为计划启用企业语音的每个用户指定一个主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="37007-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="37007-119">作为管理员，应确保此号码是唯一的。</span><span class="sxs-lookup"><span data-stu-id="37007-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="37007-120">实现之前, 必须对所有主要电话号码进行标准化 (格式正确), 并使用 Skype for Business Server 控制面板将其复制到每个用户的**行 URI**属性。</span><span class="sxs-lookup"><span data-stu-id="37007-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37007-121">有关企业语音部署所需的主电话号码示例，请参阅[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。</span><span class="sxs-lookup"><span data-stu-id="37007-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="37007-122">后续步骤：安装文件或配置 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="37007-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="37007-123">验证了企业语音的软件和环境先决条件后, 您可以执行以下操作之一:</span><span class="sxs-lookup"><span data-stu-id="37007-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="37007-124">安装中介服务器, 如在[Skype For Business server 的拓扑生成器中部署中介服务器](deploy-a-mediation-server.md)中所述, 但仅当你希望部署独立的中介服务器或池时, 因为在前端安装了中介服务器collocated 时的池或标准版服务器部署过程。</span><span class="sxs-lookup"><span data-stu-id="37007-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="37007-125">或者, 开始配置设置以路由企业语音用户的呼叫, 如[配置 Skype For Business 服务器中的中继](configure-trunks.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="37007-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

