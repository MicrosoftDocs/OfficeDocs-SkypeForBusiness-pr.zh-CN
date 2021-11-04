---
title: 为用户启用组内呼叫接听，并分配Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在呼叫组中为用户启用Skype for Business Server 企业语音，并分配组号码。
ms.openlocfilehash: c053ae4551ea5954f15261755c20afbf8a45f7b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759085"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>为用户启用组内呼叫接听，并分配Skype for Business

在呼叫组中为用户启用Skype for Business Server 企业语音，并分配组号码。

将呼叫接听组号码添加到呼叫等待通道表后，使用 SEFAUtil 工具将组号码分配给用户，并为其启用组内呼叫接听。

> [!NOTE]
> 在混合部署中，不要将组内呼叫接听组分配给在线用户。 联机用户不能参与组内呼叫接听。 也就是说，其他用户无法应答呼叫，也无法应答其他用户的呼叫。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>为用户分配组号码并启用组内呼叫接听

1. 使用管理员权限登录到安装了 SEFAUtil 工具的计算机。

2. 在命令行中运行：

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    例如，若要将组号 199 分配给用户：

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>另请参阅

[禁用用户的组分拣](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)