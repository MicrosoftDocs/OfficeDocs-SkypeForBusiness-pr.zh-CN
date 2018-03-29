---
title: 在 Skype for Business Server 2015 中创建新的 PIN 策略
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 摘要： 创建的新 PIN 策略在 Skype 业务服务器 2015年。
ms.openlocfilehash: d04c19f09830b971300d2ff9bf4a8a1d93994f7c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建新的 PIN 策略
 
**摘要：**为业务服务器 2015年，Skype 在创建的新 PIN 策略。
  
**PIN 策略**页可用于连接到与 IP 电话业务的 Skype 为用户提供个人身份验证号码 (PIN) 身份验证。 要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。
  
按照以下步骤创建用户级别或站点级别的 PIN 策略。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>创建用户或站点 PIN 策略

1.  从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。
    
4. 在“PIN 策略”****页上，单击“新建”****，然后执行下列操作之一：
    
   - 要创建用户级别的策略，请单击“用户策略”****。在“新建 PIN 策略”****的“名称”****中，键入描述该策略的名称。
    
   - 要创建站点级别的策略，请单击“站点策略”****。在“选择站点”****搜索字段中，键入要为其创建策略的站点的全部或部分名称。在得到的站点列表中，单击所需的站点，然后单击“确定”****。
    
5. 在“说明”****字段中，键入 PIN 策略的说明。
    
6. 在“最小 PIN 长度”****字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。
    
7. 为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”****复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。
    
8. 如果选中了“指定最大登录尝试数”****复选框，请在“最大登录尝试次数”****中键入或选择希望允许的最大登录尝试次数。
    
9. 要使 PIN 过期，请选中“启用 PIN 有效期”****复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。
    
10. 如果选中了“启用 PIN 有效期”****复选框，请在“PIN 有效期(天)”****中键入或选择 PIN 保持有效的天数。
    
11. 在“PIN 历史记录计数”****中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。
    
12. 要允许在 PIN 中使用数字的通用模式，如“1234”和“8888”，请选中“允许通用模式”****复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。
    
    > [!IMPORTANT]
    > 我们建议您不要允许使用通用模式。 
  
13. 单击“**提交**”。
    

