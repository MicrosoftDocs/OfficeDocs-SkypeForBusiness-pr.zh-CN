---
title: Test-CsLocationPolicy
TOCTitle: Test-CsLocationPolicy
ms:assetid: 49f7d148-d46d-4bcc-af9d-6a3a0fdde8ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425962(v=OCS.15)
ms:contentKeyID: 49312760
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsLocationPolicy

 

_**上一次修改主题：** 2015-03-09_

根据在参数值中指定的标准运行测试，以确定将要使用的位置策略。位置策略包含的设置可确定是否应用增强型 9-1-1 (E9-1-1) 以及应用的方式。E9-1-1 可以帮助 911 紧急呼叫的应答者确定呼叫者的地理位置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsLocationPolicy -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsLocationPolicy -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsLocationPolicy [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-Subnet <String>]

## 示例

## 示例 1

此示例可确定当前用户（或当前配置用户）的位置策略。TargetFqdn 是必需的参数。

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中的第一行调用 Windows PowerShell **Get-Credential** cmdlet。此 cmdlet 将检索用户凭据，并将它们作为安全对象返回。为此 cmdlet 提供的唯一参数是用户 ID。运行此 cmdlet 将打开一个要使用所提供用户 ID 预填充的对话框，并且会显示一个文本框，允许您键入用户密码。这些用户凭据保存为变量 $cred。

第 2 行调用 **Test-CsLocationPolicy** cmdlet。与示例 1 一样，我们提供目标 FQDN。但是，在此示例中我们不使用预配置的用户，而是准备对 SIP 地址为 kenmyer@litwareinc.com 的用户运行测试。我们将该值（sip: 前缀）传递到 UserSipAddress 参数，并将该用户的凭据（保存在 $cred 变量中）传递到 UserCredential 参数。

    $cred = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred -UserSipAddress "sip:kenmyer@litwareinc.com"

## 示例 3

此示例与示例 2 类似，但没有指定用户凭据。如果在未指定用户凭据的情况下调用 **Test-CsLocationPolicy** cmdlet，将使用运行此 cmdlet 的计算机上的服务器证书来进行身份验证并发现用户的位置策略。如果计算机上没有服务器证书，则必须指定如示例 2 中所示的凭据。要了解计算机上是否有服务器证书，请调用 **Get-CsCertificate** cmdlet。

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com"

## 示例 4

此示例可确定子网 ID 为 172.15.11.0 的子网的位置策略。如果该子网不与位置策略关联，则将检索当前配置用户的位置策略。

注意：通过将 **Set-CsNetworkSite** cmdlet 的 LocationPolicy 参数设置为位置策略 ID，然后将 **Set-CsNetworkSubnet** cmdlet 的 NetworkSiteId 参数设置为该站点的 ID，可以设置子网的位置策略。例如：

Set-CsNetworkSite Portland –LocationPolicy Reno

Set-CsNetworkSubnet 175.15.11.0 –NetworkSiteID Portland

    Test-CsLocationPolicy -TargetFqdn atl-cs-001.litwareinc.com -Subnet 172.15.11.0

## 详细说明

可以使用位置策略来应用与 E9-1-1 功能和客户端位置相关的设置。位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。例如，您可以使用位置策略定义哪些数字构成紧急呼叫（在美国为 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。此 cmdlet 将返回有关从特定池、子网、交换机或无线接入点的某一客户端发出呼叫时可使用的位置策略的信息。

如果在调用此 cmdlet 的过程中没有指定用户，则将对当前配置的用户进行测试。要查找当前配置的用户，请调用 **Get-CsHealthMonitoringConfiguration** cmdlet。要设置配置的用户，请调用 **Set-CsHealthMonitoringConfiguration** cmdlet。

如果找到了用户或子网的位置策略，测试将成功执行。默认情况下，返回的信息中包含位置策略（如果分配了每用户策略）的名称以及是为用户还是子网启用 E9-1-1。包括用于检索其他测试信息的 Windows PowerShell 通用参数 Verbose。

可以测试用户或网络子网的位置策略。如果通过指定 Subnet 参数的值对子网运行测试，则 cmdlet 将尝试解析该子网的位置策略。如果没有位置策略分配到子网，则将检索配置用户的位置策略。如果子网策略检索成功，则输出将包括以 subnet-tagid 开头的 LocationPolicyTagID 值。如果未找到子网的位置策略，则 LocationPolicyTagID 将以 user-tagid 开头。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsLocationPolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsLocationPolicy"}

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
<td><p>托管指定用户或子网的池的完全限定域名 (FQDN)（如果没有指定用户，则假定使用预配置的用户或是当前用户）。</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>包含正在进行位置策略测试的用户帐户的用户 ID 和密码的对象。通过调用 <strong>Get-Credential</strong> cmdlet、填写正确的信息并将输出保存为变量，可以检索凭据对象。</p></td>
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
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
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
<td><p>String</p></td>
<td><p>存在此参数时，运行该 cmdlet 的详细输出将存储在指定变量中。例如，若要将输出存储在名为 $TestOutput 的变量中，可使用以下语法：</p>
<p>-OutVerboseVariable TestOutput</p>
<p>指定变量名称时不要在前面附加 $ 字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务的端口号。</p></td>
</tr>
<tr class="even">
<td><p><em>Subnet</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试其位置策略的网络子网的 ID（IP 地址）。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要测试其位置策略的用户的 SIP 地址。格式必须是 sip:&lt; 用户 ID &gt;，例如，sip:kenmyer@litwareinc.com。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

**Test-CsLocationPolicy** cmdlet 可返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[New-CsLocationPolicy](new-cslocationpolicy.md)  
[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Set-CsLocationPolicy](set-cslocationpolicy.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Grant-CsLocationPolicy](grant-cslocationpolicy.md)  
[Get-CsHealthMonitoringConfiguration](get-cshealthmonitoringconfiguration.md)  
[Set-CsHealthMonitoringConfiguration](set-cshealthmonitoringconfiguration.md)  
[Set-CsNetworkSite](set-csnetworksite.md)

