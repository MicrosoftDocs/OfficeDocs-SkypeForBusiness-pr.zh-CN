---
title: Skype for Business Online 中的身份、范围和租户
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
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Skype for Business Online 中的身份、范围和租户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-03-09_

许多用于管理 Skype for Business Online 的 Windows PowerShell cmdlet 要求你特别了解你尝试管理的项目。 例如，当你运行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet 时，你必须指明要尝试管理的用户。 这样做有意义。 除非你明确告诉 cmdlet 要管理的用户帐户，否则**CsUserAcp** cmdlet 将不知道应修改哪些用户的音频会议信息。 因此，每次运行**CsUserAcp** cmdlet 时，你都需要包含 identity 参数，后跟要修改的用户帐户的标识：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果术语 "*标识*" 始终引用用户帐户的标识，则不会造成混淆。 当您处理人员（用户、联系人等）时，标识会引用单个用户。 但是，除用户帐户以外的其他项目也有标识。 当您处理 Skype for Business Online 服务（策略、配置设置等）的组件时，术语标识意味着略有不同。 例如，请考虑以下命令：

    Get-CsMeetingConfiguration -Identity "global"

在这种情况下，标识 "global" 指会议配置设置的范围。 *范围*是 Skype For business Online （在 Lync Server 中）使用的术语，用于指定球体的管理。 默认情况下，策略和设置始终具有全局范围。 当你首次设置 Skype for Business Online 帐户时，默认情况下，你将拥有全局策略和设置的集合-全局会议配置设置、全局外部访问策略、全局拨号计划等。

Microsoft Lync Server 2010 中引入了这些全局策略和设置，以帮助确保所有用户和所有组件始终以某种方式管理。 这在 Microsoft Office Communicator 2007 R2 中不一定是这样。 根据你的访问系统的方式，你可能最终处于不太基本的非托管状态（通常，因为组策略不能应用于你的用户帐户）。 相比之下，在 Lync Server 和 Skype for business Online 中，不会永远不会留下任何非托管。 这是因为在任何其他情况下，将始终强制执行全局策略和设置。

我们的意思是 "代替其他任何人"？ 嗯，在 Skype for business Online 的情况下，可以在*标记范围*（或管理的球体）创建策略。 在标记作用域（也称为*每用户范围*）创建的策略优先于在全局范围内创建的策略。 换句话说，每用户策略将始终优先于全局策略。 例如，你可能有两个外部用户访问策略。 全局策略禁止用户与在公共即时消息（IM）提供程序（如 Windows Live）上具有帐户的人员进行通信。 每用户策略 AllowPublicIMCommunication 允许与公共 IM 提供商进行通信。

您还可能有两个用户： Ken Myer 和 Pilar Ackerman。 已将 Ken Myer 分配给每用户策略。 Pilar Ackerman 尚未分配给每用户策略;即，她由全局外部访问策略管理。 下表显示了可以与公共 IM 提供商通信的用户（如果有）：


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


正如你所看到的，允许 Ken Myer 与公共 IM 提供商通信。 这是因为分配给他的每个用户策略中的设置替代了全局策略中的设置。 Pilar Ackerman 无法与公共 IM 提供商通信。 这是因为她由全局策略管理，而全局策略禁止此类通信。

每个用户的策略必须由 Office 365 支持人员创建。 创建策略后，您可以使用相应的**授权-Cs** cmdlet 将它们分配给用户（例如，[授予 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）。 每用户策略易于识别，因为策略标识始终以标记**前缀**开头。 例如：

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 标记<STRONG>前缀</STRONG>日期返回 Lync Server 2010 的早期开发日。 在这些天内，每个用户的策略称为<EM>标记策略</EM>，并由标记<STRONG>前缀</STRONG>标识。 这些策略现在更准确地称为 "<EM>每用户策略</EM>"，标记范围更准确地称为 "<EM>每用户" 范围</EM>。 但是，由于技术原因，标记<STRONG>前缀</STRONG>永远不会更改。



</div>

使用 Skype for Business Online 和 Windows PowerShell 时使用的另一个关键术语是*租户*。 设置 Skype for Business Online 帐户时，将为你的新部署分配租户 ID 号，它是类似于以下内容的全局唯一标识符（GUID）：

    bf19b7db-6960-41e5-a139-2aa373474354

一些 Skype for Business Online cmdlet 要求你在运行 cmdlet 时输入租户 ID。 你必须输入租户 ID，即使你已登录到且仅有一个租户。 幸运的是，您不必记住租户 ID。 你可以随时通过运行以下 Windows PowerShell 命令来检索租户 ID：

    Get-CsTenant | Select-Object TenantId

当然，知道全局范围和每用户作用域（或标签范围）之间的区别，只有一半的工作。 了解何时（或即使）你可以使用这些范围也很重要。 对于标识和租户参数，也是如此。 以下主题介绍不同的 Skype for Business Online cmdlet 如何使用标识、作用域和租户参数：

  - [Skype for Business Online 中仅使用全局范围的 cmdlet](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Skype for Business Online 中使用全局范围和标记范围的 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Skype for Business Online 中使用用户标识的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Skype for Business Online 中使用用户标识和标记作用域的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Skype for Business Online 中使用租户参数的 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Skype for Business Online 中使用会议提供商标识的 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Skype for Business Online 中不使用作用域或标识的 cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

