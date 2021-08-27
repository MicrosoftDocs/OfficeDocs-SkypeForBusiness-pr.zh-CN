---
title: 在部署中部署通过工Skype for Business Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要：了解如何在 Skype for Business Server中为部分或所有用户部署通过工作电话呼叫。
ms.openlocfilehash: c6113c4447e30d59a262bf2c02b3f7ff2db171f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624414"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>在部署中部署通过工Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中为部分或所有用户部署通过工作电话呼叫。
  
使用以下步骤为用户部署通过工位呼叫。 Plan for Call [Via Work in Skype for Business Server 中讨论了规划注意事项](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 在以前版本的 Lync Server 中，远程呼叫控制是一项使用户能够使用 Lync Server 控制其 PBX 电话的功能。 在Skype for Business Server，此功能已替换为通过工位呼叫功能。 
  
## <a name="prerequisites-for-call-via-work"></a>通过工位呼叫的先决条件

通过工位呼叫使用 UCWA (统一通信 Web API) ，该 API 会自动安装在所有Skype for Business Server前端服务器上。 若要为用户启用通过工位呼叫，还必须满足以下先决条件： 
  
- 必须将中介服务器部署为前端服务器的一部分或作为独立角色。 还必须部署 IP-PBX 网关。
    
- 将启用通过工号拨号的所有用户都必须在 PBX 电话系统上具有 (外) DID 电话。 
    
- 必须启用所有通过工位呼叫的用户企业语音。 在这样做时，必须将每个用户的 DID Skype for Business配置为相应的 PBX 电话系统的对应 DID 号码。 
    
- 在使用单位电话呼叫的所有用户的客户端中，必须在其高级连接选项中选中Skype for Business配置。 这使客户端能够发现 UCWA URL。 **自动配置** 是默认选择。
    
- 对于每个通过工位呼叫的用户，启用呼叫转发和同时响铃。 
    
- 对于每个"通过工号拨号"用户，确保启用了电话拨入式会议和会议拨出。 这使这些用户能够进入和退出Skype for Business会议。
    
- 确保已针对每个通过工位呼叫的用户禁用委派、团队呼叫和响应组。
    
## <a name="deploy-call-via-work"></a>部署单位电话呼叫

满足先决条件后，执行以下操作：
  
- 为部署创建全局电话号码，Skype for Business通过工号呼叫的用户的 PBX 呼叫者 ID 上显示该号码。 
    
- 创建一个或多个通过工位呼叫策略
    
- 将"通过工位呼叫"策略分配给将为"通过工位呼叫"启用的每个用户
    
### <a name="create-the-call-via-work-global-phone-number"></a>创建通过工号呼叫全局电话号码

- 键入以下 cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    例如，以下 cmdlet 将全局电话号码设置为 1-555-123-4567。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>创建通过工位呼叫策略

- 键入以下 cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    例如，以下 cmdlet 创建名为 ContosoUser1CvWP 的通过工号呼叫策略，要求用户使用管理员回拨号码，并设置该回拨号码为 1-555-789-1234。
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>将"通过工位呼叫"策略分配给用户

- 键入以下 cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如，以下 cmdlet 将"通过工号呼叫"策略"ContosoUser1CvWP"分配给名为 **ContosoUser1 的用户**。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另请参阅

[Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

