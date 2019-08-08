---
title: 通过 Skype for Business 服务器中的工作部署呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '摘要: 了解如何在某些或所有用户的 Skype for Business 服务器中通过工作部署呼叫。'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234252"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>通过 Skype for Business 服务器中的工作部署呼叫
 
**摘要:** 了解如何通过适用于部分或全部用户的 Skype for Business 服务器中的工作部署呼叫。
  
使用这些步骤通过适用于您的用户的工作来部署呼叫。 [通过 Skype For Business Server 中的工作计划呼叫计划](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论了规划注意事项。 在早期版本的 Lync Server 远程呼叫控制中, 支持用户使用 Lync Server 控制其 PBX 手机的功能。 在 Skype for Business 服务器中, 此功能已替换为 "通过工作通话"。 
  
## <a name="prerequisites-for-call-via-work"></a>通过工作进行通话的先决条件

通过工作进行呼叫使用统一通信 Web API (UCWA), 该 API 自动安装在所有 Skype for business 服务器前端服务器上。 若要允许用户通过工作进行呼叫, 还必须满足以下先决条件: 
  
- 你必须已部署中介服务器, 或者作为前端服务器的一部分, 或者作为独立角色进行部署。 您还必须部署 IP-PBX 网关。
    
- 通过工作启用呼叫的所有用户必须在 PBX 电话系统上进行直接向内拨号 (已执行)。 
    
- 您必须通过适用于企业语音的工作用户启用所有呼叫。 执行此操作时, 必须为每位用户将 Skype for Business 的号码配置为相应的 PBX 电话系统对应的 "号码"。 
    
- 通过工作进行呼叫的所有用户都必须在其 Skype for Business 客户端的 "**高级连接**" 选项中选中 "**自动配置**"。 这使客户能够发现 UCWA Url。 **自动配置**为默认选择。
    
- 对于每个通过工作用户拨打的电话, 启用呼叫转接和同时拨打。 
    
- 对于每个通过工作用户进行的呼叫, 请确保已启用电话拨入式会议和会议拨出。 这使这些用户能够进入和注销 Skype for Business 会议。
    
- 确保通过工作用户对每个呼叫禁用委派、团队呼叫和响应组。
    
## <a name="deploy-call-via-work"></a>部署单位电话呼叫

先决条件就绪后，请执行以下操作：
  
- 为你的部署创建全球电话号码 Skype for Business 显示在通过工作电话进行呼叫的用户的 PBX 呼叫方 ID 上。 
    
- 通过工作策略创建一个或多个通话
    
- 通过工作策略将呼叫分配给每个用户, 这些用户将通过工作进行呼叫
    
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

    例如, 以下 cmdlet 通过名为 ContosoUser1CvWP 的工作策略创建呼叫, 要求用户使用管理员回拨号码, 并将该回拨号码设置为1-555-789-1234。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>通过工作策略向用户分配呼叫

- 键入以下 cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如, 以下 cmdlet 通过工作策略 "ContosoUser1CvWP" 将调用分配给名为**ContosoUser1**的用户。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另请参阅

[通过 Skype for Business Server 中的工作计划呼叫计划](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

