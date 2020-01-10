---
title: 为用户启用组呼叫装货，并在 Skype for Business 中分配组号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在 Skype for Business Server Enterprise Voice 中启用组呼叫装货的用户，并分配组号码。
ms.openlocfilehash: 8ded9fbf7e9a9c8034684c1477c6aad92bfc9e5f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002542"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>为用户启用组呼叫装货，并在 Skype for Business 中分配组号码

在 Skype for Business Server Enterprise Voice 中启用组呼叫装货的用户，并分配组号码。

将呼叫挑选组号码添加到 "呼叫驻留的轨道" 表后，使用 SEFAUtil 工具将组号码分配给用户并为其启用组呼叫装货。

> [!NOTE]
> 在混合部署中，不要向处于联机状态的用户分配组呼叫装货组。 处于联机状态的用户不能参与组呼叫装货。 也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>分配组号码并为用户启用组呼叫装货

1. 使用管理员权限登录安装了 SEFAUtil 工具的计算机。

2. 在该命令行处，运行：

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如，将组号码 199 分配给用户：

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>另请参阅

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

