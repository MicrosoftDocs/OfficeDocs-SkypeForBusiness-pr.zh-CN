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
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的企业语音安全性和配置先决条件
 
**摘要：**对于业务服务器 2015年了解在 Skype 的企业语音的安全和配置的前提条件。
  
在部署之前企业语音，请验证您的基础结构符合下列安全、 用户配置和特定于方案的硬件系统必备组件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理权限和证书基础结构

部署前，请检查以下几点：
  
- 管理员部署企业语音应该是 RTCUniversalServerAdmins 组的成员。
    
- 执行配置任务的管理员必须具有足够的权限：
    
  - **CsVoiceAdministrator：**此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
  - **CsUserAdministrator：**此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
  - **CsAdministrator：**此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
- 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    > [!NOTE]
    > 在 Skype 业务服务器的证书要求的详细信息，请参阅[有关业务服务器 2015年的 Skype 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。 
  
## <a name="user-configuration"></a>用户配置

如果在前端部署期间搭配中介服务器与每个前端池或标准版服务器，用户设置所需的企业语音自动配置文件对这些服务器角色的安装过程。
  
如果这一次，然后再开始部署过程新部署的企业语音工作负载，将指定计划启用企业语音为每个用户的主要电话的号码。 作为管理员，应确保此号码是唯一的。 之前实施，所有主电话号码必须标准化 （正确地格式化），并复制到每个用户的**行 URI**属性对业务服务器控件面板使用 Skype。
  
> [!NOTE]
> 有关企业语音部署所需的主电话号码示例，请参阅[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>后续步骤：安装文件或配置 PSTN 连接

验证软件和企业语音的环境先决条件后您可以：
  
- 所述[部署在拓扑生成器在 Skype 业务服务器 2015年的中介服务器](deploy-a-mediation-server.md)，但只有在您希望部署独立的中介服务器或池，因为中介服务器作为前端的一部分安装安装中介服务器，池或标准版服务器部署过程时多结束。
    
- 或者，开始配置设置应用于企业语音用户的路由呼叫[配置中继业务服务器 2015年的 Skype 中](configure-trunks.md)所述。
    

