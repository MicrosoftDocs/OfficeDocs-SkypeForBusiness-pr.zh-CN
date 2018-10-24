---
title: New-CsClientPolicyEntry
TOCTitle: New-CsClientPolicyEntry
ms:assetid: e975d048-4911-4ae6-9446-2a6363726a4a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399046(v=OCS.15)
ms:contentKeyID: 49314613
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsClientPolicyEntry

 

_**上一次修改主题：** 2015-03-09_

向 Lync Server 客户端策略中添加新选项。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsClientPolicyEntry -Name <String> -Value <String>

## 示例

## 示例 1

示例 1 中显示的命令说明如何向全局客户端策略中添加一个新的策略条目。该示例向 Lync 中添加一个新的反馈选项。（请注意，此示例仅用于演示目的。您不应期望能够运行这些命令并向您的 Lync 副本中添加一个类似的反馈选项。

为了添加新的策略条目，示例中的第一个命令使用 **New-CsClientPolicyEntry** cmdlet 创建一个 Name 为 OnlineFeedbackURL 且 Value 为 http://www.litwareinc.com/feedback 的条目。生成的策略条目对象存储在一个名为 $x 的变量中。

在第二个命令中，**Get-CsClientPolicy** cmdlet 用于创建全局客户端策略的对象引用 ($y)。创建该对象引用后，使用了 Add 方法将新的策略条目添加到 PolicyEntry 属性。如果 PolicyEntry 已有一个或多个条目，则新值将只是追加到该集合的末尾。

最后，示例中的最后一个命令使用 **Set-CsClientPolicy** cmdlet 将更改写入实际全局策略中。如果不调用 **Set-CsClientPolicy** cmdlet，更改将仅存在于内存中，并且会在您结束 Windows PowerShell 会话或删除变量 $x 后立即消失。

    $x = New-CsClientPolicyEntry -Name "OnlineFeedbackURL" -Value "http://www.litwareinc.com/feedback"
    
    $y = Get-CsClientPolicy -Identity global
    $y.PolicyEntry.Add($x)
    
    Set-CsClientPolicy -Instance $y

## 示例 2

示例 2 是示例 1 中显示的命令的变体。但在此示例中，新策略条目将替换当前位于全局策略的 PolicyEntry 属性中的所有项。为执行此操作，示例中的第一个命令将创建一个存储在名为 $x 的变量中的新策略条目。然后，第二个命令使用 **Set-CsClientPolicy** cmdlet 将 PolicyEntry 属性的值设置为 $x。在该命令完成运行后，PolicyEntry 属性中唯一的项将成为该新条目。在调用 **Set-CsClientPolicy** cmdlet 之前包含在该属性中的所有项都将替换为新条目。

    $x = New-CsClientPolicyEntry -Name "OnlineFeedbackURL" -Value "http://www.litwareinc.com/feedback"
    Set-CsClientPolicy -Identity global -PolicyEntry $x

## 示例 3

示例 3 说明了如何从全局策略中删除客户端策略条目。为执行此操作，此示例中的第一个命令检索全局客户端策略，并将此信息存储在名为 $y 的变量中。

检索全局策略后，此示例中的第二个命令使用 RemoveAt() 方法删除该策略中的第一个策略条目。要删除的策略条目由其索引号指示：第一个策略条目的索引号为 0，第二个策略条目的索引号为 1，依此类推。语法 RemoveAt(0) 就是指将删除第一个策略条目。

一旦从全局策略的内存中的实例删除策略条目后，将调用 **Set-CsClientPolicy** cmdlet，以便将这些更改写入全局客户端策略的实际实例中。

    $y = Get-CsClientPolicy -Identity global
    $y.PolicyEntry.RemoveAt(0)
    
    Set-CsClientPolicy -Instance $y 

## 示例 4

示例 4 中显示的命令删除为全局策略配置的所有客户端策略条目。这是通过使用 PolicyEntry 参数并将参数值设置为空 ($Null) 来实现的。

    Set-CsClientPolicy -Identity global -PolicyEntry $Null

## 详细说明

客户端策略是 Lync Server 用来管理客户端软件（如 Lync）的主要机制。创建或配置客户端策略时，有大量选项供您使用；例如，您可以指定是否应在 Lync 中使用照片、是否允许在即时消息中使用图释以及 Lync 是否自动保存即时消息会话的脚本。这些选项涵盖管理员需要管理的许多与客户端相关的设置。

但是，它们可能并不涵盖管理员需要管理的所有客户端设置。为了增加管理灵活性和可扩展性，客户端策略包括了一个名为 PolicyEntry 的属性。通过此多值属性，管理员可以添加在客户端策略中不显式调用的新管理选项。例如，在发布 Lync Server 之前，已使试用版测试人员具备向 Lync 中添加反馈选项的能力。此选项是使用 **New-CsClientPolicyEntry** cmdlet 创建的，将添加为一个新策略条目。

请注意，您不能任意创建新的策略条目，并期望这些条目管理 Lync 或某些其他客户端应用程序。您需要等待 Microsoft 关于可用于构造新的客户端策略条目的名称和值的通知。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsClientPolicyEntry** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsClientPolicyEntry"}

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
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>新策略条目的名称。例如：-Name &quot;OnlineFeedbackURL&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>Value</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>要分配给新策略条目的值。例如：-Value http://www.litwareinc.com/feedback。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。New-CsClientPolicyEntry cmdlet 不接受通过管道传递的输入。

## 返回类型

**New-CsClientPolicyEntry** cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Policy.Client.PolicyEntryType 对象的新实例。

## 另请参阅

#### 其他资源

[New-CsClientPolicy](new-csclientpolicy.md)  
[Set-CsClientPolicy](set-csclientpolicy.md)

