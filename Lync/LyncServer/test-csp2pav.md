---
title: Test-CsP2PAV
TOCTitle: Test-CsP2PAV
ms:assetid: acb01fb7-4685-4f38-a724-8c2ae8e0219a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412821(v=OCS.15)
ms:contentKeyID: 49313903
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsP2PAV

 

_**上一次修改主题：** 2015-03-09_

测试一对用户进行对等音频/视频 (A/V) 呼叫的能力。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsP2PAV -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> -SenderCredential <PSCredential> -SenderSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsP2PAV -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] <COMMON PARAMETERS>

    Test-CsP2PAV [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## 示例

## 示例 1

示例 1 检查预先配置的一对测试用户能否登录池 atl-cs-001.litwareinc.com，并在之后进行对等音频/视频呼叫。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义，则该命令将确定这两个用户能否登录系统，若能登录，将确定他们能否使用音频/视频呼叫进行对话。

如果尚未定义测试用户，则此命令将失败，因为它不知道进行测试时使用哪个用户。如果没有为池定义测试用户，则必须包含 SenderSipAddress 和 ReceiverSipAddress 参数以及即时消息交换中涉及的用户的相应凭据。然后，**Test-CsP2PAV** cmdlet 将使用两个指定的用户进行检查。

    Test-CsP2PAV -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）能否登录 Lync Server，并在之后进行对等音频/视频呼叫。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Pilar Ackerman 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\pilar 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Pilar Ackerman 帐户的密码。）然后，将生成的凭据对象存储在名为 $cred1 的变量中。第二个命令执行相同的操作，这次返回 Ken Myer 帐户的凭据对象。

有了这两个凭据对象，此示例中的第三个命令可确定这两个用户能否登录 Lync Server 并进行对等音频/视频呼叫。为执行此任务，调用带有下列参数的 **Test-CsP2PAV** cmdlet：TargetFqdn（注册器池的 FQDN）、SenderSipAddress（第一个测试用户的 SIP 地址）、SenderCredential（包含同一用户的凭据的 Windows PowerShell 对象）、ReceiverSipAddress（另一个测试用户的 SIP 地址）以及 ReceiverCredential（包含另一个测试用户的凭据的 Windows PowerShell 对象）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsP2PAV -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

## 详细说明

**Test-CsP2PAV** cmdlet 是 Lync Server“综合事务”的一个示例。Lync Server 中使用综合事务来验证用户是否能够成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

综合事务通常以两种不同的方式执行。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用实际用户帐户运行综合事务。例如，如果两位用户无法交换即时消息，则管理员可以使用相关的两个用户帐户（而不是一对测试帐户）来运行综合事务，然后尝试诊断并解决该问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

**Test-CsP2PAV** cmdlet 用于确定两个测试用户能否加入对等音频/视频 (A/V) 对话。要测试此方案，cmdlet 首先使这两个用户登录到 Lync Server。假设这两个用户登录成功，然后第一个用户邀请第二个用户加入 A/V 呼叫。第二个用户接受呼叫，将测试两个用户之间的连接；然后呼叫结束，测试用户从系统中注销。

**Test-CsP2PAV** cmdlet 并不会实际进行 A/V 呼叫，也不会在测试用户之间交换多媒体信息。此 cmdlet 只是验证能否建立相应的连接，以及两个用户能否进行这样的呼叫。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsP2PAV"}

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
<td><p><em>ReceiverCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的两个用户帐户中第一个用户帐户的用户凭据对象。传递给 ReceiverCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\pilar 的凭据对象，并将该对象存储在名为 $y 的变量中：</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>运行此命令时，您需要提供用户密码。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要接收方凭据。</p></td>
</tr>
<tr class="even">
<td><p><em>SenderCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的用户凭据对象。传递给 SenderCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，您需要提供用户密码。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要发送方凭据。</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>要测试的池的完全限定域名 (FQDN)。</p></td>
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
<td><p>String</p></td>
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
<td><p><em>ReceiverSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第一个用户帐户的 SIP 地址。例如：-ReceiverSipAddress &quot;sip:pilar@litwareinc.com&quot;。ReceiverSipAddress 参数必须与 ReceiverCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要指定此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>SenderSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第二个帐户的 SIP 地址。例如：-SenderSipAddres &quot;sip:kenmyer@litwareinc.com&quot;。SenderSipAddress 参数必须与 SenderCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsP2PAV** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsP2PAV** cmdlet 返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsAVConference](test-csavconference.md)

