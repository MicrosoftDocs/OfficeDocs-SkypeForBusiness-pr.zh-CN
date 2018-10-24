---
title: 使用参数
TOCTitle: 使用参数
ms:assetid: 29ebda0f-ae5f-4512-ad59-240c3605b240
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362778(v=OCS.15)
ms:contentKeyID: 56271124
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用参数

 

_**上一次修改主题：** 2015-06-22_

当使用 Identity 参数时，您可能会注意到参数值 kenmyer@litwareinc.com 用双引号引起来：

    -Identity "kenmyer@litwareinc.com"

不熟悉 Windows PowerShell 的用户经常会问到的其中一个问题是：什么时候应使用双引号和什么时候不应使用双引号？此问题并没有一个简单答案，但是有一些常规规则应遵循：

  - 当参数值为数字时，通常不需要双引号。例如，要限制 [Get-CsOnlineUser](get-csonlineuser.md) cmdlet 返回的用户数，请使用此语法：
    
        -ResultSize 100
    
    事实上，从不应对数字使用双引号。如果您这样做，Windows PowerShell 可能难以将值解释为数字。
    
    同样，请确保不要在数字中包括逗号。例如，如果想要将结果大小设置为 10,000，此语法不正确：
    
        -ResultSize 10,000
    
    此语法将引起错误，因为 Windows PowerShell 使用逗号来分隔参数值。在这种情况下，Windows PowerShell 将假设您正在传递两个单独的参数值：10 和 000。由于不能将结果大小同时设置为 10 和 0，将发生错误。请使用此无逗号的语法：
    
        -ResultSize 10000

  - 当参数值为日期时，通常也不需要双引号：
    
        -StartDate 6/1/2013
    
    但是，只有当不包括时间时，这才成立。如果包括时间（意味着在日期和时间之间放置空格），则参数值必须用双引号引起来：
    
        -StartDate "6/1/2013 10:00AM"
    
    请记住，对于区域设置使用美国英语的计算机，上述命令设置了格式。如果不使用美国英语，应基于您的计算机的设置来设置日期和时间的格式。要检查 Windows PowerShell 使用的区域设置，请从 Windows PowerShell 提示符处运行此命令：
    
        Get-Host | Select-Object CurrentUICulture

  - 字符串值（例如人员的姓名）通常不需要双引号。当字符串值包括受限制的字符（例如空格、逗号或其他标点符号）时，将发生主要异常。例如，此语法有效，因为用户的标识不包括任何受限制的字符：
    
        -Identity "kenmyer@litwareinc.com"
    
    但是，此命令将失败，因为标识包括空格：
    
        -Identity Ken Myer
    
    上述命令失败是因为 Windows PowerShell 使用空格分隔各个参数。这意味着 Windows PowerShell 认为 Identity 参数是 Ken，而 Myer 是一个全新的参数。因此，您将获得以下错误消息：
    
        Get-CsOnlineUser : 找不到接受实际参数"Myer"的位置形式参数.
    
    要使用包括空格（或逗号或任何其他受限制的字符）的参数值，请用双引号将该值引起来：
    
        -Identity "Ken Myer"
    
    在大多数情况下，Windows PowerShell 允许您使用单引号，而不是双引号。例如，这是有效的 Windows PowerShell 语法：
    
        -Identity 'Ken Myer'
    
    但是请注意，字符串的开头和结尾必须使用相同类型的引号。这是无效 Windows PowerShell 语法：
    
        -Identity "Ken Myer'
    
    如果您尝试运行此命令，您将看到 Windows PowerShell 控制台中显示以下信息：
    
    ``` 
    >>
    ```
    
    双箭头是一种提示您完成命令的方法：因为您从双引号开始，Windows PowerShell 期望您使用双引号完成。如果您获得 \>\> 提示，请按 Ctrl-C 取消您的命令，然后再试。

  - 双引号不应与布尔 (True/False) 值一起使用。也请注意，当指定 True/False 时，您必须使用 Windows PowerShell 变量 $True 和 $False。例如：
    
        -EnterpriseVoiceEnabled $True

也有不接受参数值的特定 Windows PowerShell 参数，称为*开关参数*：

    -WhatIf

使用开关参数时不仅不需要参数值，而且包括参数值实际上将引起错误。例如，如果您尝试运行此命令：

    -WhatIf $True

该命令将失败，并显示以下类似错误消息：

    Set-CsUserAcp :  找不到接受实际参数"True"的位置形式参数。

您需要知道可以使用哪些 cmdlet，才能使用 Windows PowerShell 管理 Skype for Business Online。您还必须知道每个 cmdlet 可用的参数，并且必须知道每个参数的*数据类型*（即，参数值是否接受日期值、字符串值、数字等）。此信息（以及有关如何使用 cmdlet 的诸多示例）可以在 Skype for Business Online cmdlet 的帮助主题中找到。例如，以下参数可与 [Set-CsTenantPublicProvider](set-cstenantpublicprovider.md) cmdlet 一起使用：

![特定 PowerShell cmdlet 的参数](images/Dn362778.ead7add1-eec3-4fa4-8bbe-9aa72bb7a1ae(OCS.15).png "特定 PowerShell cmdlet 的参数")

如您所见，参数表提供 cmdlet 的描述；指明参数是必需的（强制性的）还是可选的；以及告诉您每个参数的数据类型。请注意，表中显示的数据类型是 .NET Framework 使用的正式数据类型。这意味着数据类型显示为 System.Management.Automation.SwitchParameter，而不是 Switch Parameter。下面是 Skype for Business Online cmdlet 最常使用的数据类型的快速指南：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>代表用户的标识的字符串值。这通常是用户的 UPN 或 SIP 地址：</p>
<pre><code>-Identity &quot;kenmyer@litwareinc.com&quot;</code></pre></td>
</tr>
<tr class="even">
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN 是完全限定的域名。例如：</p>
<pre><code>-Fqdn &quot;atl-lync-001.litwareinc.com&quot;</code></pre></td>
</tr>
<tr class="odd">
<td><p>System.Boolean</p></td>
<td><p>布尔值是 True/False 值。记住，当指定布尔值时，您必须使用 Windows PowerShell 变量 $True 和 $False：</p>
<pre><code>-Enabled $True -EnterpriseVoiceEnabled $False</code></pre></td>
</tr>
<tr class="even">
<td><p>System.Guid</p></td>
<td><p>GUID 是<em>全局唯一标识符</em>的首字母缩写，它是 Skype for Business Online 中分配给各个 Skype for Business Online 租户的唯一标识符。例如：</p>
<pre><code>-Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</code></pre>
<p>您可以使用此命令检索分配给您的 Skype for Business Online 租户的 GUID：</p>
<pre><code>Get-CsTenant | Select-Object TenantId</code></pre></td>
</tr>
<tr class="odd">
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>开关参数如此命名是因为它们已打开或已关闭。如果参数存在，则可以说开关处于打开状态；如果不存在，则开关处于关闭状态。例如，要使用 Confirm 参数要求在运行命令之前进行确认，请包括 Confirm 参数（不带参数值）作为命令的一部分。例如：</p>
<pre><code>Remove-CsUserAcp -Identity &quot;Ken Myer&quot; -Confirm</code></pre>
<p>如果不希望确认，请不要包括 Confirm 参数：</p>
<pre><code>Remove-CsUserAcp -Identity &quot;Ken Myer&quot;</code></pre></td>
</tr>
<tr class="even">
<td><p>System.String</p></td>
<td><p>字符串值是指一个字母数字值；也就是说，它可以包含（一般而言）可在键盘上键入的任何字符。例如：</p>
<pre><code>-Password &quot;abc123%&amp;*&quot;</code></pre>
<p>字符串值最好用双引号引起来。但并不始终要求这样做。但是，如果字符串值包含空格或逗号，或者是保留的 Windows PowerShell 关键字，则必须这样做。（关键字是指一个命令或者属于 Windows PowerShell 语言本身的一部分的其他元素。例如，“If”和“End”都是 Windows PowerShell 关键字。有关详细信息，请从 Windows PowerShell 命令提示符处键入以下命令：</p>
<p>Get-Help about_Reserved_Words</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Windows PowerShell 和 Lync Online 简介](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

