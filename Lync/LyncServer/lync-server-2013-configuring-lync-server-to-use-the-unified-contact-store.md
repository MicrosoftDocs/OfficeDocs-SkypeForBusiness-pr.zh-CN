---
title: Lync Server 2013：配置 Lync Server 以使用统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>将 Microsoft Lync Server 2013 配置为使用统一联系人存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-07_

"统一联系人存储" 使用户能够维护单个联系人列表，然后让这些联系人在多个应用程序中可用，包括 Microsoft Lync 2013、Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013。 为用户启用统一联系人存储时，用户的联系人不存储在 Microsoft Lync Server 2013 中，然后使用 SIP 协议进行检索。 相反，他/她的联系人存储在 Microsoft Exchange Server 2013 中，并且通过使用 Exchange Web 服务进行检索。

<div>


> [!NOTE]  
> 从技术上讲，联系人信息存储在用户的 Exchange 2013 邮箱中找到的一对文件夹中。 联系人本身存储在名为 "Lync 联系人" 的文件夹中，这些联系人对最终用户可见;有关联系人的元数据存储在对最终用户不可见的子文件夹中。



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>为用户启用统一的联系人存储库

如果你已在 Lync Server 2013 和 Exchange 2013 之间配置了服务器到服务器身份验证，则你还启用了统一联系人存储的使用;不需要额外的服务器配置。 但是，若要将用户的联系人移至统一的联系人存储库，则需要执行额外的用户帐户配置。 默认情况下，用户联系人保留在 Lync Server 中，而不是在统一联系人存储中。

通过使用 Lync Server 用户服务策略管理对统一联系人存储的访问。 用户服务器策略只具有一个属性 (UcsAllowed)；此属性用于确定存储用户联系人的位置。 如果用户由 UcsAllowed 已设置为 True （$True）的用户服务策略进行管理，则用户的联系人将存储在统一联系人存储中。 如果用户由 UcsAllowed 已设置为 False （$False）的用户服务策略进行管理，则他或她的联系人将存储在 Lync Server 中。

安装 Lync Server 2013 时，将同时安装单个用户服务策略（在全局范围内配置）。 此策略中的 UcsAllowed 值将设置为 True，这意味着在默认情况下，用户联系人将存储在统一联系人存储中（假设已部署和配置它）。 若要将所有用户联系人迁移到统一联系人存储，根本不必执行任何操作。

如果您不想将所有联系人都迁移到统一联系人存储，您可以通过在全局策略中将 UcsAllowed 属性设置为 False 来对所有用户禁用统一联系人存储：

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

在全局策略中禁用统一联系人存储后，您可以创建允许使用统一联系人存储的基于用户的策略;这允许你让某些用户在 "统一联系人" 存储中保留其联系人，而其他用户继续在 Lync Server 中保留其联系人。 可通过使用与以下命令类似的命令来创建每用户的用户服务策略：

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

在创建新的策略后，您必须将此策略分配给应有权访问统一的联系人存储库的任何用户。可通过使用与以下内容类似的命令来将每用户策略分配给用户：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

分配策略后，Lync 服务器将开始将用户的联系人迁移到 "统一联系人存储"。 完成迁移后，用户将在 Exchange 中存储其联系人，而不是 Lync Server。 如果用户在迁移完成时登录到 Lync 2013，则会出现一个消息框，系统将要求用户注销 Lync，然后重新登录以完成该过程。 如果未向用户分配此每用户策略，则用户的联系人不会存储到统一联系人存储中。 这是因为这些用户受全局策略管理，而全局策略中已禁止使用统一联系人存储。

你可以通过在 Lync Server Management Shell 中运行[CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet 来验证用户的联系人是否已成功迁移到统一联系人存储：

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

如果 Test-CsUnifiedContactStore 成功，则表示已将用户 sip:kenmyer@litwareinc.com 的联系人迁移到统一的联系人存储库中。

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>回滚统一的联系人存储库

如果需要从 "统一联系人存储" 中删除用户的联系人（例如，如果用户需要在 Microsoft Lync Server 2010 上 rehomed，因此无法再使用 "统一联系人存储"），则必须执行两项操作。 首先，您必须为用户分配一个新的用户服务策略，此策略禁止将联系人存储在统一的联系人存储库中。 （即，UcsAllowed 属性已设置为 $False 的策略。）如果您没有这样的策略，则可以使用类似如下的命令创建一个策略：

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

然后，可通过使用与以下内容类似的命令分配此新的每用户策略 (NoUnifiedContactStore)：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上面的命令将新策略分配给用户 Ken Myer，并且还阻止将 Ken 的联系人迁移到统一的联系人存储库中。

<div>


> [!NOTE]  
> 在某些情况下，只需取消分配用户的当前用户服务策略，即可获得相同的网络效果。 例如，假定 Ken Myer 具有启用统一的联系人存储库的每用户用户服务策略，但您的全局策略禁止使用统一的联系人存储库。 在这种情况下，您可以取消分配 Ken 的每用户服务策略。 在执行此操作后，Ken 将自动由全局策略管理，因此他将不再能够访问统一的联系人存储库。<BR>若要取消分配以前分配的每用户策略，请使用前面所示的相同命令，但这次将 PolicyName 参数设置为 null 值：<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

在使用统一的联系人存储库时，请务必记住术语“阻止将 Ken 的联系人迁移到统一的联系人存储库中”。 仅为 Ken 分配一个新的用户服务策略并不会将其联系人从统一的联系人存储库中移出。 当用户登录到 Lync Server 2013 时，系统会检查用户的用户服务策略，以查看其联系人是否应保留在 "统一联系人" 存储中。 如果回答为“是”（即，在 UcsAllowed 属性设置为 $True 的情况下），则这些联系人将被迁移到统一的联系人存储库中（假定这些联系人尚未包含在统一的联系人存储库中）。 如果答案为 "否"，则 Lync Server 只会忽略用户的联系人并转到其下一个任务。 这意味着 Lync Server 不会自动将用户的联系人从 "统一联系人存储" 移出，无论 UcsAllowed 属性的值如何。

这还意味着，在为用户分配新的用户服务策略之后，必须运行[CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet，以便将用户的联系人从 Exchange 2013 移出并返回到 Lync Server 2013。 例如，在为 Ken Myer 分配一个新的用户服务策略后，可使用以下命令将用户的联系人从统一的联系人存储库中移出：

    Invoke-CsUcsRollback -Identity "Ken Myer"

如果更改用户服务策略但不运行 Invoke-CsUcsRollback cmdlet，则不会从统一的联系人存储库中删除 Ken 的联系人。 如果运行 Invoke-CsUcsRollback 但不更改 Ken Myer 的用户服务策略，会出现什么情况？ 在此情况下，会暂时从统一的联系人存储库中删除 Ken 的联系人。 请务必记住此删除是暂时性的这一事实。 从 "统一联系人存储" 删除 Ken 联系人后，Lync Server 2013 将等待7天，然后检查哪些用户服务策略已分配给 Ken。 如果仍为 Ken 分配了允许使用统一的联系人存储库的策略，则其联系人将被自动移回联系人存储库中。 若要从统一的联系人存储库中永久性删除联系人，您必须更改用户服务策略并运行 Invoke-CsUcsRollback cmdlet。

由于存在可影响迁移的大量变量，因而很难估计将帐户完全迁移到统一存储库会用多长时间。但一般说来，迁移不会立即生效：即使迁移的联系人数量不多，完成迁移也可能要用 10 分钟或更长时间。

</div>

</div>

<span> </span>

</div>

</div>

</div>

