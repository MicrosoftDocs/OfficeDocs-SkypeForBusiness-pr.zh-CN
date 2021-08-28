---
title: 在安全与配置中企业语音先决条件Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: Summary： Learn about the security and configuration prerequisites for 企业语音 in Skype for Business Server.
ms.openlocfilehash: 0f46de6fa8b8c2027a3828df67a0330212392e45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617018"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>在安全与配置中企业语音先决条件Skype for Business Server
 
**摘要：** 了解 企业语音 中的安全Skype for Business Server。
  
在部署企业语音，请验证基础结构是否满足以下安全性、用户配置和特定于方案的硬件先决条件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理权限和证书基础结构

在部署之前，请检查以下内容：
  
- 部署企业语音的管理员应当是 RTCUniversalServerAdmins 组的成员。
    
- 执行配置任务的管理员必须具有足够的权限：
    
  - **CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
  - **CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
- 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    > [!NOTE]
    > 有关 Skype for Business Server 中的证书要求的详细信息，请参阅[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 Server requirements for Skype for Business Server [2019。](../../../SfBServer2019/plan/system-requirements.md) 
  
## <a name="user-configuration"></a>用户配置

如果在前端部署期间将中介服务器与每台前端池或 Standard Edition 服务器并并，则安装这些服务器角色的文件时会自动配置 企业语音 所需的用户设置。
  
如果此时要执行全新的企业语音工作负荷部署，则在开始部署过程之前，为计划要对其启用企业语音的每个用户指定一个主电话号码。 作为管理员，应确保此号码是唯一的。 实施之前，所有主要电话号码都必须 (格式正确) 控制面板复制到每个用户的"线路 **URI"Skype for Business Server** 属性。
  
> [!NOTE]
> 有关部署所需的主要电话号码企业语音，请参阅[示例规范化规则](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>下一步：安装文件或配置 PSTN 连接

验证软件和环境先决条件后企业语音您可以：
  
- 安装中介服务器，如[在 Skype for Business Server](deploy-a-mediation-server.md)的拓扑生成器中部署中介服务器中所述，但仅在要部署独立的中介服务器或池时，因为中介服务器是作为前端池或 Standard Edition 服务器部署过程的一部分安装的。）
    
- 或者，开始配置设置以路由 企业语音 用户的呼叫，如在 Skype for Business Server 中配置[中继中所述](configure-trunks.md)。
    

