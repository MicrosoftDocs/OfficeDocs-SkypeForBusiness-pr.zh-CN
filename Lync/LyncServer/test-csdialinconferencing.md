---
title: Test-CsDialInConferencing
TOCTitle: Test-CsDialInConferencing
ms:assetid: e4aedf4f-77ac-4c8b-9613-07f8ea12c041
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399013(v=OCS.15)
ms:contentKeyID: 49314549
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsDialInConferencing

 

_**上一次修改主题：** 2015-03-09_

**Test-CsDialInConferencing** cmdlet 用于检查用户是否可以参与电话拨入式会议会话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsDialInConferencing -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetPstnPhoneNumber <String>] [-UserSipAddress <String>] [-VerifyConferenceJoin <$true | $false>] <COMMON PARAMETERS>

    Test-CsDialInConferencing -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] [-TargetPstnPhoneNumber <String>] [-VerifyConferenceJoin <$true | $false>] <COMMON PARAMETERS>

    Test-CsDialInConferencing [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## 示例

## 示例 1

示例 1 验证预先配置的测试用户是否可以参与池 atl-cs-001.litwareinc.com 中的电话拨入式会议。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义，则该命令将确定第一个测试用户能否登录到 Lync Server。

如果尚未定义测试用户，则该命令将失败，因为该命令无法知道要登录的用户。如果没有为池定义测试用户，则必须包括 UserCredential 参数和尝试登录时此命令应使用的用户凭据。

    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中显示的命令测试特定用户 (litwareinc\\pilar) 参与池 atl-cs-001.litwareinc.com 中的电话拨入式会议的能力。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Pilar Ackerman 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\pilar 用作参数，因此管理员仅需在“Windows PowerShell 凭据请求”对话框中输入 Pilar Ackerman 帐户的密码。）然后，将生成的凭据对象存储在名为 $cred1 的变量中。

然后，第二个命令检查用户 Pilar Ackerman 是否可以登录到池 atl-cs-001.litwareinc.com 并参与电话拨入式会议。为执行此任务，调用了带有以下三个参数的 **Test-CsDialInConferencing** cmdlet：TargetFqdn（注册器池的 FQDN）、UserCredential（包含 Pilar Ackerman 的用户凭据的 Windows PowerShell 对象）以及 UserSipAddress（与所提供的用户凭据对应的 SIP 地址）。

    $cred1 = Get-Credential "litwareinc\pilar"
    
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $cred1

## 详细说明

**Test-CsDialInConferencing** cmdlet 是 Lync Server“综合事务”的一个示例。Lync Server 使用综合事务来验证用户能否成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

综合事务通常以两种不同的方式执行。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用实际用户帐户运行综合事务。例如，如果两位用户无法交换即时消息，则管理员可以使用相关的两个用户帐户（而不是一对测试帐户）来运行综合事务，然后尝试诊断并解决该问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

**Test-CsDialInConferencing** cmdlet 通过尝试使测试用户登录到系统进行工作。（如果您正在使用测试用户，则 **Test-CsDialInConferencing** cmdlet 将使用为该池配置的第一个测试帐户。）如果登录成功，则该 cmdlet 将使用用户的凭据和权限尝试可用的电话拨入式会议访问号码。系统将记录每次电话拨入尝试的成败，然后从 Lync Server 注销该测试用户。

**Test-CsDialInConferencing** cmdlet 只验证是否可以建立相应连接。该 cmdlet 实际上不进行任何电话呼叫，也不创建任何其他用户可以加入的电话拨入式会议。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsDialInConferencing** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsDialInConferencing"}

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>要测试的池的完全限定域名 (FQDN)。</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>要测试的用户帐户的用户凭据对象。传递给 UserCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，您需要提供用户密码。如果您使用运行状况监控配置设置来执行测试，则不需要此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction+AuthenticationMechanism</p></td>
<td><p>测试中使用的身份验证类型。允许的值包括：</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>存在此参数时，运行该 cmdlet 的详细输出将存储在指定变量中。例如，若要将输出存储在名为 $TestOutput 的变量中，可使用以下语法：</p>
<p>-OutVerboseVariable TestOutput</p>
<p>指定变量名称时不要在前面附加 $ 字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要指定此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>TargetPstnPhoneNumber</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将用于验证 PSTN 用户是否可以加入电话拨入式会议的 PSTN 电话的电话号码。例如：</p>
<p>-TargetPstnPhoneNumber &quot;+12065551219&quot;</p>
<p>请注意，只有在使用 VerifyConferenceJoinType 参数时才应包含 TargetPstnPhoneNumber。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要测试的用户帐户的 SIP 地址。例如：-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;。UserSipAddress 参数必须和 UserCredential 引用相同的用户帐户。如果您使用运行状况监控配置设置来执行测试，则不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>VerifyConferenceJoin</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>设置为 True 时，请使用 PSTN 电话验证是否可以加入电话拨入式会议。执行此测试时，您可以选择包括 TargetPstnPhoneNumber。如果这样做，TargetPstnPhoneNumber 必须指定要用于加入会议的 PSTN 电话。如果未包含 TargetPstnPhoneNumber，则 <strong>Test-CsDialInConferencing</strong> cmdlet 将使用预先分配给相应的电话拨入式会议区域的拨入电话号码。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsDialInConferencing** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsDialInConferencing** cmdlet 返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsAVConference](test-csavconference.md)

