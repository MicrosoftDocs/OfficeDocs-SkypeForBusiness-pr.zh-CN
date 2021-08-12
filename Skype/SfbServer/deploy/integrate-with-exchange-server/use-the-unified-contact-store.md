---
title: 配置Skype for Business Server统一联系人存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 摘要：为联系人和联系人配置统一Exchange Server Skype for Business Server。
ms.openlocfilehash: 78953049394391517d229205e711e670701d9f857458673646e4022a178d3843
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295709"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>配置Skype for Business Server统一联系人存储
 
**摘要：** 为 2016 或 Exchange Server 2013 Exchange Server配置统一的联系人Skype for Business Server。
  
通过使用统一的联系人存储，用户可以维护一个联系人列表，然后将这些联系人用于多个应用程序，包括 Skype for Business、Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013。 为用户启用统一联系人存储时，该用户的联系人不会存储在 Skype for Business Server并根据需要进行检索。 相反，其联系人存储在 Exchange Server 2016 或 Exchange Server 2013 中，并且使用 Exchange Web 服务进行检索。
  
> [!NOTE]
> 从技术上说，联系人信息存储在用户邮箱的一对Exchange中。 联系人本身存储在名为"联系人Skype for Business最终用户可见的文件夹中;有关联系人的元数据存储在最终用户不可见的子文件夹内。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>为用户启用统一的联系人存储库

如果已配置 Skype for Business Server 和 Exchange Server 之间的服务器到服务器身份验证，则还启用了统一联系人存储;无需其他服务器配置。 但是，若要将用户的联系人移至统一的联系人存储库，则需要其他用户帐户配置。 默认情况下，用户联系人保存在统一Skype for Business Server，而不是保存在统一的联系人存储中。
  
通过使用统一联系人存储的用户服务策略Skype for Business Server统一联系人存储。 用户服务器策略只具有一个属性 (UcsAllowed)；此属性用于确定存储用户联系人的位置。 如果用户由 UcsAllowed 设置为 True 的用户服务策略进行管理 ($True) 则用户的联系人将存储在统一的联系人存储中。 如果用户由 UcsAllowed 设置为 False 的用户服务策略进行管理 ($False) 则其联系人将存储在 Skype for Business Server。
  
安装 Skype for Business Server时， (全局范围配置的单用户服务策略) 安装。 此策略中的 UcsAllowed 值设置为 True，这意味着默认情况下，用户联系人将存储在统一联系人存储中 (假定已部署和配置) 。 如果要将所有的用户联系人迁移到统一的联系人存储，则完全不需要执行任何操作。 
  
如果您不希望将所有联系人迁移到统一的联系人存储，可以通过将全局策略中的 UcsAllowed 属性设置为 False 来禁用所有用户的统一联系人存储：
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

在全局策略中禁用统一联系人存储后，可以创建允许使用统一联系人存储的按用户策略;这样，一些用户可以将联系人保存在统一的联系人存储中，而其他用户可以继续将联系人保存在统一Skype for Business Server。 可通过使用与以下内容类似的命令来创建每用户用户服务策略：
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

在创建新的策略后，您必须将此策略分配给应有权访问统一的联系人存储库的任何用户。可通过使用与以下内容类似的命令来将每用户策略分配给用户：
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

分配策略后，Skype for Business Server开始将用户的联系人迁移到统一的联系人存储。 迁移完成后，用户将联系人存储在 Exchange 中，而不是Skype for Business Server。 如果用户在迁移完成时登录到 Lync 2013，将出现一个消息框，并要求其注销 Skype for Business 然后重新登录以完成此过程。 尚未分配此每用户策略的用户不会将其联系人迁移到统一的联系人存储。 这是因为这些用户由全局策略管理，并且已在全局策略中禁用对统一联系人存储的使用。
  
通过从命令行管理程序内运行[Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet，可以验证用户的联系人已成功迁移到统一Skype for Business Server存储：
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

如果Test-CsUnifiedContactStore，则意味着用户 sip：kenmyer@ <span></span> litwareinc .com 的联系人已迁移到 <span></span> 统一的联系人存储。
  
## <a name="rolling-back-the-unified-contact-store"></a>回滚统一的联系人存储库

如果需要从统一联系人存储 (中删除用户的联系人，例如，如果用户需要在 Microsoft Lync Server 2010 上重新进行管理，因而无法再使用统一联系人存储) 则必须执行两项操作。 首先，您必须为用户分配一个新的用户服务策略，此策略禁止将联系人存储在统一的联系人存储库中。  (即 UcsAllowed 属性已设置为 $False.) 如果没有此类策略，可以使用以下类似命令创建一个策略：
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

然后，可通过使用与以下内容类似的命令分配此新的每用户策略 (NoUnifiedContactStore)：
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上面的命令将新策略分配给用户 Ken Myer，并且还阻止将 Ken 的联系人迁移到统一的联系人存储库中。
  
> [!NOTE]
> 在某些情况下，只需取消分配用户的当前用户服务策略，可以实现相同的效果。 例如，假定 Ken Myer 具有启用统一的联系人存储库的每用户用户服务策略，但您的全局策略禁止使用统一的联系人存储库。 在这种情况下，您可以取消分配 Ken 的按用户服务策略。 在执行此操作后，Ken 将自动由全局策略管理，因此他将不再能够访问统一的联系人存储库。 若要取消分配之前分配每用户策略，请使用与前面所示相同的命令，但这次将 PolicyName 参数设置为空值：Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
在使用统一的联系人存储库时，请务必记住术语“阻止将 Ken 的联系人迁移到统一的联系人存储库中”。 仅为 Ken 分配一个新的用户服务策略并不会将其联系人从统一的联系人存储库中移出。 当用户登录到 Skype for Business Server时，系统会检查用户的用户服务策略，以查看其联系人是否应该保留在统一的联系人存储中。 如果回答为“是”（即，在 UcsAllowed 属性设置为 $True 的情况下），则这些联系人将被迁移到统一的联系人存储库中（假定这些联系人尚未包含在统一的联系人存储库中）。 如果回答为"否"，则Skype for Business Server忽略用户的联系人，然后继续下一个任务。 这意味着Skype for Business Server用户联系人不会自动从统一的联系人存储中移出，无论 UcsAllowed 属性的值如何。
  
这也意味着，在向用户分配一个新的用户服务策略后，您必须运行[Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet 才能将用户的联系人从 Exchange Server 移回 Skype for Business Server。 例如，在为 Ken Myer 分配一个新的用户服务策略后，可使用以下命令将用户的联系人从统一的联系人存储库中移出：
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

如果更改用户服务策略但不运行 Invoke-CsUcsRollback cmdlet，则不会从统一的联系人存储库中删除 Ken 的联系人。 如果运行 Invoke-CsUcsRollback 但不更改 Ken Myer 的用户服务策略，会出现什么情况？ 在此情况下，会暂时从统一的联系人存储库中删除 Ken 的联系人。 请务必记住此删除是暂时性的这一事实。 从统一的联系人存储中删除 Ken 的联系人后，Skype for Business Server等待 7 天，然后查看向 Ken 分配了哪个用户服务策略。 如果仍为 Ken 分配了允许使用统一的联系人存储库的策略，则其联系人将被自动移回联系人存储库中。 若要从统一的联系人存储库中永久性删除联系人，您必须更改用户服务策略并运行 Invoke-CsUcsRollback cmdlet。
  
由于大量的变量会影响迁移，因此很难估计帐户完全迁移到统一联系人存储之前需要多久。 但是，作为一般规则，迁移不会立即生效：即使迁移少量联系人，移动完成也可能需要 10 分钟或更大时间。
