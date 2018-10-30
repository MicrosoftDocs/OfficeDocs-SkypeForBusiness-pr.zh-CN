---
title: New-CsPrivacyConfiguration
TOCTitle: New-CsPrivacyConfiguration
ms:assetid: 9b7f02d7-93a5-4fa5-a74c-3fe4baf8bbfc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398807(v=OCS.15)
ms:contentKeyID: 49313729
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPrivacyConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建新的隐私配置设置集合。隐私配置设置可以帮助确定用户可与其他用户共享的信息量。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsPrivacyConfiguration -Identity <XdsIdentity> [-AutoInitiateContacts <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisplayPublishedPhotoDefault <$true | $false>] [-EnablePrivacyMode <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-PublishLocationDataDefault <$true | $false>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令会创建新的隐私配置设置集合，这些设置将会应用到 Redmond 站点 (-Identity site:Redmond)。新设置将启用隐私模式，可通过添加 EnablePrivacyMode 参数并将参数值设置为 True 来执行此操作。请注意，如果 Redmond 站点已拥有隐私设置的集合，则此命令将失败。

    New-CsPrivacyConfiguration -Identity site:Redmond -EnablePrivacyMode $True

## 示例 2

示例 2 演示了如何能够使用 InMemory 参数来创建初始仅存在于内存中的新的隐私配置设置集合。为执行此操作，调用带 Identity 和 InMemory 参数的 **New-CsPrivacyConfiguration** cmdlet；生成的对象会存储在名为 $x 的变量中。此时，隐私设置仅存在于内存中；如果运行 **Get-CsPrivacyConfiguration** cmdlet，您将看不到 site:Redmond 的列表。

在第二个命令中，EnablePrivacyMode 属性的值设置为 True。最后，第三个命令使用 **Set-CsPrivacyConfiguration** cmdlet 将此虚拟隐私设置集合转换为应用于 Redmond 站点的实际设置集合。调用 **Set-CsPrivacyConfiguration** cmdlet 很重要：如果调用此 cmdlet 失败，则新隐私设置将不会应用于 Redmond 站点，并且这些设置将在您终止 Windows PowerShell 会话或删除变量 $x 时一同消失。

    $x = New-CsPrivacyConfiguration -Identity site:Redmond -InMemory
    $x.EnablePrivacyMode = $True
    Set-CsPrivacyConfiguration -Instance $x

## 详细说明

通过 Lync Server，用户可以与其他人共享大量的状态信息：可以发布自己的照片；可以提供详细的位置信息；可以向组织中的所有人自动提供状态信息（而不是仅向用户联系人列表上的人员提供此信息）。

某些用户会很高兴可以与同事共享这些信息，而其他用户可能不太愿意共享这些数据。（例如，很多人在决定是否将自己的照片包含在状态数据时，可能会很犹豫。）一般而言，用户可以控制他们将共享（或不共享）的信息；例如，用户可以选中或取消选中某个复选框以便控制是否与他人共享其位置信息。此外，通过隐私配置 cmdlet，管理员可以管理其用户的隐私设置。在某些情况下，管理员可以启用或禁用设置；例如，如果将属性 AutoInitiateContacts 设置为 True，则会将团队成员自动添加到每个用户的联系人列表；如果将此属性设置为 False，则不会将团队成员自动添加到每个用户的联系人列表。

在其他情况下，管理员可以在 Lync 中配置默认值，同时还向用户授予更改这些值的权限。例如，尽管用户有权停止发布其位置数据，但在默认情况下还是会发布该数据。通过将 PublishLocationDataByDefault 属性设置为 False，管理员可以更改此行为：在这种情况下，尽管如果用户进行选择，他们仍然有权发布位置数据，但在默认情况下，不发布该数据。

隐私配置设置可以应用于全局范围、站点范围和服务范围（尽管仅针对“用户服务器”服务）。通过 **New-CsPrivacyConfiguration** cmdlet，您能够创建要应用于站点或服务的新隐私配置设置。（无法在全局范围创建新集合。）请注意，每个单独的站点或服务最多只能有一个隐私配置设置的集合：如果尝试创建 Redmond 站点的新集合，但此站点已经拥有隐私设置的集合，则命令将失败。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsPrivacyConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPrivacyConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要创建的隐私配置设置的唯一标识符。要在站点范围创建设置的新集合，请使用类似语法：-Identity site:Redmond。要在服务范围创建新设置，请使用类似语法：-Identity service:UserServer:atl-cs-001.litwareinc.com。只能为“用户服务器”服务创建隐私设置。如果尝试将这些设置应用到任何其他服务，则会出现错误。</p>
<p>请注意，如果指定站点或服务已存在隐私配置设置，则命令将失败。同样，如果尝试创建全局设置的新集合，则命令也将失败。</p></td>
</tr>
<tr class="even">
<td><p><em>AutoInitiateContacts</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果为 True，则 Lync 会自动将您的经理和直接下属添加到您的联系人列表中。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayPublishedPhotoDefault</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果为 True，则会自动在 Lync 中发布用户的照片。如果为 False，则除非用户明确选择了选项“让其他人看到我的照片”，否则不会提供用户的照片。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePrivacyMode</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果为 True，则用户可以启用高级隐私模式。在高级隐私模式中，仅允许您联系人列表中的人员查看您的状态信息。如果为 False，则组织中的任何人都可以查看您的状态信息。默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>PublishLocationDataDefault</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果为 True，则会自动在 Lync 中发布位置数据。如果为 False，则除非用户明确选择了选项“向联系人显示我的位置”，否则不会提供位置数据。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>为 Skype for Business Online 租户帐户的全局唯一标识符 (GUID) 创建新的隐私配置设置集合。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>通过运行此命令可以返回每位租户的租户 ID。</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**New-CsPrivacyConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**New-CsPrivacyConfiguration** cmdlet 会创建 Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PrivacyConfiguration 对象的新实例。

## 另请参阅

#### 其他资源

[Get-CsPrivacyConfiguration](get-csprivacyconfiguration.md)  
[Remove-CsPrivacyConfiguration](remove-csprivacyconfiguration.md)  
[Set-CsPrivacyConfiguration](set-csprivacyconfiguration.md)

