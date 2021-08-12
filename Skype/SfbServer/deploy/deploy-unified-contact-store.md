---
title: '在统一联系人存储中Skype for Business Server '
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
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要：在联系人集中启用统一Skype for Business Server。
ms.openlocfilehash: 6311b760daf2c397cfc5c75ddeb5e28fd2fb6503c0c2db11ef9ed6de71a7562e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310011"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>在统一联系人存储中Skype for Business Server
 
**摘要：** 在统一联系人存储中Skype for Business Server。
  
在统一的联系人Skype for Business Server不需要任何拓扑设置。 为用户启用统一联系人存储：
  
- 启用统一的联系人存储库策略（将启用默认值）。
    
- 用户至少使用 Skype for Business登录一次。
    
迁移用户的联系人后（当用户使用 Skype for Business 登录时，会自动进行迁移，然后用户可以从 Skype for Business、Outlook 2013 或 Outlook Web Access 访问和管理其 Skype for Business 联系人。 用户无需登录到 Skype for Business，Outlook Web Access Outlook联系人。
  
> [!IMPORTANT]
> 如果用户在迁移后从 Skype for Business 登录，则联系人和组可用且是最新的，但该用户无法管理 (，即添加、删除、移动、标记、取消标记或修改) 联系人。 
  
## <a name="enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

在部署Skype for Business Server并发布拓扑时，默认情况下会为所有用户启用统一联系人存储。 部署统一联系人存储后，无需执行任何其他操作Skype for Business Server。 但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一的联系人存储库。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一的联系人存储库

1. 启动命令行Skype for Business Server：**单击"** 开始"，单击"所有程序 **"，Skype for Business"，** 然后单击"Skype for Business Server **命令行管理程序"。** 
    
2. 执行下列任意操作：
    
   - 若要为所有用户全局启用统一的联系人Skype for Business Server，请通过命令行界面Windows PowerShell以下 cmdlet：
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 若要为特定站点上的用户启用统一的联系人存储，在提示符下键入：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 若要按租户启用统一联系人存储，在提示符下键入：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 若要为特定用户启用统一的联系人存储，在提示符下键入：
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 还可以使用用户别名或 SIP URI 代替用户显示名称。 
  
    例如：
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。
  
## <a name="migrate-users-to-unified-contact-store"></a>将用户迁移到统一的联系人存储

当用户处于以下情况时，会自动将用户的联系人迁移到 Exchange 2013 服务器：
  
- 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。
    
- 已使用 Exchange 2013 邮箱进行预配，并且至少已登录邮箱一次。
    
- 使用富客户端Skype for Business登录。
    
如果用户使用 Lync 或早期客户端登录，或者用户未连接到 Exchange 2013 服务器，则用户服务策略将被忽略，并且用户的联系人仍保留在 Skype for Business Server 中。
  
您可以通过以下任一方法来确定是否已迁移用户的联系人： 
  
- 在客户端计算机上检查以下注册表项：
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS
    
    如果用户的联系人存储在 Exchange 2013 中，则此键包含值为 2165 的 InUCSMode 值。
    
- 运行 **Test-CsUnifiedContactStore** cmdlet。 在命令行Skype for Business Server命令行中键入：
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    如果 **Test-CsUnifiedContactStore** 成功，表明用户的联系人已迁移到统一联系人存储中。
    
## <a name="roll-back-migrated-users"></a>回滚迁移的用户

如果需要回滚统一的联系人存储功能，则仅在将用户移回 Exchange 2010 或 Lync Server 2010 时回滚联系人。 要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。 只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。 例如，如果用户由于 Exchange 2013 回滚到 Exchange 2010 而回滚，然后用户的邮箱移动到 Exchange 2013，则只要在用户服务策略中仍为用户启用统一联系人存储，统一联系人存储迁移将在回滚七天后再次启动。
  
**在下列情况下，Move-CsUser** cmdlet 会自动将用户的联系人存储从 Exchange 2013 回滚到 Skype for Business Server：
  
- 将用户从 Skype for Business Server Microsoft Lync Server 2013 或 Lync Server 2010 时。 
    
- 当用户跨内部部署迁移时（例如，当用户从 Skype for Business Online Skype for Business Server本地迁移时，反之亦然。
    
如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：
  
- 如果在将用户的联系人迁移到 Exchange 2013 之前导出联系人列表，然后在迁移后导入相同的数据，则统一联系人存储数据和联系人列表将损坏。
    
- 如果在将用户迁移到 Exchange 2013 之后导出用户数据，回滚迁移，然后出于某种原因在迁移后导入数据，则统一联系人存储数据和联系人列表将损坏。
    
> [!IMPORTANT]
> 在将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保 Skype for Business Server 管理员首先将 Skype for Business Server 用户联系人从 Exchange 2013 回滚到 Skype for Business Server。 若要将统一的联系人存储联系人回滚到 Skype for Business Server，请参阅本节稍后介绍的过程"将统一联系人存储联系人从 Exchange 2013 回滚到 Skype for Business Server"。 
  
 **如何回滚用户联系人：** 如果使用 **Move-CsUser** cmdlet 在 Skype for Business Server 2015 和 Lync Server 2010 之间移动用户，可以跳过这些步骤，因为 **Move-CsUser** cmdlet 在将用户从 Skype for Business Server 2015 移动到 Lync Server 2010 时会自动回滚统一联系人存储。 **Move-CsUser** 不会禁用统一的联系人存储策略，因此，如果用户移回 2015 年 10 月，则迁移到统一联系人存储Skype for Business Server重复。
  

