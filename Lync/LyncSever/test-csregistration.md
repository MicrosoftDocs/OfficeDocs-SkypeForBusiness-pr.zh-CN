---
title: Test-CsRegistration
TOCTitle: Test-CsRegistration
ms:assetid: 9e38cb36-c97a-43f2-97fe-64759f663be2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412737(v=OCS.15)
ms:contentKeyID: 49313753
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsRegistration

 

_**上一次修改主题：** 2015-03-09_

测试用户登录 Lync Server 的能力。**Test-CsRegistration** cmdlet 是一种“综合事务”：对常见的 Lync Server 活动的模拟，用于监控运行状况和性能。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsRegistration -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsRegistration -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsRegistration [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## 示例

## 示例 1

示例 1 为池 atl-cs-001.litwareinc.com 测试注册器服务。只有已为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会有效。如果已定义，则该命令将确定第一个测试用户能否登录到 Lync Server。

如果尚未定义测试用户，则该命令将失败，因为该命令无法知道要登录的用户。如果尚未定义池的测试用户，则必须包括 UserSipAddress 参数以及尝试登录时命令会使用的用户凭据。

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中显示的命令测试特定用户 (litwareinc\\pilar) 能否登录到 Lync Server。为执行此操作，示例中的第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Pilar Ackerman 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\pilar 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Pilar Ackerman 帐户的密码。）然后，将生成的凭据对象存储在名为 $cred1 的变量中。

然后，第二个命令检查此用户是否能够登录到池 atl-cs-001.litwareinc.com。为执行此任务，调用了带有以下三个参数的 **Test-CsRegistration** cmdlet：TargetFqdn（注册器池的 FQDN）、UserCredential（包含 Pilar Ackerman 的用户凭据的 Windows PowerShell 对象）以及 UserSipAddress（与所提供的用户凭据对应的 SIP 地址）。

    $cred1 = Get-Credential "litwareinc\pilar"
    
    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred1 -UserSipAddress "sip:pilar@litwareinc.com"

## 详细说明

**Test-CsRegistration** cmdlet 是 Lync Server“综合事务”的一个示例。Lync Server 中使用综合事务来验证用户是否能够成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

通常以两种不同的方式执行综合事务。许多管理员会使用 CsHealthMonitoringConfiguration cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员只需对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用实际用户帐户来运行综合事务。例如，如果两个用户无法交换即时消息，管理员可以使用这两个用户帐户（而非两个测试帐户）运行综合事务，然后尝试诊断并解决问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

使用 **Test-CsRegistration** cmdlet，您可以验证组织中的用户能否登录 Lync Server。为执行此检查，**Test-CsRegistration** cmdlet 需要单个测试帐户。如果已为待测试的池设置了测试用户，则无需指定帐户，**Test-CsRegistration** cmdlet 将自动使用分配给池的第一个测试帐户。（有关详细信息，请参阅 [New-CsHealthMonitoringConfiguration](new-cshealthmonitoringconfiguration.md) cmdlet 帮助主题。）或者，也可以使用尚未分配到池的帐户执行测试。这样，即使您没有配置测试用户也能运行测试。此外，还允许测试某个特定用户是否可以登录到 Lync Server。（如果选择使用此方法，您需要提供测试帐户的用户名和密码。）

运行 **Test-CsRegistration** cmdlet 后，此 cmdlet 会尝试将该测试用户登录到 Lync Server 上，如果成功，便会断开此用户与系统的连接。所有这些无需用户进行任何干预，并且不会影响任何真实用户。例如，假定 sip:kenmyer@litwareinc.com 测试帐户对应于拥有真实 Lync Server 帐户的某位真实用户。在该情况下，执行测试不会对真实的 Ken Myer 造成任何干扰。在 Ken Myer 测试帐户从系统中注销后，Ken Myer 本人还继续处于登录状态。

通过添加 Verbose 参数，可以获取 **Test-CsRegistration** cmdlet 为完成其测试所执行的所有操作的详细说明。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsRegistration"}

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
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>待测试帐户的用户凭据对象。传递到 UserCredential 的值必须是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，此代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在变量</p>
<p>$x 中：$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，需要提供用户密码。如果使用池的运行状况监控配置设置执行测试，则不需要此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>可选</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>测试中使用的身份验证类型。允许的值包括：</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>存在此参数时，运行该 cmdlet 的详细输出将存储在指定变量中。例如，若要将输出存储在名为 $TestOutput 的变量中，可使用以下语法：</p>
<p>-OutVerboseVariable TestOutput</p>
<p>指定变量名称时不要在前面附加 $ 字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试的用户帐户的 SIP 地址，例如：-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;。UserSipAddress 参数必须和 UserCredential 引用相同的用户帐户。如果使用池的运行状况监控配置设置执行测试，则不需要此参数。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsRegistration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsRegistration** cmdlet 可返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

