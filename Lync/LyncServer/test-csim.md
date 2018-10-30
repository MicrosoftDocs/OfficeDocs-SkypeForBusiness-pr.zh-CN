---
title: Test-CsIM
TOCTitle: Test-CsIM
ms:assetid: 2fdab54c-5ec4-4db5-b29c-a3efaae68f66
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425802(v=OCS.15)
ms:contentKeyID: 49312402
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsIM

 

_**上一次修改主题：** 2015-03-09_

测试两个用户能否交换即时消息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsIM -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> -SenderCredential <PSCredential> -SenderSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsIM -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] <COMMON PARAMETERS>

    Test-CsIM [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-EmailHost <String>] [-Force <SwitchParameter>] [-IsSsl <$true | $false>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-Password <String>] [-Port <UInt16>] [-TestLegalIntercept <SwitchParameter>] [-Username <String>] [-WaitSeconds <Int16>]

## 示例

## 示例 1

示例 1 检查预先配置的一对测试用户能否登录池 atl-cs-001.litwareinc.com，然后交换即时消息。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义，则此命令将确定两个用户能否登录系统，如果能够登录，则随后还将确定这两个用户能否交换即时消息。

如果尚未定义测试用户，该命令将失败，因为它不知道进行测试时使用哪个用户。如果没有为池定义注册器，则必须包含 SenderSipAddress 和 ReceiverSipAddress 参数以及 IM 会话中涉及的用户的相应凭据。然后，**Test-CsIM** cmdlet 将使用这两个指定的用户执行其检查。

    Test-CsIm -TargetFqdn atl-cs-001.litwareinc.com

## 示例 2

示例 2 中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）能否登录 Lync Server，然后交换即时消息。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Pilar Ackerman 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\pilar 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Pilar Ackerman 帐户的密码。）然后将得到的凭据对象存储在名为 $cred1 的变量中。第二个命令执行相同操作，但这次返回的是 Ken Myer 帐户的凭据对象。

创建这两个凭据对象后，示例中的第三个命令将确定这两个用户能否登录 Lync Server，然后交换即时消息。为执行此操作，将调用带下列参数的 **Test-CsIM** cmdlet：TargetFqdn（注册器池的 FQDN）、SenderSipAddress（第一个测试用户的 SIP 地址）、SenderCredential（包含此用户的凭据的 Windows PowerShell 对象）、-ReceiverSipAddress（另一个测试用户的 SIP 地址）以及 ReceiverCredential（包含另一个用户的凭据的 Windows PowerShell 对象）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsIm -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

## 详细说明

**Test-CsIM** cmdlet 是 Lync Server“综合事务”的一个示例。在 Lync Server 中使用综合事务可验证用户能否成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

通常以两种不同的方式执行综合事务。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用真实的用户帐户运行综合事务。例如，如果两个用户无法交换即时消息，则管理员可使用这两个相关的用户帐户（而非一对测试帐户）运行综合事务以尝试诊断和解决问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的凭据。

**Test-CsIM** cmdlet 首先尝试让一对测试用户登录到 Lync Server。假定这两次登录成功，此 cmdlet 随后将在这两个测试用户之间发起即时消息 (IM) 会话。（用户 1 邀请用户 2 加入 IM 会话，然后用户 2 接受邀请。）验证能否在两个用户之间交换消息之后，**Test-CsIM** cmdlet 将结束该 IM 会话，并将这两个用户从系统中注销。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsIM"}

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
<p>运行此命令时，需要提供用户密码。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要接收方凭据。</p></td>
</tr>
<tr class="even">
<td><p><em>SenderCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的用户凭据对象。传递给 SenderCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，需要提供用户密码。</p>
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
<td><p>SipSyntheticTransaction + AuthenticationMechanism</p></td>
<td><p>测试中使用的身份验证类型。允许的值包括：</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>EmailHost</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>Legal Intercept 测试中使用的用户的电子邮件主机。例如：</p>
<p>-EmailHost &quot;litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>IsSsl</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，将指定正使用安全套接字层 (SSL) 协议开展测试。</p></td>
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
<td><p><em>Password</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>Legal Intercept 测试中使用的用户的密码。</p></td>
</tr>
<tr class="odd">
<td><p><em>Port</em></p></td>
<td><p>可选</p></td>
<td><p>UInt16</p></td>
<td><p>用于 Legal Intercept 服务的端口。</p></td>
</tr>
<tr class="even">
<td><p><em>ReceiverSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第一个用户帐户的 SIP 地址。例如：-ReceiverSipAddress &quot;sip:jhaas@litwareinc.com&quot;。ReceiverSipAddress 参数必须与 ReceiverCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>SenderSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的 SIP 地址。例如：-SenderSipAddress &quot;sip:kenmyer@litwareinc.com&quot;。SenderSipAddress 参数必须与 SenderCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>TestLegalIntercept</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>如果使用此使用，则指示 Test-CsIM 测试指定用户的 Legal Intercept 服务。</p></td>
</tr>
<tr class="even">
<td><p><em>Username</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>Legal Intercept 测试中使用的用户的用户名。</p></td>
</tr>
<tr class="odd">
<td><p><em>WaitSeconds</em></p></td>
<td><p>可选</p></td>
<td><p>Int16</p></td>
<td><p>指定系统应等待 Legal Intercept 服务进行响应的时间长度（以秒为单位）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsIM** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsIM** cmdlet 将返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsGroupIM](test-csgroupim.md)

