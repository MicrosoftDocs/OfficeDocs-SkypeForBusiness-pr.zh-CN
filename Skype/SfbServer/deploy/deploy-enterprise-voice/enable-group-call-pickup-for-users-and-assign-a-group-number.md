---
title: 为用户启用组呼叫分拣和分配 Skype for Business 中的一组数
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 为用户启用组中 Skype 调用的分拣业务 Server 企业语音，并分配组数。
ms.openlocfilehash: 94498732ef9bdc66130a6c15cbf342681c48f036
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881845"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>为用户启用组呼叫分拣和分配 Skype for Business 中的一组数

为用户启用组中 Skype 调用的分拣业务 Server 企业语音，并分配组数。

将呼叫分拣组号码添加到呼叫寄存通道表后，您使用 SEFAUtil 工具将组号码分配给用户和组呼叫分拣启用。

> [!NOTE]
> 在混合部署中，现在将一组呼叫分拣组分配给驻留联机用户。 联机驻留的用户不能参与组呼叫分拣。 也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>指定一组数并为用户启用组呼叫分拣

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

[用户的禁用组分拣](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

