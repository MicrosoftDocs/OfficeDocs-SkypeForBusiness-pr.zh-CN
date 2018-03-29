---
title: 在 Skype for Business Server 2015 中部署统一联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要： 使业务服务器 2015年的统一的联系人存储在 Skype。
ms.openlocfilehash: fbe94023a6693f7d016d2963d49d88646c9b969e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署统一联系人存储
 
**摘要：**启用业务服务器 2015年的统一的联系人存储在 Skype。
  
启用统一的联系人存储在 Skype 的业务服务器 2015年不需要任何拓扑结构设置。 要为用户启用统一的联系人存储库，需要：
  
- 启用统一的联系人存储库策略（将启用默认值）。
    
- 用户登录 Skype 业务与至少一次。
    
用户的联系人迁移，它会自动在用户登录 Skype 业务时之后，用户可以访问和管理其 Skype 业务联系人从 Skype 业务、 Outlook 2013 或 Outlook Web Access。 用户不需要登录到业务来管理他们的联系人从 Outlook 或 Outlook Web Access 的 Skype。
  
> [!IMPORTANT]
> 如果用户在登录 Skype 业务从迁移后，联系人和组将可用并保持最新，但用户不能管理 （即，添加，删除，移动、 标记、 取消标签，或修改） 这些联系人。 
  
## <a name="enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

当您部署 Skype 业务服务器 2015年并发布拓扑时，统一联系人存储库是为所有用户默认启用的。 您不需要执行任何其他操作的业务服务器 2015年部署 Skype 之后启用统一的联系人存储库。 但是，可以使用**一组 CsUserServicesPolicy** cmdlet 可以自定义哪些用户有统一的可用联系人存储库。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 请执行以下任一操作：
    
   - 若要启用所有业务服务器用户的 Skype 为全局统一联系人存储库，间以下 cmdlet 在 Windows PowerShell 命令行接口：
    
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
    > 在前面的示例中，第一个命令创建新的每用户策略命名 UCS 已启用用户与 UcsAllowed 标志设置为 True。 第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。
  
## <a name="migrate-users-to-unified-contact-store"></a>将用户迁移到统一联系人存储

用户的联系人会自动迁移到 Exchange 2013 服务器时使用：
  
- 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。
    
- 已设置与 Exchange 2013 邮箱和已登录到该邮箱至少一次。
    
- 在通过 Skype 业务丰富的客户端的日志。
    
如果用户登录 Lync 或早期客户端，或用户未连接到 Exchange 2013 服务器，用户服务策略将被忽略，并在 Skype 保持业务服务器的用户的联系人。
  
您可以通过以下任一方法来确定是否已迁移用户的联系人： 
  
- 在客户端计算机上检查以下注册表项：
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< SIP URL\>\UCS
    
    用户的联系人存储在 Exchange 2013，如果此项包含值为 2165 InUCSMode 的值。
    
- 运行**测试 CsUnifiedContactStore** cmdlet。 在 Skype 业务服务器管理外壳程序命令行，键入：
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    如果成功**测试 CsUnifiedContactStore** ，用户的联系人已迁移到统一的联系人存储库中。
    
## <a name="roll-back-migrated-users"></a>回滚已迁移用户

如果需要回滚统一的联系人存储功能，只有当您移动用户返回到 Exchange 2010 或 Lync Server 2010 回滚联系人。 若要回滚，禁用该用户的策略，然后运行**调用 CsUcsRollback** cmdlet。 只需运行**调用 CsUcsRollback**仅不足以确保永久回滚，因为如果不启用此策略时将再次启动统一联系人存储库迁移。 例如，如果用户回滚原因 Exchange 2013 回滚到 Exchange 2010，然后将该用户的邮箱移动到 Exchange 2013，统一联系人存储库迁移将启动再次七天之后回滚，只要统一的联系人存储仍然会启用用户服务策略中的用户。
  
**移动 CsUser** cmdlet 自动回滚用户的联系人存储库从 Exchange 2013 到 Skype 业务服务器 2015年在以下情况下：
  
- 当用户移动 Skype 的业务服务器 2015年到 Microsoft Lync Server 2013 或 Lync Server 2010。 
    
- 交叉的场所，例如，当用户从移动 Skype 的在线业务到 Skype 的业务服务器 2015年内部，迁移用户时，反之亦然。
    
如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：
  
- 如果您导出联系人列表之前用户的联系人都将迁移到 Exchange 2013，然后，迁移后，导入相同的数据，会破坏统一的联系人存储库数据和联系人列表。
    
- 如果您将用户迁移到 Exchange 2013 之后导出用户数据，回滚迁移，然后在迁移后导入的数据由于某种原因，统一的联系人存储数据和联系人列表会被破坏。
    
> [!IMPORTANT]
> 从 Exchange 2013 Exchange 邮箱移动到 Exchange 2010 之前，Exchange 管理员必须确保，Skype 业务服务器管理员已首先回滚 Skype 业务服务器用户联系人从 Exchange 2013 到 Skype 的企业服务器。 回滚统一联系人存储联系人到 Skype 业务服务器，请参阅"过程回滚统一联系人存储联系人从 Exchange 2013 到 Skype for 业务服务器，"以后在此部分中。 
  
 **如何回滚用户联系人：**如果您使用**移动 CsUser** cmdlet 的业务服务器 2015 Skype 和 Lync Server 2010 之间移动用户，因为**移动 CsUser** cmdlet 自动回滚统一联系人存储库从 Skype 为移动用户时，您可以跳过这些步骤业务服务器到 Lync Server 2010 中的 2015 年。 **移动 CsUser**不会禁用统一联系人的存储策略，因此如果用户将移回 Skype 的业务服务器 2015年重复迁移到统一的联系人存储库。
  

