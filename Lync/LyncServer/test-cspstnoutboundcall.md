---
title: Test-CsPstnOutboundCall
TOCTitle: Test-CsPstnOutboundCall
ms:assetid: 12d940c3-8526-4c8f-8dc1-3fe65a3211bc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398207(v=OCS.15)
ms:contentKeyID: 49312063
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsPstnOutboundCall

 

_**上一次修改主题：** 2015-03-09_

测试用户能否呼叫位于公用电话交换网 (PSTN) 上的电话号码。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsPstnOutboundCall -TargetPstnPhoneNumber <String> -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsPstnOutboundCall -TargetFqdn <String> -TargetPstnPhoneNumber <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsPstnOutboundCall [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## 示例

## 示例 1

示例 1 检查预先配置的测试用户能否登录池 atl-cs-001.litwareinc.com，然后通过 PSTN 网关发起电话呼叫。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义，则此命令将确定第一个测试用户能否登录系统，如果能登录，则向位于 PSTN 网络上的电话发起呼叫。

如果尚未定义测试用户，此命令将失败，因为它不知道进行测试时使用哪个用户。如果没有为池定义测试用户，则必须包含 UserSipAddress 参数以及测试中涉及的用户帐户的相应凭据。然后，**Test-CsPstnOutboundCall** cmdlet 将使用指定的用户执行其检查。

    Test-CsPstnOutboundCall -TargetFqdn atl-cs-001.litwareinc.com -TargetPstnPhoneNumber "+15551234567" 

## 示例 2

示例 2 中显示的命令检验测试用户 (litwareinc\\kenmyer) 能否登录 Lync Server，然后通过 PSTN 网关发起电话呼叫。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Ken Myer 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\kenmyer 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Ken Myer 帐户的密码。）然后将得到的凭据对象存储在名为 $cred1 的变量中。

创建凭据对象后，示例中的第二个命令将确定测试用户能否登录 Lync Server，然后对目标电话号码 (+15551234567) 发起电话呼叫。为完成此任务，将调用带下列参数的 **Test-CsPstnOutboundCall** cmdlet：TargetFqdn（注册器池的 FQDN）、UserSipAddress（发起呼叫的用户的 SIP 地址）、UserCredential（包含测试用户的凭据的 Windows PowerShell 对象）和 TargetPstnPhoneNumber（被叫电话号码）。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPstnOutboundCall -TargetFqdn atl-cs-001.litwareinc.com -TargetPstnPhoneNumber "+15551234567" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

## 示例 3

示例 3 说明了如何在服务器平台模式下使用 **Test-CsPstnOutboundCall** cmdlet。在该模式下，将指定用户的 SIP 地址，但不包含用户凭据。以这种方式运行时，Lync Server 将使用证书对测试用户进行身份验证。

    Test-CsPstnOutboundCall -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress sip:kenmyer@litwareinc.com -TargetPstnPhoneNumber "+15551234567"

## 详细说明

**Test-CsPstnOutboundCall** cmdlet 是 Lync Server“综合事务”的一个示例。在 Lync Server 中使用综合事务可验证用户能否成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

通常以两种不同的方式执行综合事务。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用真实的用户帐户运行综合事务。例如，如果两个用户无法交换即时消息，则管理员可使用这两个相关的用户帐户（而非一对测试帐户）运行综合事务，并尝试诊断和解决问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

Test-CsPstnOutboundCall 也可在服务器平台模式下使用。在此情况下，只需要指定用户的 SIP 地址，Lync Server 将使用证书对该用户进行身份验证。

运行 **Test-CsPstnOutboundCall** cmdlet 时，该 cmdlet 首先尝试使测试用户登录到 Lync Server。如果登录成功，该 cmdlet 随后将尝试通过 PSTN 网关发起电话呼叫。将使用分配给测试帐户的拨号计划、语音策略以及其他策略和设置发起此电话呼叫。应答呼叫时，该 cmdlet 通过网络发送双音多频 (DTMF) 代码以验证媒体连接。

**Test-CsPstnOutboundCall** cmdlet 在执行其测试时将发起真实的电话呼叫：目标电话将响铃，必须接电话测试才能成功。此外，还必须由管理员手动终止此呼叫。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsPstnOutboundCall"}

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
<td><p><em>TargetFqdn</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>要测试的池的完全限定域名 (FQDN)。</p></td>
</tr>
<tr class="even">
<td><p><em>TargetPstnPhoneNumber</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>执行测试时要呼叫的 PSTN 电话号码。目标电话号码最好使用 E.164 格式指定，这意味着该号码将类似“+14255551298”，该号码包含一个加号 (+)，后跟国家/地区呼叫代码 (1)、区号 (425) 和电话号码 (5551298)。指定电话号码时请勿使用短划线、括号或任何其他字符。</p>
<p>如果不使用 E.164 格式，则会将测试用户的拨号计划追加到该号码末尾。Lync Server 随后使用该拨号计划将号码规范化为 E.164 格式。如果无法对号码进行规范化，则无法发起呼叫，测试将失败。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的帐户的用户凭据对象。传递给 UserCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，需要提供用户密码。</p>
<p>如果命令正在使用通过 CsHealthMonitoringConfiguration cmdlet 配置的测试用户，则无需此参数。如果正在服务器平台模式下进行测试，也无需指定此参数。在此情况下，Lync Server 将尝试使用证书对用户进行身份验证。</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>可选</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>测试中使用的身份验证类型。允许的值包括：</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>如果存在此参数，运行该 cmdlet 的详细输出将存储在指定变量中。此变量包含一对方法 ToHTML 和 ToXML，稍后可使用这对方法将该输出保存到 HTML 或 XML 文件中。</p>
<p>若要将输出存储在名为 $TestOutput 的记录器变量中，请使用以下语法：</p>
<p>-OutLoggerVariable TestOutput</p>
<p>注意：在指定变量名称时，不要使用预置 $ 字符。若要将记录器变量中存储的信息保存到 HTML 文件中，请使用如下命令：</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>若要将记录器变量中存储的信息保存到 XML 文件中，请使用与下面类似的命令：</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="odd">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>存在此参数时，运行该 cmdlet 的详细输出将存储在指定变量中。例如，若要将输出存储在名为 $TestOutput 的变量中，可使用以下语法：</p>
<p>-OutVerboseVariable TestOutput</p>
<p>指定变量名称时不要在前面附加 $ 字符。</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的用户帐户的 SIP 地址。例如：-SenderSipAddress &quot;sip:kenmyer@litwareinc.com&quot;。UserSipAddress 参数必须和 UserCredential 引用相同的用户帐户。</p>
<p>如果命令正在使用通过 CsHealthMonitoringConfiguration cmdlet 配置的测试用户，则无需此参数。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsPstnOutboundCall** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsPstnOutboundCall** cmdlet 将返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsPstnPeerToPeerCall](test-cspstnpeertopeercall.md)

