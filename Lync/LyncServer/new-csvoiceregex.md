---
title: New-CsVoiceRegex
TOCTitle: New-CsVoiceRegex
ms:assetid: a1a498b7-8353-40bd-9c02-424c95743ec3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412751(v=OCS.15)
ms:contentKeyID: 49313789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsVoiceRegex

 

_**上一次修改主题：** 2015-03-09_

创建用于将电话号码转换为不同格式的正则表达式模式和转换。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsVoiceRegex -AtLeastLength <Int32> [-DigitsToPrepend <String>] [-DigitsToStrip <Int32>] [-StartsWith <String>] <COMMON PARAMETERS>

    New-CsVoiceRegex -ExactLength <Int32> [-DigitsToPrepend <String>] [-DigitsToStrip <Int32>] [-StartsWith <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS:

## 示例

## 示例 1

此示例创建一个新的正则表达式模式和转换。此表达式包含的模式必须正好为 7 个字符 (-ExactLength 7)，并将删除匹配的号码的前三个数字 (-DigitsToStrip 3)。此正则表达式创建的 Pattern 将为 ^\\d{3}(\\d{4})$，而 Translation 将为 $1。例如，号码 5551212 会与此模式匹配，生成的转换将为 1212：7 位数字去除前 3 个数字。

    $regex = New-CsVoiceRegex -ExactLength 7 -DigitsToStrip 3

## 示例 2

此示例也创建一个新的正则表达式模式和转换，但随后会使用这些值创建一个新的语音规范化规则。在第一行中，调用 **New-CsVoiceRegEx** cmdlet 以创建一个正则表达式，其中匹配的号码必须至少为 7 个字符 (-AtLeastLength 7)，并且必须以 1 (-StartsWith "1") 开头。此命令的结果将分配给变量 $regex。

在第二行中，调用 **New-CsVoiceNormalizationRule** cmdlet。我们为该新规则指定了一个唯一名称，在此示例中即 global/internal rule。然后，以规范化规则的 Pattern 方式分配通过调用 **New-CsVoiceRegex** cmdlet 创建的 Pattern：-Pattern $regex.Pattern。我们对 Translation 执行相同的操作，并分配由 **New-CsVoiceRegex** cmdlet 调用创建的 Translation：-Translation $regex.Translation。

注意：此示例中创建的 Pattern 为 ^(1\\d{5}\\d+)$。可以将其解释为一个以 1 (1) 开头的号码，后跟五个数字 (\\d{5})，然后跟任意数目的数字 (\\d+)。这样总计达到的号码将包含至少 7 位数（1 加 5 加 1 或更多）并以 1 开头，与我们所要求的完全一样。

    $regex = New-CsVoiceRegex -AtLeastLength 7 -StartsWith "1"
    New-CsVoiceNormalizationRule "global/internal rule" -Pattern $regex.Pattern -Translation $regex.Translation

## 详细说明

正则表达式用于匹配字符模式。Lync Server 使用正则表达式将电话号码在各种格式之间转换，包括已拨号码、E.164 以及本地专用交换机 (PBX) 和公用电话交换网 (PSTN) 格式。除非您了解使用正则表达式的语法和格式规则，否则定义这些转换规则可能造成用户误解。**New-CsVoiceRegex** cmdlet 可提供用于指定特定条件的参数，然后生成正则表达式。

使用此 cmdlet 可帮助您生成正则表达式，以用作规范化规则 (**New-CsVoiceNormalizationRule** cmdlet) 和出站转换规则 (**New-CsOutboundTranslationRule** cmdlet) 的 Pattern 与 Translation 值，以及用作语音路由 (**New-CsVoiceRoute** cmdlet) 的 NumberPattern 值。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsVoiceRegex** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsVoiceRegex"}

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
<td><p><em>AtLeastLength</em></p></td>
<td><p>必需</p></td>
<td><p>System.Int32</p></td>
<td><p>字符串（电话号码）要与表达式匹配所需的最小长度。例如，如果要定义一个只影响长度必须至少为 7 个数字（或字符）的号码的规范化规则，请为此参数指定值 7。</p>
<p>您必须为此参数或 ExactLength 参数输入一个值，但不能同时为这两个参数输入值。</p></td>
</tr>
<tr class="even">
<td><p><em>ExactLength</em></p></td>
<td><p>必需</p></td>
<td><p>System.Int32</p></td>
<td><p>字符串（电话号码）要与正则表达式匹配必须具有的长度。例如，如果希望某个规范化规则只影响 10 位数的号码，请为此参数指定值 10。</p>
<p>您必须为此参数或 AtLeastLength 参数输入一个值，但不能同时为这两个参数输入值。</p></td>
</tr>
<tr class="odd">
<td><p><em>DigitsToPrepend</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于指定要添加到电话号码开头的字符或数字的字符串。为此参数输入的值会影响 Translation 值，并会将字符附加到与正则表达式模式匹配的号码之前。例如，如果与该模式匹配的号码为 5551212 并且 DigitsToPrepend 值为 425，则转换后的号码将为 4255551212（假设未应用其他任何转换）。</p></td>
</tr>
<tr class="even">
<td><p><em>DigitsToStrip</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>要从字符串（电话号码）开头去除的字符数。例如，如果输入的号码为 2065551212 并且 DigitsToStrip 为 3，则该号码将转换为 5551212。</p></td>
</tr>
<tr class="odd">
<td><p><em>StartsWith</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>字符串（电话号码）的第一个字符。除非字符串以 StartsWith 参数中指定的字符串开头，否则与正则表达式将不匹配。例如，如果为 StartsWith 指定了值“+1”，则只有以 +1 开头的号码才会与该模式匹配并进行转换。请注意，StartsWith 字符串中的字符数将包含在 ExactLength 和 AtLeastLength 总数中。例如，如果已指定 ExactLength 为 10 以及指定 StartsWith 字符串为 +1，则匹配的电话号码的长度将为 8 个字符，前面为 +1，总共 10 位。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.Voice.OcsVoiceRegex 的对象。

## 另请参阅

#### 其他资源

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)  
[New-CsVoiceRoute](new-csvoiceroute.md)

