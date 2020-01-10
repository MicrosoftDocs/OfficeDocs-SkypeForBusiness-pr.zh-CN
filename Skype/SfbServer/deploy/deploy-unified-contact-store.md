---
title: '在 Skype for Business 服务器中部署统一联系人存储 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要：在 Skype for Business 服务器中启用统一联系人存储。
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003062"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署统一联系人存储
 
**摘要：** 在 Skype for Business 服务器中启用统一联系人存储。
  
在 Skype for Business 服务器中启用统一联系人存储不需要任何拓扑设置。 要为用户启用统一的联系人存储库，需要：
  
- 启用统一的联系人存储库策略（将启用默认值）。
    
- 用户至少能用 Skype for Business 登录。
    
迁移用户的联系人后，当用户使用 Skype for Business 登录时，将自动发生此情况，用户可以从 Skype for Business、Outlook 2013 或 Outlook Web Access 访问和管理其 Skype for business 联系人。 用户不必登录到 Skype for Business 即可从 Outlook 或 Outlook Web Access 管理其联系人。
  
> [!IMPORTANT]
> 如果用户在迁移后从 Skype for Business 登录，则 "联系人" 和 "组" 可用且是最新的，但用户无法管理（即添加、删除、移动、标记、取消标记或修改）这些联系人。 
  
## <a name="enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

部署 Skype for Business 服务器并发布拓扑时，默认情况下为所有用户启用 "统一联系人存储"。 部署 Skype for Business 服务器后，无需执行任何其他操作即可启用统一联系人存储。 但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一联系人存储。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

1. 启动 Skype for Business 服务器命令行管理程序：单击 "**开始**"，单击 "**所有程序**"，单击 " **skype**for Business"，然后单击 " **skype for business 服务器管理外壳**"。
    
2. 请执行以下任一操作：
    
   - 若要为所有 Skype for Business Server 用户全局启用统一联系人存储，请在 Windows PowerShell 命令行界面上使用以下 cmdlet：
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 若要为特定站点的用户启用统一联系人存储，请在命令提示符中键入：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 若要按租户启用统一联系人存储，请在命令提示符中键入：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 若要为特定用户启用统一联系人存储，请在命令提示符中键入：
    
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
    > 在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”的新每用户策略，并将 UcsAllowed 标记设置为 True。 第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。
  
## <a name="migrate-users-to-unified-contact-store"></a>将用户迁移到统一联系人存储

当用户执行以下操作时，用户的联系人会自动迁移到 Exchange 2013 服务器：
  
- 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。
    
- 已使用 Exchange 2013 邮箱进行了设置，并且至少已登录到邮箱一次。
    
- 使用 Skype for Business 胖客户端登录。
    
如果用户使用 Lync 或更早的客户端登录，或者如果用户未连接到 Exchange 2013 服务器，则将忽略用户服务策略，并且用户的联系人保留在 Skype for Business 服务器中。
  
您可以通过以下任一方法来确定是否已迁移用户的联系人： 
  
- 在客户端计算机上检查以下注册表项：
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    如果用户的联系人存储在 Exchange 2013 中，则此注册表项包含值为2165的 InUCSMode 值。
    
- 运行 **Test-CsUnifiedContactStore** cmdlet。 在 Skype for Business Server Management Shell 命令行中，键入：
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    如果 **Test-CsUnifiedContactStore** 成功，表明用户的联系人已迁移到统一联系人存储中。
    
## <a name="roll-back-migrated-users"></a>回滚已迁移用户

如果需要回滚 "统一联系人存储" 功能，请仅在将用户移回 Exchange 2010 或 Lync Server 2010 时，才返回联系人。 要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。 只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。 例如，如果由于 Exchange 2013 回退到 Exchange 2010 而回滚用户，然后将用户的邮箱移动到 Exchange 2013，则在回滚后的七天内将再次启动统一联系人存储迁移，只要有统一联系人存储在用户服务策略中仍为用户启用。
  
在以下情况下， **move-csuser** cmdlet 会将用户的联系人存储从 Exchange 2013 自动回退到 Skype For business 服务器：
  
- 当用户从 Skype for Business 服务器移动到 Microsoft Lync Server 2013 或 Lync Server 2010 时。 
    
- 当用户在本地迁移时，例如，当用户从 Skype for Business Online 移动到本地 Skype for business 服务器时，反之亦然。
    
如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：
  
- 如果在将用户联系人迁移到 Exchange 2013 之前导出联系人列表，然后在迁移后导入相同的数据，则统一联系人存储数据和联系人列表将损坏。
    
- 如果你在将用户迁移到 Exchange 2013 后导出用户数据，请回退迁移，然后，出于某些原因，在迁移后导入数据时，统一联系人存储数据和联系人列表将损坏。
    
> [!IMPORTANT]
> 将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保 Skype for Business 服务器管理员首先将 Skype for business Server 用户联系人从 Exchange 2013 回退到 Skype for Business企业服务器。 若要将统一联系人存储联系人回滚到 Skype for business 服务器，请参阅本部分后面部分中的过程 "将统一联系人存储联系人从 Exchange 2013 回滚到 Skype for business 服务器"。 
  
 **如何回退用户联系人：** 如果你使用**move-csuser** Cmdlet 在 Skype For business server 2015 和 Lync server 2010 之间移动用户，则可以跳过这些步骤，因为**move-csuser** cmdlet 会在将用户从 Skype for business Server 2015 移动到 Lync Server 2010 时自动回退 "统一联系人存储"。 **Move-move-csuser**不会禁用统一联系人存储策略，因此如果用户移回 Skype For business Server 2015，则迁移到统一联系人存储将会重现。
  

