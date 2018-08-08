---
title: 部署呼叫通过业务服务器 Skype 中工作
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要： 了解如何部署为部分或全部用户呼叫通过单位电话的 Skype 业务服务器。
ms.openlocfilehash: 60890f510f5f895f3a99f070cd9cf1a7c997da61
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991043"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>部署呼叫通过业务服务器 Skype 中工作
 
**摘要：** 了解如何部署为部分或全部用户呼叫通过单位电话的 Skype 业务服务器。
  
使用以下步骤为用户部署通过单位电话呼叫。 [规划呼叫通过中工作的企业服务器的 Skype](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论了规划注意事项。 在早期版本的 Lync Server 远程呼叫控制是一种功能，允许用户控制其 PBX 电话与 Lync Server。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。 
  
## <a name="prerequisites-for-call-via-work"></a>用单位电话呼叫的先决条件

通过单位电话呼叫使用统一通信 Web API (UCWA)，其上自动安装所有 Skype 的业务 Server 前端服务器。 若要为用户启用呼叫通过单位电话，您必须具有就地以下先决条件： 
  
- 您必须具有中介服务器部署，前端服务器的一部分或作为独立角色。 您还必须部署 IP-PBX 网关。
    
- 将启用呼叫通过单位电话的所有用户必须在 PBX 电话系统上都具有外线直拨分机 (DID)。 
    
- 您必须启用企业语音呼叫通过单位电话的所有用户。 时执行此操作时，您必须配置为每个用户使用的相应的 PBX 电话系统的相应 DID 号码业务 DID 号码 Skype。 
    
- 将使用呼叫通过单位电话的所有用户必须都具有**自动配置**其 Skype 业务客户端中其**高级连接**选项中选择。 这样，客户端可以发现 UCWA Url。 **自动配置**为默认选择。
    
- 对于每个呼叫通过单位电话用户，启用呼叫转接和同时响铃。 
    
- 为每个呼叫通过单位电话用户，确保启用了电话拨入式会议和拨出式会议。 这样，这些用户获得业务会议和 Skype 注销。
    
- 确保通过单位电话呼叫中的每个用户禁用委派、 团队呼叫和响应组。
    
## <a name="deploy-call-via-work"></a>部署单位电话呼叫

先决条件就绪后，请执行以下操作：
  
- 创建部署上正在呼叫通过单位电话的呼叫的用户的 PBX 呼叫者 ID 显示 for Business 的 Skype 全局电话号码。 
    
- 创建一个或多个呼叫通过单位电话的策略
    
- 通过单位电话呼叫策略分配给每个用户都将启用通过单位电话呼叫
    
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
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    例如，以下 cmdlet 创建名为 ContosoUser1CvWP 呼叫通过单位电话策略、 要求用户使用管理员回拨号码，并将该回拨号码设置为 1-555-789-1234。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>为用户分配呼叫通过工作策略

- 键入以下 cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如，以下 cmdlet 将"ContosoUser1CvWP"的通过单位电话呼叫策略分配给名为**ContosoUser1**的用户。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另请参阅

[规划用单位电话的 Skype 业务服务器的呼叫](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

