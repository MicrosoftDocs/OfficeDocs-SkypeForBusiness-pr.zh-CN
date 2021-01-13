---
title: 在 Skype for Business Server 中创建新的 PIN 策略
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
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 摘要：在 Skype for Business Server 中创建新的 PIN 策略。
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828402"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>在 Skype for Business Server 中创建新的 PIN 策略
 
**摘要：** 在 Skype for Business Server 中创建新的 PIN 策略。
  
可以使用 **"PIN** 策略"页向使用 IP 电话 (Skype for Business (PIN) 身份验证提供个人标识号。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。
  
按照以下步骤创建用户级别或站点级别的 PIN 策略。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>创建用户或站点 PIN 策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。
    
4. 在“PIN 策略”页上，单击“新建”，然后执行下列操作之一：
    
   - 要创建用户级别的策略，请单击“用户策略”。在“新建 PIN 策略”的“名称”中，键入描述该策略的名称。
    
   - 要创建站点级别的策略，请单击“站点策略”。在“选择站点”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“确定”。
    
5. 在“说明”字段中，键入 PIN 策略的说明。
    
6. 在“最小 PIN 长度”字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
7. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
8. 如果选中了“指定最大登录尝试数”复选框，请在“最大登录尝试次数”中键入或选择希望允许的最大登录尝试次数。
    
9. 要使 PIN 过期，请选中“启用 PIN 有效期”复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
10. 如果选中了“启用 PIN 有效期”复选框，请在“PIN 有效期(天)”中键入或选择 PIN 保持有效的天数。
    
11. 在“PIN 历史记录计数”中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
12. 若要在 PIN 中允许数字的常见模式，例如"1234"和"8888"，请选中"允许通用 **模式"复选框** 。 如果未选择此选项，则仅允许使用数字的复杂模式。 默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 我们建议您不要允许使用通用模式。 
  
13. 单击“提交”。
    

