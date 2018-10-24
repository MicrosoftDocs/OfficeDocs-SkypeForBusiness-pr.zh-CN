---
title: 标识、作用域和租户
TOCTitle: 标识、作用域和租户
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56271169
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 标识、作用域和租户

 

_**上一次修改主题：** 2015-06-22_

许多用于管理 Skype for Business Online 的 Windows PowerShell cmdlet 要求您很具体地了解您试图管理的项目。例如，当您运行 [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp) cmdlet 时，您必须指明您试图管理哪个用户。这意义重大。除非您具体告诉 cmdlet 要管理的用户帐户，否则 **Set-CsUserAcp** cmdlet 不知道应修改哪个用户的音频会议信息。因此，当您每次运行 **Set-CsUserAcp** cmdlet 时，都需要包括 Identity 参数，后跟要修改的用户帐户的标识：

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

如果术语*标识*始终是指某用户帐户的标识，那么可能会引起一些混淆。当您处理人员（用户、联系人等）时，标识是指各个用户本身。然而，用户帐户以外的其他项目也具有标识。当您处理 Skype for Business Online 服务的组件（策略、配置设置等）时，术语“标识”的涵义略有不同。例如，考虑此命令：

    Get-CsMeetingConfiguration -Identity "global"

在此例中，标识“global”是指会议配置设置的作用域。*作用域*这一术语在 Skype for Business Online（和 Lync Server）中用于指定管理的范围。默认情况下，策略和设置始终具有全局作用域。当首次设置 Skype for Business Online 帐户时，默认情况下，您将拥有全局策略和设置的集合（全局会议配置设置、全局外部访问策略、全局拨号计划等）。

这些全局策略和设置已在 Microsoft Lync Server 2010 中引入，可帮助确保所有用户和所有组件始终以某种方式进行管理。在 Microsoft Office Communicator 2007 R2 中不必如此。根据您访问系统的方式，您可能会以在很大程度上不受管理的状态结束（通常，因为组策略无法应用于您的用户帐户）。与之相比，在 Lync Server 和 Skype for Business Online 中，没有什么内容不受管理。 这是因为无论如何始终将强制实施全局策略和设置。

我们说的“无论如何”是什么意思？对于 Skype for Business Online，可以在*标记作用域*处创建策略或管理的范围。在标记作用域（也称为*每用户作用域*）处创建的策略优先于在全局作用域处创建的策略。换句话说，每用户策略始终优先于全局策略。例如，您可能有两个外部用户访问策略。全局策略禁止用户与在公共即时消息 (IM) 提供商（如 Windows Live）上拥有帐户的人员进行通信。每用户策略 AllowPublicIMCommunication 允许与公共 IM 提供商进行通信。

您可能也有两个用户：Ken Myer 和 Pilar Ackerman。Ken Myer 被分配了每用户策略。Pilar Ackerman 未被分配每用户策略；也就是说，她受全局外部访问策略管理。下表显示了哪个用户（如果有）可以与公共 IM 提供商进行通信：


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
<td><p>公共 IM 提供商的全局策略设置</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>公共 IM 提供商的每用户策略设置</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>用户可以与公共 IM 提供商进行通信</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


如您所见，Ken Myer 允许与公共 IM 提供商进行通信。这是因为分配给他的每用户策略中的设置将替代全局策略中的设置。Pilar Ackerman 不能与公共 IM 提供商进行通信。这是因为她受全局策略管理，而全局策略禁止此类通信。

每用户策略必须由 Office 365 支持人员为您创建。创建策略后，您可以使用合适的 **Grant-Cs** cmdlet（例如，[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)）将它们分配给用户。每用户策略易于识别，因为策略标识使用以标记 **prefix** 开头。例如：

    Identity : tag:AllowPublicIMCommunication

> [!NOTE]  
> 标记 <strong>prefix</strong> 可回溯到 Lync Server 2010 最初部署的那些天。在这些天里，每用户策略称为<em>标记策略</em>，通过标记 <strong>prefix</strong> 进行标识。这些策略现在更准确地称为<em>每用户策略</em>，标记作用域更准确地称为<em>每用户作用域</em>。但是，出于技术原因，标记 <strong>prefix</strong> 从未更改。



使用 Skype for Business Online 和 Windows PowerShell 时要使用的另一个关键术语是*租户*。当您设置 Skype for Business Online 帐户时，您的新部署会被分配一个租户 ID 号，它是与此类似的全局唯一标识符 (GUID)：

    bf19b7db-6960-41e5-a139-2aa373474354

一些 Skype for Business Online cmdlet 要求您每次运行 cmdlet 时输入租户 ID。即使您已经登录并且仅有一个租户，也必须输入租户 ID。幸运的是，您不必记住租户 ID。您随时可通过运行以下 Windows PowerShell 命令检索您的租户 ID：

    Get-CsTenant | Select-Object TenantId

当然，知道全局作用域和每用户作用域（或标记作用域）之间的区别等事项只是成功的一半。了解何时（甚至是否）可使用这些作用域非常重要。对于标识和租户参数也是如此。以下主题介绍了不同的 Skype for Business Online cmdlet 如何使用标识、作用域和租户参数：

  - [仅使用全局作用域的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [使用全局作用域和标记作用域的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [使用用户标识的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [使用用户标识和标记作用域的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [使用 Tenant 参数的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [使用会议提供商标识的 Cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [不使用作用域或标识的 Cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

