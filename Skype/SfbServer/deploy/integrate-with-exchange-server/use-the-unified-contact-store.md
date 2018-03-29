---
title: Skype 业务服务器 2015 使用统一的联系人存储库的配置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 摘要： 配置业务服务器 2015年的统一的联系人存储的 Exchange Server 2016年或 Exchange Server 2013年和 Skype。
ms.openlocfilehash: 479032425c8a3d2d66bd341f54908a071dd5480d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-the-unified-contact-store"></a>Skype 业务服务器 2015 使用统一的联系人存储库的配置
 
**摘要：**配置业务服务器 2015年的统一的联系人存储的 Exchange Server 2016年或 Exchange Server 2013年和 Skype。
  
使用统一的联系人存储库，用户维护单个联系人列表，然后在多个应用程序，包括商业、 Microsoft Outlook 2013，和 Microsoft Outlook Web App 2013 Skype 可用的联系人。 当您启用统一联系人存储库用户，用户的联系人未存储在 Skype 业务服务器 2015年和根据需要进行检索。 相反，他 / 她的联系人存储在 Exchange Server 2016年或 Exchange Server 2013年，并通过使用 Exchange Web 服务来检索。
  
> [!NOTE]
> 从技术上讲，两个用户的 Exchange 邮箱中的文件夹中存储联系人信息。 自己的联系人存储在一个名为 Skype，这是显示给最终用户; 商务联系人的文件夹对最终用户是不可见的子文件夹中存储联系人有关的元数据。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>为用户启用统一的联系人存储库

如果已经配置了业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013 Skype 之间的服务器到服务器进行身份验证，然后您也启用了统一的联系人存储库;不不需要任何额外的服务器配置。 但是，若要将用户的联系人移至统一的联系人存储库，则需要执行额外的用户帐户配置。 默认情况下，用户联系人保留在 Skype 业务服务器而不是在统一的联系人存储库。
  
通过 Skype 业务服务器用户服务策略管理对统一联系人存储库的访问。 用户服务器策略只具有一个属性 (UcsAllowed)；此属性用于确定存储用户联系人的位置。 如果某个用户是由 UcsAllowed 设置为 True ($True) 的用户服务策略管理的，则该用户的联系人将存储在统一的联系人存储库中。 如果用户由用户服务已将 UcsAllowed 设置为 False ($False)，然后他或她的联系人将存储在 Skype 业务服务器的策略。
  
当安装 Skype 业务服务器上时，也同时安装 （在全球范围内配置） 的单用户服务策略。 此策略中的 UcsAllowed 值将设置为 True，这意味着在默认情况下，用户联系人将存储在统一联系人存储中（假设已部署和配置它）。 若要将所有用户联系人迁移到统一联系人存储，根本不必执行任何操作。 
  
如果您不想将所有联系人都迁移到统一联系人存储，您可以通过在全局策略中将 UcsAllowed 属性设置为 False 来对所有用户禁用统一联系人存储：
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

在禁用统一联系人存储库中的全局策略后可以创建允许使用的统一的联系人存储库; 一个每用户策略这使您可以统一联系人存储库中保持其联系人，同时其他用户继续需要其联系人的 Skype 业务服务器的某些用户。 可通过使用与以下命令类似的命令来创建每用户的用户服务策略：
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

在创建新的策略后，您必须将此策略分配给应有权访问统一的联系人存储库的任何用户。可通过使用与以下内容类似的命令来将每用户策略分配给用户：
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

已分配该策略后，将开始 Skype 业务服务器迁移到统一的联系人存储库的用户的联系人。 迁移完成后，用户将具有他或她为业务服务器而不是 Skype 在 Exchange 存储的联系人。 如果用户登录到恰好 Lync 2013 时间迁移完成，将出现一个消息框，将要求他或她 Skype 为企业注销并重新登录才能完成该过程。 如果未向用户分配此每用户策略，则用户的联系人不会存储到统一联系人存储中。 这是因为这些用户由全球政策，并使用统一的联系人存储库的全局策略中已禁用。
  
您可以验证该用户的联系人成功已迁移到统一联系人存储库通过为业务服务器管理外壳程序运行[测试 CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet 从 Skype 内：
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

如果 Test-CsUnifiedContactStore 成功，则表示已将用户 sip:kenmyer@litwareinc.com 的联系人迁移到统一的联系人存储库中。
  
## <a name="rolling-back-the-unified-contact-store"></a>回滚统一的联系人存储库

如果您需要删除用户的联系人联系的统一存储 （例如，如果用户需要在 Microsoft Lync Server 2010 上重新连接，并因此不能使用统一的联系人存储库） 必须做两件事。 首先，您必须为用户分配一个新的用户服务策略，此策略禁止将联系人存储在统一的联系人存储库中。 （也就是说，策略其中 UcsAllowed 属性已设置为 $False。）如果没有这样的策略，您可以创建使用与以下类似的命令：
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

然后，可通过使用与以下内容类似的命令分配此新的每用户策略 (NoUnifiedContactStore)：
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上面的命令将新策略分配给用户 Ken Myer，并且还阻止将 Ken 的联系人迁移到统一的联系人存储库中。
  
> [!NOTE]
> 在某些情况下，只需取消分配用户的当前用户服务策略即可达到相同的效果。 例如，假定 Ken Myer 具有启用统一的联系人存储库的每用户用户服务策略，但您的全局策略禁止使用统一的联系人存储库。 在此情况下，您可以取消分配 Ken 的每用户服务策略。 在执行此操作后，Ken 将自动由全局策略管理，因此他将不再能够访问统一的联系人存储库。 不指派先前指定每个用户的策略，对使用同一命令，如下所示在前，但这一次将 PolicyName 参数设置为空值： 授予 CsUserServicesPolicy-标识"鸿波"-PolicyName $Null 
  
在使用统一的联系人存储库时，请务必记住术语“阻止将 Ken 的联系人迁移到统一的联系人存储库中”。 仅为 Ken 分配一个新的用户服务策略并不会将其联系人从统一的联系人存储库中移出。 当用户登录 Skype 业务服务器时，系统将检查该用户的用户服务策略，以查看是否应该统一联系人存储库中保留他 / 她的联系人。 如果回答为“是”（即，在 UcsAllowed 属性设置为 $True 的情况下），则这些联系人将被迁移到统一的联系人存储库中（假定这些联系人尚未包含在统一的联系人存储库中）。 如果答案为否，Skype 业务服务器只是忽略用户的联系人，然后移到其下一步的任务。 这意味着，Skype 业务服务器不会自动移动用户的联系人外统一联系人存储库，而不考虑 UcsAllowed 属性的值。
  
这也就意味着之后将该用户分配新用户服务策略，, 您必须运行[调用 CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet 以便移动业务服务器的 Exchange Server 取出并放回 Skype 用户的联系人。 例如，在为 Ken Myer 分配一个新的用户服务策略后，可使用以下命令将用户的联系人从统一的联系人存储库中移出：
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

如果更改用户服务策略但不运行 Invoke-CsUcsRollback cmdlet，则不会从统一的联系人存储库中删除 Ken 的联系人。 如果运行 Invoke-CsUcsRollback 但不更改 Ken Myer 的用户服务策略，会出现什么情况？ 在此情况下，会暂时从统一的联系人存储库中删除 Ken 的联系人。 请务必记住此删除是暂时性的这一事实。 Ken 的联系人已经从统一的联系人存储库中删除后，Skype 业务服务器将等待 7 天，然后检查以查看哪个用户服务策略已指派给 Ken。 如果仍为 Ken 分配了允许使用统一的联系人存储库的策略，则其联系人将被自动移回联系人存储库中。 若要从统一的联系人存储库中永久性删除联系人，您必须更改用户服务策略并运行 Invoke-CsUcsRollback cmdlet。
  
由于存在可影响迁移的大量变量，因而很难估计将帐户完全迁移到统一存储库会用多长时间。但一般说来，迁移不会立即生效：即使迁移的联系人数量不多，完成迁移也可能要用 10 分钟或更长时间。
  

