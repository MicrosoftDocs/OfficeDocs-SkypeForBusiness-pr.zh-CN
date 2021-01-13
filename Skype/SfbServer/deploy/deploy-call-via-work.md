---
title: 在 Skype for Business Server 中部署通过工位呼叫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要：了解如何在 Skype for Business Server 中为部分或所有用户部署通过工位呼叫。
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825002"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>在 Skype for Business Server 中部署通过工位呼叫
 
**摘要：** 了解如何在 Skype for Business Server 中为部分或所有用户部署通过工位呼叫。
  
使用以下步骤为用户部署通过工位呼叫。 规划注意事项在 Plan [for Call Via Work in Skype for Business Server 中进行讨论](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 在早期版本的 Lync Server 远程呼叫控制中，该功能使用户能够使用 Lync Server 控制 PBX 电话。 在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。 
  
## <a name="prerequisites-for-call-via-work"></a>通过工次电话呼叫的先决条件

通过工次电话呼叫使用 UCWA (统一通信 Web API) ，它会自动安装在所有 Skype for Business Server 前端服务器上。 若要为用户启用通过工位电话呼叫，还必须满足以下先决条件： 
  
- 必须部署中介服务器（作为前端服务器的一部分或作为独立角色）。 还必须部署 IP-PBX 网关。
    
- 将启用通过工号拨号的所有用户都必须在 PBX 电话系统 (DID) 直拨拨号码。 
    
- 必须为所有通过工位呼叫的用户启用企业语音。 这样做时，必须将每个用户的 Skype for Business DID 号码配置为相应的 PBX 电话系统的对应 DID 号码。 
    
- 将使用单位电话呼叫的所有用户都必须在 **Skype** for Business客户端的高级连接选项中选中自动配置。 这使客户端能够发现 UCWA URL。 **自动配置** 是默认选择。
    
- 对于每个通过工位呼叫的用户，启用呼叫转发和同时响铃。 
    
- 对于每个通过工号拨号的用户，确保启用了电话拨入式会议和会议拨出。 这使这些用户可以进入和退出 Skype for Business 会议。
    
- 确保已针对每个通过工位呼叫的用户禁用委派、团队呼叫和响应组。
    
## <a name="deploy-call-via-work"></a>部署单位电话呼叫

在先决条件就位后，执行以下操作：
  
- 为部署创建全局电话号码，Skype for Business 将在进行通过工号呼叫的用户的 PBX 呼叫者 ID 上显示该号码。 
    
- 创建一个或多个通过工位呼叫策略
    
- 为将启用通过工位电话呼叫的每个用户分配"通过工位呼叫"策略
    
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

    例如，以下 cmdlet 创建名为 ContosoUser1CvWP 的"通过工号呼叫"策略，要求用户使用管理员回拨号码，并设置该回拨号码为 1-555-789-1234。
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>向用户分配通过工位呼叫策略

- 键入以下 cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如，以下 cmdlet 将"通过工号呼叫"策略"ContosoUser1CvWP"分配给名为 **ContosoUser1 的用户**。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中规划通过工位呼叫](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

