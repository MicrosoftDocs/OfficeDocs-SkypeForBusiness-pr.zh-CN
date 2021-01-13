---
title: 为用户启用组内呼叫接听，在 Skype for Business 中分配组号码
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在 Skype for Business Server 企业语音为用户启用组内呼叫企业语音分配组号码。
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830962"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>为用户启用组内呼叫接听，在 Skype for Business 中分配组号码

在 Skype for Business Server 企业语音为用户启用组内呼叫企业语音分配组号码。

将呼叫接听组号码添加到呼叫等待通道表后，使用 SEFAUtil 工具将组号码分配给用户，并为其启用组内呼叫分拣。

> [!NOTE]
> 在混合部署中，不要将组内呼叫接听组分配给在线用户。 联机用户不能参与组内呼叫接听。 也就是说，其他用户无法应答其呼叫，并且无法应答其他用户的呼叫。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>为用户分配组号码并启用组内呼叫接听

1. 使用管理员权限登录到安装 SEFAUtil 工具的计算机。

2. 在命令行中运行：

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如，若要将组号 199 分配给用户：

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>另请参阅

[禁用用户的组分拣](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

