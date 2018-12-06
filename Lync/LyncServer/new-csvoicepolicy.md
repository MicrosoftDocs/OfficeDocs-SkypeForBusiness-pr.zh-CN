---
title: New-CsVoicePolicy
TOCTitle: New-CsVoicePolicy
ms:assetid: 3852de89-a604-437a-9fdf-3597b88ce13d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425856(v=OCS.15)
ms:contentKeyID: 49312500
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsVoicePolicy

 

_**上一次修改主题：** 2015-03-09_

创建新的语音策略。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsVoicePolicy -Identity <XdsIdentity> [-AllowCallForwarding <$true | $false>] [-AllowPSTNReRouting <$true | $false>] [-AllowSimulRing <$true | $false>] [-CallForwardingSimulRingUsageType <VoicePolicyUsage | InternalOnly | CustomUsage>] [-Confirm [<SwitchParameter>]] [-CustomCallForwardingSimulRingUsages <PSListModifier>] [-Description <String>] [-EnableBWPolicyOverride <$true | $false>] [-EnableCallPark <$true | $false>] [-EnableCallTransfer <$true | $false>] [-EnableDelegation <$true | $false>] [-EnableMaliciousCallTracing <$true | $false>] [-EnableTeamCall <$true | $false>] [-EnableVoicemailEscapeTimer <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Name <String>] [-PreventPSTNTollBypass <$true | $false>] [-PstnUsages <PSListModifier>] [-PSTNVoicemailEscapeTimer <Int64>] [-Tenant <Guid>] [-VoiceDeploymentMode <OnPrem | Online | OnlineBasic | OnPremOnlineHybrid>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例使用默认的设置创建一个新的每用户语音策略，其 Identity 为 UserVoicePolicy1。

    New-CsVoicePolicy -Identity UserVoicePolicy1

## 示例 2

此示例创建一个新的 Identity 为 UserVoicePolicy2 的每用户语音策略，并将 AllowSimulRing 属性设置为 False，这意味着分配了此策略的所有用户都不会启用同时响铃，同时响铃功能确定是否可以将另一个电话（例如移动电话）设置为在每次用户的办公电话响铃时也同时响铃。此命令还将“Local”添加到 PSTN 用法列表，它可将此语音策略与也使用 Local PSTN 用法的语音路由关联。（请注意，没有显式指定 Identity 参数。Identity 参数是一个位置参数，因此如果您将标识值放在参数列表的最前面，则无需显式声明它就是 Identity。）

    New-CsVoicePolicy UserVoicePolicy2 -AllowSimulRing $false -PstnUsages @{add = "Local"}

## 示例 3

此示例为站点 Redmond 创建一个新语音策略，并将为组织定义的所有 PSTN 用法应用于此策略。此示例中的第一行调用 **Get-CsPstnUsage** cmdlet，以检索组织的全局 PSTN 用法集并将其保存在变量 $a 中。第二行调用 **New-CsVoicePolicy** cmdlet，为站点 Redmond 创建新的语音策略。并且将一个值传递给 PstnUsages 参数，以将包含在全局 PSTN 用法集中的列表添加到此策略中。请注意，添加值的语法如下：$a.Usage。这指的是 PSTN 用法设置的 Usage 属性，它包含 PSTN 用法列表。

    $a = Get-CsPstnUsage
    New-CsVoicePolicy site:Redmond -PstnUsages @{add = $a.Usage}

## 详细说明

此 cmdlet 可创建新的语音策略。语音策略用于管理诸如同时响铃（每次有人拨打办公电话时可以同时使第二部电话响铃的功能）和呼叫转接等企业语音相关功能。此 cmdlet 创建的策略可决定是否启用这些功能中的多数功能。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsVoicePolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsVoicePolicy"}

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
<td><p>XdsIdentity</p></td>
<td><p>用于指定范围或策略名称的唯一标识符。此 cmdlet 的有效值为 site:&lt;站点名称&gt;（其中 &lt;站点名称&gt; 是应用此策略的 Lync Server 站点的名称，例如 site:Redmond），以及用于指定每用户策略的字符串（如 RedmondVoicePolicy）。默认情况下存在全局策略。</p></td>
</tr>
<tr class="even">
<td><p><em>AllowCallForwarding</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果此参数设置为 True，则可以转接呼叫。如果此参数设置为 False，则无法转接呼叫。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowPSTNReRouting</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>当此参数设置为 True 时，将通过公用电话交换网 (PSTN) 路由对另一个池中托管的内部号码发出的呼叫（如果该池或 WAN 不可用）。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>AllowSimulRing</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>同时响铃功能允许在拨打一个号码时多个电话同时响铃。如果此参数设置为 True，则将启用此功能。如果此参数设置为 False，则不能为分配了此策略的任何用户配置同时响铃。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>CallForwardingSimulRingUsageType</em></p></td>
<td><p>可选</p></td>
<td><p>CallForwardingSimulRingUsageType</p></td>
<td><p>为管理员提供了一种管理呼叫转接和同时响铃的方法。允许的值包括：</p>
<p>* VoicePolicyUsage – 该默认语音策略用法用于管理所有呼叫上的呼叫转接和同时响铃。此值为默认值。</p>
<p>* InternalOnly – 呼叫转接和同时响铃仅限于从一个 Lync 用户到另一个用户的呼叫。</p>
<p>* CustomUsage。自定义 PSTN 用法将用于管理呼叫转接和同时响铃。必须使用 CustomCallForwardingSimulRingUsages 参数指定此用法。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>CustomCallForwardingSimulRingUsages</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>用于管理所有呼叫转接和同时响铃的自定义 PSTN 用法。若要将自定义用法添加到语音策略，请使用以下类似语法：</p>
<p>-CustomCallForwardingSimulRingUsages @{Add=&quot;RedmondPstnUsage&quot;}</p>
<p>若要删除自定义用法，请使用以下语法：</p>
<p>-CustomCallForwardingSimulRingUsages @{Remove=&quot;RedmondPstnUsage&quot;}</p>
<p>请注意，必须先存在用法，然后才能将其与 CustomCallForwardingSimulRingUsages 参数一起使用。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>语音策略的描述。</p>
<p>最大长度：1040 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableBWPolicyOverride</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>可以将策略设置为管理网络配置，包括限制带宽。如果将此参数设置为 True，则可以覆盖这些策略。换言之，如果此参数设置为 True，则将不会进行任何带宽检查，无论呼叫允许控制 (CAC) 设置如何，呼叫都将接通。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableCallPark</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>通过 呼叫寄存应用程序，可以在一组号码中的某个号码上保持或寄存呼叫，以便稍后取回。如果此参数设置为 True，则将启用此应用程序。如果此参数设置为 False，则分配给此策略的用户无法寄存来电。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableCallTransfer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>决定是否可以将呼叫转接至其他号码。如果此参数设置为 True，则可以转接呼叫；如果设置为 False，则不能转接呼叫。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDelegation</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>呼叫委派允许用户为其他用户接听电话或者代表其他用户发出呼叫。例如，经理可以设置呼叫委派，以便来电时，经理的电话和管理员的电话同时响铃。如果此参数设置为 True，则拥有此策略的用户将可以设置呼叫委派。如果此参数设置为 False，则禁用呼叫委派。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMaliciousCallTracing</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>恶意呼叫跟踪功能是一种标准功能，用于跟踪用户指定为恶意呼叫的呼叫。即使呼叫者 ID 被阻止，也可以跟踪这些呼叫。只有相应的权威机构可以使用此跟踪功能，用户不能使用此功能。如果此属性设置为 True，则可以对恶意呼叫设置跟踪功能。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableTeamCall</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>团队呼叫允许用户指定一组其他用户，这些用户的电话会在该用户收到来电时响铃。此功能在团队中非常有用，例如，团队中的任何人都可以接听客户的来电。如果此参数设置为 True，则将启用此功能。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableVoicemailEscapeTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，对未应答移动设备的呼叫将路由至组织语音邮件，而不是移动设备提供商的语音邮件。如果“太早”应答呼叫（即，为 PSTNVoicemailEscapeTimer 属性配置的时间值尚未用完），则会假设该移动设备不可用且该呼叫将路由至组织语音邮件。</p>
<p>默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>一个描述此策略的可显示名称。</p>
<p>默认值：DefaultPolicy</p></td>
</tr>
<tr class="odd">
<td><p><em>PreventPSTNTollBypass</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>PSTN 费通常称为长途电话费。有时候，组织可以通过实施 IP 语音 (VoIP) 解决方案来避免支付这些费用，此解决方案可使分支机构通过网络呼叫进行连接。如果此参数设置为 True，则将通过 PSTN 发送呼叫并且需要支付费用，而不是通过网络发送呼叫以避免支付费用。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>PstnUsages</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>适用于此策略的 PSTN 用法列表。PSTN 用法将语音策略与电话路由关联在一起。</p>
<p>可以将任意字符串值放置在此列表中（只要该值存在于 PSTN 用法的当前全局列表中）。（不允许放置重复的字符串；所有字符串都必须是唯一的。）可以通过调用 <strong>Get-CsPstnUsage</strong> cmdlet 来检索 PSTN 用法列表。</p>
<p>默认情况下，此列表为空。如果您不为此参数提供值，将会收到一条警告消息，指出授予了此策略的用户将无法发起出站 PSTN 呼叫。</p></td>
</tr>
<tr class="odd">
<td><p><em>PSTNVoicemailEscapeTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Int64</p></td>
<td><p>用于确定对呼叫的应答是否“太早”的时间（以毫秒为单位）。如果在此时间间隔内收到响应，Lync Server 将假设该移动设备不可用并且会自动将呼叫切换到组织的语音邮箱。如果在此时间间隔结束前未收到响应，将允许该呼叫继续进行。默认值为 1500 毫秒。</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>Guid</p></td>
<td><p>要为其创建新语音策略的 Skype for Business Online 租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceDeploymentMode</em></p></td>
<td><p>可选</p></td>
<td><p>VoiceDeploymentMode</p></td>
<td><p>允许的值包括：</p>
<p>* OnPrem</p>
<p>* Online</p>
<p>* OnlineBasic</p>
<p>* OnPremOnlineHybrid</p>
<p>默认值为 OnPrem。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

此 cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Voice.VoicePolicy 对象的实例。

## 另请参阅

#### 其他资源

[Remove-CsVoicePolicy](remove-csvoicepolicy.md)  
[Set-CsVoicePolicy](set-csvoicepolicy.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Grant-CsVoicePolicy](grant-csvoicepolicy.md)  
[Test-CsVoicePolicy](test-csvoicepolicy.md)  
[Get-CsPstnUsage](get-cspstnusage.md)

