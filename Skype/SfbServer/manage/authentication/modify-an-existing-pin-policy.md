---
title: 修改 Skype for Business Server 中的现有 PIN 策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 摘要：修改 Skype for Business Server 中的现有 PIN 策略。
ms.openlocfilehash: d97d535c8930c1b9155da4f8c35171f2b70692e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828352"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>修改 Skype for Business Server 中的现有 PIN 策略
 
**摘要：** 修改 Skype for Business Server 中的现有 PIN 策略。
  
可以使用 **"PIN** 策略"选项卡向使用 IP 电话 (Skype for Business) PIN 身份验证提供个人标识号。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。
  
按照以下步骤修改用户级别或站点级别的 PIN 策略。 
  
### <a name="to-modify-an-existing-pin-policy"></a>修改现有 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在 **"PIN 策略"** 页上，单击某个策略，再单击 **"** 编辑"，然后单击"**显示详细信息"。**
    
5. 在“编辑 PIN 策略”的“最小 PIN 长度”中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
6. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
7. 如果选中了“指定最大登录尝试数”复选框，请在“最大登录尝试次数”中键入或选择希望允许的最大登录尝试次数。
    
8. 要使 PIN 过期，请选中“启用 PIN 有效期”复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
9. 如果选中了“启用 PIN 有效期”复选框，请在“PIN 有效期(天)”中键入或选择 PIN 保持有效的天数。
    
10. 在“PIN 历史记录计数”中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
11. 要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 我们建议您不要允许使用通用模式。 
  
12. 单击“提交”。
    

