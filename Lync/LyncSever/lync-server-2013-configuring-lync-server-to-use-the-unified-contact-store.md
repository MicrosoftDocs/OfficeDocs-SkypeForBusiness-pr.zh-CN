---
title: 将 Microsoft Lync Server 2013 配置为使用统一联系人存储
TOCTitle: 将 Microsoft Lync Server 2013 配置为使用统一联系人存储
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49888452
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Microsoft Lync Server 2013 配置为使用统一联系人存储

 

_**上一次修改主题：** 2014-02-07_

利用统一的联系人存储库，用户可以维护单个联系人列表，然后使这些联系人适用于多个应用程序，包括 Microsoft Lync 2013、Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013。在为某个用户启用统一的联系人存储库后，该用户的联系人不会存储在 Microsoft Lync Server 2013 中，并且稍后将使用 SIP 协议进行检索。相反，该用户的联系人将存储在 Microsoft Exchange Server 2013 中并通过使用 Exchange Web 服务进行检索。

> [!NOTE]  
> 从技术上说，联系人信息将存储在用户的 Exchange 2013 邮箱中包含的一对文件夹中。联系人本身将存储在一个对最终用户可见的名为 Lync Contacts 的文件夹中；有关联系人的元数据将存储在一个对最终用户不可见的子文件夹中。



## 为用户启用统一的联系人存储库

如果已在 Lync Server 2013 和 Exchange 2013 之间配置服务器到服务器身份验证，则您同时也支持对统一的联系人存储库的使用；不需要进行任何附加的服务器配置。但是，若要将用户的联系人移至统一的联系人存储库，则需要其他用户帐户配置。默认情况下，用户联系人保存在 Lync Server 中，而不是保存在统一的联系人存储库中。

对统一的联系人存储库的访问是通过使用 Lync Server 用户服务策略来管理的。用户服务器策略只具有一个属性 (UcsAllowed)；此属性用于确定存储用户联系人的位置。如果某个用户是由 UcsAllowed 设置为 True ($True) 的用户服务策略管理的，则该用户的联系人将存储在统一的联系人存储库中。如果用户是由 UcsAllowed 设置为 False ($False) 的用户服务策略管理的，则其联系人将存储在 Lync Server 中。

安装 Lync Server 2013 时，也将安装单个用户服务策略（在全局范围配置）。此策略中的 UcsAllowed 值将设置为 True，这意味着在默认情况下，用户联系人将存储在统一联系人存储中（假设已部署和配置它）。若要将所有用户联系人迁移到统一联系人存储，根本不必执行任何操作。

如果您不想将所有联系人都迁移到统一联系人存储，您可以通过在全局策略中将 UcsAllowed 属性设置为 False 来对所有用户禁用统一联系人存储：

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

在全局策略中禁用统一联系人存储后，您就可以创建支持使用统一联系人存储的每用户策略；这将允许一些用户将其联系人保存在统一联系人存储中，而其他用户继续将其联系人保存在 Lync Server 中。可通过使用与以下命令类似的命令来创建每用户的用户服务策略：

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

在创建新的策略后，您必须将此策略分配给应有权访问统一的联系人存储库的任何用户。可通过使用与以下内容类似的命令来将每用户策略分配给用户：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

分配此策略后，Lync Server 会开始将用户的联系人迁移到统一联系人存储中。完成迁移后，用户的联系人将存储在 Exchange 而非 Lync Server 中。如果用户在迁移完成时登录到 Lync 2013，则将出现一个消息框，并要求用户注销 Lync 并重新登录以便最终完成此过程。如果未向用户分配此每用户策略，则用户的联系人不会存储到统一联系人存储中。这是因为这些用户受全局策略管理，而全局策略中已禁止使用统一联系人存储。

通过从 Lync Server 命令行管理程序中运行 [Test-CsUnifiedContactStore](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet，您可以验证是否已将用户的联系人成功迁移到统一的联系人存储库中：

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

如果 Test-CsUnifiedContactStore 成功，则表示已将用户 sip:kenmyer@litwareinc.com 的联系人迁移到统一的联系人存储库中。

## 回滚统一的联系人存储库

如果您需要从统一的联系人存储库中删除用户的联系人（例如，如果用户需要重新驻留在 Microsoft Lync Server 2010 中，因此再不能使用统一的联系人存储库），则必须执行两项操作。首先，您必须为用户分配一个新的用户服务策略，此策略禁止将联系人存储在统一的联系人存储库中。（即，UcsAllowed 属性已设置为 $False 的策略。）如果您没有此类策略，则可使用与以下内容类似的命令创建一个此类策略：

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

然后，可通过使用与以下内容类似的命令分配此新的每用户策略 (NoUnifiedContactStore)：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上面的命令将新策略分配给用户 Ken Myer，并且还阻止将 Ken 的联系人迁移到统一的联系人存储库中。

> [!NOTE]  
> 在某些情况下，只需取消分配用户的当前用户服务策略即可达到相同的效果。例如，假定 Ken Myer 具有启用统一的联系人存储库的每用户用户服务策略，但您的全局策略禁止使用统一的联系人存储库。在此情况下，您可以取消分配 Ken 的每用户服务策略。在执行此操作后，Ken 将自动由全局策略管理，因此他将不再能够访问统一的联系人存储库。<br />
若要取消分配之前已分配的每用户策略，请使用如前所示的相同命令，但此时需将 PolicyName 参数设置为 null 值：<br />
Grant-CsUserServicesPolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null



在使用统一的联系人存储库时，请务必记住术语“阻止将 Ken 的联系人迁移到统一的联系人存储库中”。仅为 Ken 分配一个新的用户服务策略并不会将其联系人从统一的联系人存储库中移出。当用户登录到 Lync Server 2013 时，系统将检查用户的用户服务策略以查看其联系人是否应保留在统一的联系人存储库中。如果回答为“是”（即，在 UcsAllowed 属性设置为 $True 的情况下），则这些联系人将被迁移到统一的联系人存储库中（假定这些联系人尚未包含在统一的联系人存储库中）。如果回答是“否”，则 Lync Server 只需忽略用户的联系人，然后继续执行其下一个任务。这意味着，Lync Server 不会自动将用户的联系人从统一的联系人存储库中移出，无论 UcsAllowed 属性的值如何都是如此。

这还意味着，在为用户分配一个新的用户服务策略后，您必须运行 [Invoke-CsUcsRollback](https://docs.microsoft.com/en-us/powershell/module/skype/Invoke-CsUcsRollback) cmdlet 才能将用户的联系人从 Exchange 2013 中移出并返回到 Lync Server 2013。例如，在为 Ken Myer 分配一个新的用户服务策略后，可使用以下命令将用户的联系人从统一的联系人存储库中移出：

    Invoke-CsUcsRollback -Identity "Ken Myer"

如果更改用户服务策略但不运行 Invoke-CsUcsRollback cmdlet，则不会从统一的联系人存储库中删除 Ken 的联系人。如果运行 Invoke-CsUcsRollback 但不更改 Ken Myer 的用户服务策略，会出现什么情况？在此情况下，会暂时从统一的联系人存储库中删除 Ken 的联系人。请务必记住此删除是暂时性的这一事实。从统一的联系人存储库中删除 Ken 的联系人之后，Lync Server 2013 将在 7 天后检查以查看为 Ken 分配了哪个用户服务策略。如果仍为 Ken 分配了允许使用统一的联系人存储库的策略，则其联系人将被自动移回联系人存储库中。若要从统一的联系人存储库中永久性删除联系人，您必须更改用户服务策略并运行 Invoke-CsUcsRollback cmdlet。

由于存在可影响迁移的大量变量，因而很难估计将帐户完全迁移到统一存储库会用多长时间。但一般说来，迁移不会立即生效：即使迁移的联系人数量不多，完成迁移也可能要用 10 分钟或更长时间。

