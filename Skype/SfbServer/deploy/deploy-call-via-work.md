---
title: 在 Skype for Business Server 2015 中部署单位电话呼叫
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要： 了解如何部署调用通过工作在 Skype 业务服务器 2015年的某些或所有用户。
ms.openlocfilehash: 325134bd4e24621bbb223ccc47180274256eaca2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署单位电话呼叫
 
**摘要：**了解如何部署调用通过工作在 Skype 业务服务器 2015年的某些或所有用户。
  
使用下列步骤为您的用户部署调用通过工作。 [用于调用通过工作在 Skype 的业务服务器 2015年计划](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论规划的考虑因素。 在以前版本的 Lync 服务器远程调用控制是一种功能，使用户能够控制手机 PBX Lync Server。 在 Skype 业务服务器，此功能已被调用通过工作。 
  
## <a name="prerequisites-for-call-via-work"></a>通过工作的呼叫的先决条件

通过工作中调用使用统一通信 Web API (UCWA)，它的业务服务器前端服务器会自动在所有 Skype 上安装。 若要使用户调用通过工作，还必须满足以下先决条件到位： 
  
- 您必须部署，中介服务器作为前端服务器的一部分或作为一个独立的角色。 您还必须部署 IP-PBX 网关。
    
- 所有的用户都将启用调用通过工作必须直接向内拨号 (DID) 的 PBX 电话系统。 
    
- 您必须启用企业语音调用通过工作的所有用户。 当您执行此操作时，您必须配置为每个用户使用相应的 PBX 电话系统的相应 DID 号码业务未编号 Skype。 
    
- 所有的用户都将使用调用通过工作必须具有**自动配置**其 Skype 业务客户端在其**高级连接**选项中选择。 这使客户端能够发现 UCWA Url。 **自动配置**为默认选择。
    
- 对于每个调用通过工作的用户，启用呼叫转移和并发响铃。 
    
- 对于每个呼叫通过单位用户，请确保启用了拨入会议和会议拨出。 这使这些用户可以获得 Skype 进出业务会议。
    
- 确保每个呼叫通过单位用户禁用委派、 团队联络和响应组。
    
## <a name="deploy-call-via-work"></a>部署单位电话呼叫

先决条件就绪后，请执行以下操作：
  
- 创建部署 Skype 业务显示在 PBX 呼叫方 ID 的用户要调用调用通过工作全局的电话号码。 
    
- 创建一个或多个调用通过工作策略
    
- 为每个用户都将启用调用通过工作分配调用通过工作策略
    
### <a name="create-the-call-via-work-global-phone-number"></a>创建通过工号拨号全局电话号码

- 键入以下 cmdlet
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    例如，以下 cmdlet 将全局电话号码设为 1-555-123-4567。
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>创建通过工号拨号策略

- 键入以下 cmdlet
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    例如，以下 cmdlet 创建称为 ContosoUser1CvWP 的调用通过的工作策略，要求用户使用管理员回拨号码，并将该回叫号码设置为 1-555-789-1234。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>向用户分配调用通过工作策略

- 键入以下 cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如，以下 cmdlet 将分配给名为**ContosoUser1**的用户的调用通过工作策略"ContosoUser1CvWP"。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另请参阅

#### 

[规划工作在 Skype 业务服务器 2015年通过调用](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

