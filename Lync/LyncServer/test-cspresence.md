---
title: Test-CsPresence
TOCTitle: Test-CsPresence
ms:assetid: 09a5faf6-4e80-4a3b-ac84-aec9778ee9b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398148(v=OCS.15)
ms:contentKeyID: 49311937
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsPresence

 

_**上一次修改主题：** 2015-03-09_

测试用户能否登录 Lync Server、发布其状态信息并订阅另一个用户发布的状态信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsPresence -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-PublisherSipAddress <String>] [-RegistrarPort <Int32>] [-SubscriberSipAddress <String>] <COMMON PARAMETERS>

    Test-CsPresence -PublisherCredential <PSCredential> -PublisherSipAddress <String> -SubscriberCredential <PSCredential> -SubscriberSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsPresence [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-SubscriberSipAddress <String>]

## 示例

## 示例 1

示例 1 检查预配置的一对测试用户能否登录池 atl-cs-001.litwareinc.com。测试用户登录之后，**Test-CsPresence** cmdlet 将检查这两个用户能否交换状态信息。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义注册器，此命令将确定第一个测试用户能否登录系统，然后检查该用户能否与为池定义的第二个测试用户交换状态信息。

如果尚未定义注册器，则此命令将会失败，原因是在进行测试时此命令不知道使用哪些用户。如果您尚未为池定义测试用户，则必须包含 SubscriberSipAddress 和 PublisherSipAddress 参数，以及作为状态订阅者和状态发布者的用户的相应凭据。然后，**Test-CsPresence** cmdlet 将使用这两个指定的用户执行检查。

    Test-CsPresence -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）能否登录 Lync Server 并交换状态信息。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Pilar Ackerman 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\pilar 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Pilar Ackerman 帐户的密码。）然后将得到的凭据对象存储在名为 $cred1 的变量中。第二个命令执行相同操作，但这次返回的是 Ken Myer 帐户的凭据对象。

有了这两个凭据对象，示例中的第三个命令即可确定这两个用户能否登录 Lync Server 并交换状态信息。为完成此任务，将调用带下列参数的 **Test-CsPresence** cmdlet：TargetFqdn（注册器池的 FQDN）、SubscriberSipAddress（某个测试用户的 SIP 地址）、SubscriberCredential（包含该用户的凭据的 Windows PowerShell 对象）、PublisherSipAddress（另一个测试用户的 SIP 地址）和 PublisherCredential（包含另一个用户的凭据的 Windows PowerShell 对象）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPresence -TargetFqdn atl-cs-001.litwareinc.com -SubscriberSipAddress "sip:pilar@litwareinc.com" -SubscriberCredential $cred1 -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $cred2

## 详细说明

**Test-CsPresence** cmdlet 是 Lync Server“综合事务”的一个示例。在 Lync Server 中使用综合事务可验证用户能否成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

通常以两种不同的方式执行综合事务。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。通常，这些帐户是测试帐户，而不是属于实际用户的帐户。为池配置这些用户帐户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

或者，管理员也可以使用真实的用户帐户运行综合事务。例如，如果两个用户无法交换即时消息，管理员可以使用这两个相关的用户帐户（而非一对测试帐户）运行综合事务，尝试诊断和解决问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

**Test-CsPresence** cmdlet 用于确定一对测试用户能否登录 Lync Server，然后交换状态信息。为此，此 cmdlet 首先使这两个用户登录系统。如果登录成功，第一个测试用户随后将要求从第二个用户接收状态信息。第二个用户发布此信息，然后 **Test-CsPresence** cmdlet 将验证是否已将信息成功传输给第一个用户。交换状态信息之后，将从 Lync Server 注销这两个测试用户。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsPresence"}

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
<td><p><em>PublisherCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的两个用户帐户中第一个用户帐户的用户凭据对象。传递给 PublisherCredential 的值应当是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，需要提供用户密码。</p>
<p>如果使用池的运行状况监视配置设置运行测试，则不需要发布方凭据。</p></td>
</tr>
<tr class="even">
<td><p><em>SubscriberCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的用户凭据对象。传递给 SubscriberCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\pilar 的凭据对象，并将该对象存储在名为 $y 的变量中：</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>运行此命令时，需要提供用户密码。</p>
<p>如果使用池的运行状况监视配置设置运行测试，则不需要订阅者凭据。</p></td>
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
<td><p><em>PublisherSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的 SIP 地址。例如：-PublisherSipAddress &quot;sip:kenmyer@litwareinc.com&quot;。PublisherSipAddress 参数必须与 PublisherCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>SubscriberSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的两个用户帐户中第二个用户帐户的 SIP 地址。例如：-SubscriberSipAddress &quot;sip:pilar@litwareinc.com&quot;。SubscriberSipAddress 参数必须与 SubscriberCredential 引用相同的用户帐户。</p>
<p>如果您使用池的运行状况监控配置设置来运行测试，则不需要 SIP 地址。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsPresence** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsPresence** cmdlet 将返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsRegistration](test-csregistration.md)

