---
title: 配置 Skype for Business Server 以使用统一联系人存储
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
description: 摘要： 配置 Exchange Server 和 Skype 的统一的联系人存储业务服务器。
ms.openlocfilehash: ebed3e81b12718ae053b4482455cf38bd844799c
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533066"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>配置 Skype for Business Server 以使用统一联系人存储
 
**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 的统一的联系人存储业务服务器。
  
使用统一联系人存储库，用户维护单个联系人列表，然后在多个应用程序，包括 Skype 业务、 Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013 中可用的联系人。 当您启用统一联系人存储库的用户的用户的联系人不存储在 Skype 业务服务器，并根据需要进行检索。 相反，他/她的联系人存储在 Exchange Server 2016 或 Exchange Server 2013 和使用 Exchange Web 服务检索。
  
> [!NOTE]
> 技术上讲，联系信息存储在一对用户的 Exchange 邮箱中找到的文件夹中。 自己的联系人存储在业务联系人可见向最终用户; 命名 Skype 文件夹有关联系人的元数据存储在对最终用户不可见的子文件夹中。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>为用户启用统一的联系人存储库

如果已配置的业务服务器 Skype 和 Exchange Server 之间的服务器到服务器身份验证，然后您也启用了统一的联系人存储;不不需要任何其他服务器配置。 但是，若要将用户的联系人移至统一的联系人存储库，则需要执行额外的用户帐户配置。 默认情况下，和 Skype 业务服务器中的统一联系人存储库不保留用户联系人。
  
使用 Business Server 用户服务策略的 Skype 管理对统一联系人存储库的访问。 用户服务器策略只具有一个属性 (UcsAllowed)；此属性用于确定存储用户联系人的位置。 如果用户托管其中已了将 UcsAllowed 设置为 True ($True) 的用户服务策略然后将统一联系人存储中存储用户的联系人。 如果用户所管理的用户服务的策略其中已了将 UcsAllowed 设置为 False ($False)，则他/她的联系人将存储在 Skype 业务服务器。
  
在安装时 Skype 业务服务器，以及安装 （在全局作用域配置） 的单个用户服务策略。 此策略中的 UcsAllowed 值将设置为 True，这意味着在默认情况下，用户联系人将存储在统一联系人存储中（假设已部署和配置它）。 若要将所有用户联系人迁移到统一联系人存储，根本不必执行任何操作。 
  
如果您不想将所有联系人都迁移到统一联系人存储，您可以通过在全局策略中将 UcsAllowed 属性设置为 False 来对所有用户禁用统一联系人存储：
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

已禁用的统一联系人存储库中的全局策略后，您可以创建允许的统一联系人存储库; 使用每用户策略这样可使其联系人保持其他用户继续保留其联系人中 Skype 业务服务器状态的统一联系人存储库中的某些用户。 可通过使用与以下命令类似的命令来创建每用户的用户服务策略：
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

在创建新的策略后，您必须将此策略分配给应有权访问统一的联系人存储库的任何用户。可通过使用与以下内容类似的命令来将每用户策略分配给用户：
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

在分配策略后，将开始 Skype 业务服务器以将用户的联系人迁移到统一联系人存储库。 完成迁移后，用户将具有业务服务器在 Exchange 存储而不是 Skype 他/她的联系人。 如果用户碰巧登录到 Lync 2013 在时间迁移完成后，将出现一个消息框，将要求他/她 for Business 的 Skype 注销并重新登录以完成该过程。 如果未向用户分配此每用户策略，则用户的联系人不会存储到统一联系人存储中。 这是由于这些用户正在由全局策略，并在全局策略已禁用的统一联系人存储库的使用。
  
您可以验证的用户的联系人成功已迁移到统一的联系人存储通过 for Business Server 命令行管理程序运行[Test-csunifiedcontactstore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet 从 Skype 中：
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

如果 Test-csunifiedcontactstore 成功，则意味着，联系人的用户 sip: kenmyer @<span></span>litwareinc<span></span>.com 已迁移到统一联系人存储库。
  
## <a name="rolling-back-the-unified-contact-store"></a>回滚统一的联系人存储库

如果您需要从统一联系人存储库删除用户的联系人 （例如，如果用户需要在 Microsoft Lync Server 2010 上重新连接，并因此不能再使用统一的联系人存储） 必须执行两项操作。 首先，您必须为用户分配一个新的用户服务策略，此策略禁止将联系人存储在统一的联系人存储库中。 （即，策略其中了将 UcsAllowed 属性已设置为 $False。）如果您没有这样的策略可以创建一个使用类似于以下命令：
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

然后，可通过使用与以下内容类似的命令分配此新的每用户策略 (NoUnifiedContactStore)：
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上面的命令将新策略分配给用户 Ken Myer，并且还阻止将 Ken 的联系人迁移到统一的联系人存储库中。
  
> [!NOTE]
> 在某些情况下，只需取消分配用户的当前用户服务策略即可达到相同的效果。 例如，假定 Ken Myer 具有启用统一的联系人存储库的每用户用户服务策略，但您的全局策略禁止使用统一的联系人存储库。 在此情况下，您可以取消分配 Ken 的每用户服务策略。 在执行此操作后，Ken 将自动由全局策略管理，因此他将不再能够访问统一的联系人存储库。 取消分配以前分配每用户策略，使用同一个命令之前，所示，但这次将 PolicyName 参数设置为空值： Grant-csuserservicespolicy-Identity"Ken Myer"PolicyName $Null 
  
在使用统一的联系人存储库时，请务必记住术语“阻止将 Ken 的联系人迁移到统一的联系人存储库中”。 仅为 Ken 分配一个新的用户服务策略并不会将其联系人从统一的联系人存储库中移出。 当用户登录到 Skype 业务服务器时，系统会检查用户的用户服务策略，以查看是否应统一联系人存储库中保留他/她的联系人。 如果回答为“是”（即，在 UcsAllowed 属性设置为 $True 的情况下），则这些联系人将被迁移到统一的联系人存储库中（假定这些联系人尚未包含在统一的联系人存储库中）。 如果答案为否，Skype 业务服务器只需将忽略用户的联系人，然后移到其下一个任务。 这意味着，Skype 业务服务器不会自动移动用户的联系人外统一联系人存储库，而不考虑了将 UcsAllowed 属性的值。
  
这还意味着之后将用户分配新的用户服务策略，, 您必须运行[Invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet 以将用户的联系人利用 Exchange Server，并返回到 Skype 移动业务服务器。 例如，在为 Ken Myer 分配一个新的用户服务策略后，可使用以下命令将用户的联系人从统一的联系人存储库中移出：
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

如果更改用户服务策略但不运行 Invoke-CsUcsRollback cmdlet，则不会从统一的联系人存储库中删除 Ken 的联系人。 如果运行 Invoke-CsUcsRollback 但不更改 Ken Myer 的用户服务策略，会出现什么情况？ 在此情况下，会暂时从统一的联系人存储库中删除 Ken 的联系人。 请务必记住此删除是暂时性的这一事实。 Ken 的联系人已从统一联系人存储库后，Skype 业务服务器将等待 7 天，然后检查以查看已分配给 Ken 的用户服务策略。 如果仍为 Ken 分配了允许使用统一的联系人存储库的策略，则其联系人将被自动移回联系人存储库中。 若要从统一的联系人存储库中永久性删除联系人，您必须更改用户服务策略并运行 Invoke-CsUcsRollback cmdlet。
  
由于存在可影响迁移的大量变量，因而很难估计将帐户完全迁移到统一存储库会用多长时间。但一般说来，迁移不会立即生效：即使迁移的联系人数量不多，完成迁移也可能要用 10 分钟或更长时间。
  

