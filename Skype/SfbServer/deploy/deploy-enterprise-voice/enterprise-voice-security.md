---
title: Skype 业务服务器中的企业语音的安全性和配置先决条件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 摘要： 了解面向 Business Server Skype 中的企业语音的安全性和配置先决条件。
ms.openlocfilehash: 9fd7a4fd35785c0cb4a7c10efb7dc781b84b8186
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887585"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Skype 业务服务器中的企业语音的安全性和配置先决条件
 
**摘要：** 了解有关 Skype 中的企业语音的安全性和配置先决条件的业务服务器。
  
之前部署企业语音，请验证您的基础结构满足以下安全性、 用户配置和特定于方案的硬件先决条件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理权限和证书基础结构

部署前，请检查以下几点：
  
- 部署企业语音的管理员应当是 RTCUniversalServerAdmins 组的成员。
    
- 执行配置任务的管理员必须具有足够的权限：
    
  - **CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
  - **CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
- 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    > [!NOTE]
    > Skype 中的业务服务器的证书要求的详细信息，请参阅[环境要求的业务服务器 2015 Skype](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[业务服务器 2019年的 Skype 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。 
  
## <a name="user-configuration"></a>用户配置

如果您并置在一起的中介服务器与每个前端池或 Standard Edition server 前端部署过程中，所必需的企业语音的用户设置自动配置的文件的这些服务器角色的安装过程中。
  
如果您在此之前的部署过程的时间新部署企业语音工作负荷，，指定您计划启用企业语音的每个用户主要电话号码。 作为管理员，应确保此号码是唯一的。 之前实现，所有的主电话号码必须规范化 （正确设置其格式），并复制到每个用户的**线路 URI**属性用于业务 Server Control Panel Skype。
  
> [!NOTE]
> 有关企业语音部署所需的主电话号码示例，请参阅[Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>后续步骤：安装文件或配置 PSTN 连接

验证软件和环境的企业语音先决条件后您可以：
  
- 安装中介服务器，如下所述[部署中介服务器中的业务服务器 Skype 的拓扑生成器中](deploy-a-mediation-server.md)，但仅当您想要部署为独立中介服务器或池，因为前端的一部分安装中介服务器池或 Standard Edition 服务器部署过程并置。
    
- 或者，开始配置设置以路由企业语音用户的呼叫[中的业务服务器 Skype 配置中继](configure-trunks.md)中所述。
    

