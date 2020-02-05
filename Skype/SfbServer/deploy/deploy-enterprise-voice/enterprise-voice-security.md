---
title: Skype for business 服务器中的企业语音的安全和配置先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 摘要：了解 Skype for business 服务器中的企业语音的安全和配置先决条件。
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767235"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Skype for business 服务器中的企业语音的安全和配置先决条件
 
**摘要：** 了解 Skype for business 服务器中的企业语音的安全和配置先决条件。
  
部署企业语音之前，请验证你的基础结构是否满足以下安全性、用户配置以及特定于方案的硬件先决条件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理权限和证书基础结构

部署前，请检查以下几点：
  
- 部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。
    
- 执行配置任务的管理员必须具有足够的权限：
    
  - **CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
  - **CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
- 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    > [!NOTE]
    > 有关 Skype for Business Server 中的证书要求的详细信息，请参阅 skype for business server [2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
## <a name="user-configuration"></a>用户配置

如果在前端部署期间使用每个前端池或标准版服务器 collocated 中介服务器，则在安装这些服务器角色的文件期间会自动配置企业语音所需的用户设置。
  
如果此时你新部署企业语音工作负荷，则在开始部署过程之前，请为计划启用企业语音的每个用户指定一个主要电话号码。 作为管理员，应确保此号码是唯一的。 实现之前，必须对所有主要电话号码进行标准化（格式正确），并使用 Skype for Business Server 控制面板将其复制到每个用户的**行 URI**属性。
  
> [!NOTE]
> 有关企业语音部署所需的主电话号码示例，请参阅[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>后续步骤：安装文件或配置 PSTN 连接

验证了企业语音的软件和环境先决条件后，您可以执行以下操作之一：
  
- 如在[Skype For Business server 的拓扑生成器中部署中介服务器](deploy-a-mediation-server.md)中所述，但仅当你想要部署独立的中介服务器或池时，才会安装中介服务器，因为在 collocated 时，会在前端池或标准版服务器部署过程的一部分中安装中介服务器。
    
- 或者，开始配置设置以路由企业语音用户的呼叫，如[配置 Skype For Business 服务器中的中继](configure-trunks.md)中所述。
    

