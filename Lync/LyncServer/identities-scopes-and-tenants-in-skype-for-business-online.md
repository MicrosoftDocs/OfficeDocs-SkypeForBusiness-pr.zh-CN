---
title: Skype for Business Online 中的标识、范围和租户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dd2008984707f1f8e76b7e61074d5303c0d0819
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Skype for Business Online 中的标识、范围和租户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-03-09_

许多用于管理 Skype for Business Online 的 Windows PowerShell cmdlet 都要求您特别注意您尝试管理的项目。 例如，当您运行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet 时，您必须指明要尝试管理的用户。 这很合理。 除非您明确告知 cmdlet 要管理哪个用户帐户，否则**CsUserAcp** cmdlet 将不知道应修改哪个用户的音频会议信息。 因此，每次运行**CsUserAcp** cmdlet 时，都需要包含 identity 参数，后跟要修改的用户帐户的标识：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果术语 "*标识*" 总是指用户帐户的标识，则很少导致混淆。 当您处理人员（用户、联系人等）时，标识将分别引用各个用户。 但是，除用户帐户之外的其他项目也具有标识。 当您处理 Skype for Business Online 服务的组件（策略、配置设置等）时，术语标识意味着有些不同。 例如，请考虑以下命令：

    Get-CsMeetingConfiguration -Identity "global"

在这种情况下，标识 "global" 表示会议配置设置的范围。 *Scope*是 Skype For business Online 中使用的术语（在 Lync Server 中），用于指定用于管理的球体。 默认情况下，策略和设置始终具有全局作用域。 在您首次设置 Skype for Business Online 帐户时，默认情况下，将拥有全局策略和设置（全局会议配置设置、全局外部访问策略、全局拨号计划等）的集合。

这些全局策略和设置在 Microsoft Lync Server 2010 中引入，以帮助确保所有用户和所有组件都始终以某种方式进行管理。 在 Microsoft Office Communicator 2007 R2 中不一定如此。 根据您访问系统的方式，可能会最终导致不受管理的状态（通常是因为组策略不能应用于您的用户帐户）。 与此相反，在 Lync Server 和 Skype for Business Online 中，决不会留下任何非托管。 这是因为，而不是其他任何内容，则始终强制实施全局策略和设置。

我们的意思是 "代替其他任何程序"？ 嗯，在 Skype for business Online 的情况下，可以在*标记范围*或管理层创建策略。 在标记作用域（也称为 *"每用户范围"*）中创建的策略优先于在全局范围内创建的策略。 换言之，每用户策略将始终优先于全局策略。 例如，您可能有两个外部用户访问策略。 全局策略禁止用户与在公共即时消息（IM）提供程序（如 Windows Live）上具有帐户的人员进行通信。 每用户策略 AllowPublicIMCommunication 允许与公共 IM 提供商进行通信。

您可能还有两个用户： Ken Myer 和 Pilar Ackerman。 已为 Ken Myer 分配每用户策略。 尚未为 Pilar Ackerman 分配每用户策略;即，由全局外部访问策略管理她。 下表显示了可以与公共 IM 提供商通信的用户（如果有）：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>策略设置</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>公用 IM 提供商的全局策略设置</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>公用 IM 提供商的每用户策略设置</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>用户可以与公共 IM 提供商通信</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


正如您所看到的，允许 Ken Myer 与公共 IM 提供商通信。 这是因为分配给他的每用户策略中的设置将覆盖全局策略中的设置。 Pilar Ackerman 无法与公共 IM 提供商通信。 这是因为她由全局策略进行管理，而全局策略将禁止此类通信。

必须由 Office 365 支持为您创建每个用户的策略。 创建策略后，可以使用相应的**Grant-Cs** cmdlet 将它们分配给用户（例如， [set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）。 由于策略标识总是以标记**前缀**开头，因此每个用户的策略易于识别。 例如：

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 标记<STRONG>前缀</STRONG>日期返回到 Lync Server 2010 的早期开发日。 在这些天中，每个用户的策略称为<EM>标记策略</EM>，并由标记<STRONG>前缀</STRONG>标识。 现在，这些策略更准确地称为 "<EM>每用户策略</EM>"，标记作用域更准确地称为 "<EM>每用户" 作用域</EM>。 但是，由于技术原因，标记<STRONG>前缀</STRONG>永远不会更改。



</div>

使用 Skype for Business Online 和 Windows PowerShell 时使用的另一个关键术语是*租户*。 当你设置 Skype for Business Online 帐户时，将为你的新部署分配租户 ID 号，该号码是与以下内容类似的全局唯一标识符（GUID）：

    bf19b7db-6960-41e5-a139-2aa373474354

几个 Skype for Business Online cmdlet 要求您在每次运行 cmdlet 时输入租户 ID。 您必须输入租户 ID，即使您已登录到且只有一个租户。 幸运的是，您不必记住租户 ID。 您可以通过运行以下 Windows PowerShell 命令随时检索租户 ID：

    Get-CsTenant | Select-Object TenantId

当然，了解全局范围和每用户范围之间的差异（或标记范围）只是一件工作的一半。 此外，了解何时（或即使）可以使用这些范围也很重要。 对于标识和租户参数，情况也是如此。 以下主题介绍不同的 Skype for Business Online cmdlet 如何使用标识、作用域和租户参数：

  - [仅使用全局范围的 Skype for business Online 中的 cmdlet](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Skype for Business Online 中使用用户标识的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Skype for Business Online 中使用用户标识和标记作用域的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [使用租户参数的 Skype for Business Online 中的 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Skype for Business Online 中使用会议提供商标识的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Skype for Business Online 中不使用作用域或标识的 cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

