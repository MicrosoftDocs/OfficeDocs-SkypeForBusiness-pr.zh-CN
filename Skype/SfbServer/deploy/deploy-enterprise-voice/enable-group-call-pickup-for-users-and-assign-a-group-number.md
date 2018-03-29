---
title: 在 Skype for Business 2015 中为用户启用组内呼叫应答并分配组号码
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 允许用户使用在 Skype 的组调用取货业务服务器企业语音，并指定一组数。
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a>在 Skype for Business 2015 中为用户启用组内呼叫应答并分配组号码
 
允许用户使用在 Skype 的组调用取货业务服务器企业语音，并指定一组数。
  
呼叫分拣组电话号码添加到调用公园轨道表后，您使用 SEFAUtil 工具向用户分配组数字并为其启用组调用装货。
  
> [!NOTE]
> 在混合部署中，不要给在线托管的用户分配组调用拾取组。 联机托管的用户无法参与组调用装货。 也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>指定组号，为用户启用组调用装货

1. 使用管理员权限登录安装了 SEFAUtil 工具的计算机。
    
2. 在该命令行处，运行：
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如，将组号码 199 分配给用户：
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a>另请参阅

#### 

[用户的禁用组装货](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

