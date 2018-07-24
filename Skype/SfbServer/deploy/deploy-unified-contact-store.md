---
title: '部署统一的联系人存储中 Skype 业务服务器 '
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要： 启用统一的联系人存储中 Skype 业务服务器。
ms.openlocfilehash: 36515e9542a18d422254292b0cf2a2b4ef937178
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978219"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>部署统一的联系人存储中 Skype 业务服务器
 
**摘要：** 启用统一的联系人存储中 Skype 业务服务器。
  
启用统一的联系人存储中 Skype 业务服务器不需要任何拓扑设置。 要为用户启用统一的联系人存储库，需要：
  
- 启用统一的联系人存储库策略（将启用默认值）。
    
- 用户登录与 for Business 的 Skype 至少一次。
    
用户的联系人迁移，这种情况使用 Skype 为企业用户登录时自动发生之后，用户可以访问和管理其业务联系人 Skype 从 Skype 业务、 Outlook 2013 或 Outlook Web Access。 用户不需要登录到 Skype for Business Outlook 或 Outlook Web Access 中管理他们的联系人。
  
> [!IMPORTANT]
> 如果用户从登录 for Business 的 Skype 迁移后，联系人和组都可用并且保持最新，但用户无法管理 （即添加、 删除、 移动、 标记，取消标记，或修改） 这些联系人。 
  
## <a name="enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

当您部署业务服务器 Skype 并发布拓扑时，统一联系人存储库默认情况下启用为所有用户。 不需要执行任何其他操作来业务服务器部署 Skype 后启用统一的联系人存储库。 但是， **Set-csuserservicespolicy** cmdlet 可用于自定义哪些用户有统一联系人存储库可用。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

1. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。
    
2. 请执行以下任一操作：
    
   - 若要启用全局性针对所有 Skype 业务 Server 用户的统一联系人存储库，中间在 Windows PowerShell 命令行界面以下 cmdlet:
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 若要为特定站点的用户启用统一联系人存储，请在命令提示符中键入：
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例如：
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 若要按租户启用统一联系人存储，请在命令提示符中键入：
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例如：
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 若要为特定用户启用统一联系人存储，请在命令提示符中键入：
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 还可以使用用户别名或 SIP URI 代替用户显示名称。 
  
    例如：
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。
  
## <a name="migrate-users-to-unified-contact-store"></a>将用户迁移到统一联系人存储

用户的联系人都将自动迁移到 Exchange 2013 服务器时用户：
  
- 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。
    
- 已设置 Exchange 2013 邮箱和已登录该邮箱至少一次。
    
- 使用 Skype 业务富客户端中的日志。
    
如果用户登录 Lync 或早期客户端，或者用户未连接到 Exchange 2013 服务器，请忽略用户服务策略和用户的联系人保留业务服务器在 Skype。
  
您可以通过以下任一方法来确定是否已迁移用户的联系人： 
  
- 在客户端计算机上检查以下注册表项：
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< SIP URL\>\UCS
    
    如果用户的联系人存储在 Exchange 2013 中，此项包含 InUCSMode 的值为 2165年的值。
    
- 运行**Test-csunifiedcontactstore** cmdlet。 在为业务 Server 命令行管理程序命令行 Skype，键入：
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    如果**Test-csunifiedcontactstore**成功，用户的联系人迁移到统一联系人存储库。
    
## <a name="roll-back-migrated-users"></a>回滚已迁移用户

如果需要回滚统一的联系人存储功能，但仅当您将用户移回到 Exchange 2010 或 Lync Server 2010 回滚联系人。 若要回滚，禁用对用户策略，然后再运行**Invoke-csucsrollback** cmdlet。 只需运行**Invoke-csucsrollback**本身不足以确保永久回滚，因为如果不禁用此策略，则将再次启动统一联系人存储库迁移。 例如，如果用户回滚原因 Exchange 2013 回滚到 Exchange 2010，然后将该用户的邮箱移到 Exchange 2013，统一联系人存储库迁移将启动再次七天后回滚，只要统一的联系人存储仍用户服务策略中为用户启用。
  
**Move-csuser** cmdlet 自动回滚用户的联系人存储从 Exchange 2013 到 Skype 业务服务器在下列情况下：
  
- 当用户移动 Skype 业务服务器到 Microsoft Lync Server 2013 或 Lync Server 2010。 
    
- 当用户交叉迁移，如当用户从移动 Skype 业务 online 到 Skype 的业务服务器的本地，反之亦然。
    
如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：
  
- 如果用户的联系人迁移到 Exchange 2013，然后迁移后，导入相同的数据之前, 导出的联系人列表会损坏的统一联系人存储数据和联系人列表。
    
- 如果后将用户迁移到 Exchange 2013 导出用户数据，回滚迁移，则由于某种原因，在迁移后导入的数据，统一的联系人存储数据和联系人列表会被破坏。
    
> [!IMPORTANT]
> 将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保的 Skype 业务服务器管理员已先回滚 Skype 的企业服务器用户联系人从 Exchange 2013 到 Skype 的业务服务器。 回滚统一的联系人存储联系人到 Skype 业务服务器，请参阅过程"回滚统一的联系人存储联系人从 Exchange 2013 收件人 Skype for Business Server，"后面本节中。 
  
 **如何回滚用户联系人：** 如果您使用**Move-csuser** cmdlet 的业务服务器 2015 Skype 和 Lync Server 2010 之间移动用户，因为**Move-csuser** cmdlet 自动回滚统一的联系人存储从 Skype 的移动用户时，您可以跳过这些步骤到 Lync Server 2010 的业务服务器 2015。 **Move-csuser**不禁用统一联系人存储库策略，因此当用户移回至 Skype 的业务服务器 2015年重复迁移到统一联系人存储库。
  

