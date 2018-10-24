---
title: Test-CsAddressBookService
TOCTitle: Test-CsAddressBookService
ms:assetid: 8398c9ea-eaab-4a4d-9e09-473ea2b27e22
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398661(v=OCS.15)
ms:contentKeyID: 49313443
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookService

 

_**上一次修改主题：** 2015-03-09_

测试用户访问托管通讯簿下载 Web 服务的服务器的能力。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsAddressBookService -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsAddressBookService -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsAddressBookService -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## 示例

## 示例 1

示例 1 为池 atl-cs-001.litwareinc.com 测试通讯簿下载 Web 服务。此命令使用为池 atl-cs-001.litwareinc.com 预先配置的测试用户测试通讯簿下载 Web 服务。

    Test-CsAddressBookService -TargetFqdn atl-cs-001.litwareinc.com 

## 示例 2

示例 2 中显示的命令同样用于测试运行通讯簿下载 Web 服务的服务器的可用性；但是，在此示例中，这些命令是使用用户 Ken Myer (litwareinc\\kenmyer) 的凭据运行的。为执行此操作，第一个命令使用 **Get-Credential** cmdlet 创建一个包含用户 Ken Myer 的名称和密码的 Windows PowerShell 凭据对象。（由于包含的登录名 litwareinc\\kenmyer 用作参数，因此，Windows PowerShell 凭据请求对话框将仅要求管理员输入 Ken Myer 帐户的密码。）然后，将生成的凭据对象存储在名为 $cred1 的变量中。

在第二个命令中，使用 **Test-CsAddressBookService** cmdlet 测试池 atl-cs-001.litwareinc.com 的通讯簿下载 Web 服务。要使用 Ken Myer 的用户凭据运行此命令，应包含 UserCredential 参数和参数值 $cred1。此外，必须使用 UserSipAddress 参数提供 Ken 的 SIP 地址。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAddressBookService -TargetFqdn atl-cs-001.litwareinc.com -UserCredential $cred1 -UserSipAddress "sip:kenmyer@litwareinc.com"

## 示例 3

示例 3 说明了如何针对 atl-cs-001.litwareinc.com 测试通讯簿下载 Web 服务。为执行此操作，调用带有以下两个参数的 **Test-CsAddressBookService** cmdlet：TargetUri，用于指定通讯簿下载 Web 服务的 URI；UserSipAddress，包含测试中利用的用户帐户的 Windows PowerShell SIP 地址。

``` 


Test-CsAddressBookService -TargetUri https://atl-cs-001.litwareinc.com/abs/handler -UserSipAddress "sip:kenmyer@litwareinc.com"
```

## 详细说明

**Test-CsAddressBookService** cmdlet 是“综合事务”的一个示例。Lync Server 中使用综合事务来验证用户是否能够成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

综合事务通常以两种不同的方式执行。许多管理员会使用 **CsHealthMonitoringConfiguration** cmdlet 为其每一个注册器池设置测试用户。这些测试用户是预先配置的与综合事务配合使用的一对用户。（通常，这些帐户是测试帐户，而不是属于实际用户的帐户。）为池配置测试用户后，管理员可以对该池运行综合事务，而不必指定测试中所涉及的用户帐户的标识（也不必提供该帐户的凭据）。

此外，管理员也可以使用实际用户帐户运行综合事务。例如，如果两位用户无法交换即时消息，则管理员可以使用这两个用户帐户（而不是一对测试帐户）来运行综合事务，然后尝试诊断并解决该问题。如果决定使用实际用户帐户执行综合事务，您需要提供每个用户的登录名和密码。

**Test-CsAddressBookService** cmdlet 提供了一种方法，用于验证用户是否可以连接到通讯簿下载 Web 服务。运行此 cmdlet 时，**Test-CsAddressBookService** cmdlet 将连接到指定池中的通讯簿下载 Web 服务，然后请求通讯簿文件的位置。如果通讯簿下载 Web 服务提供该位置，则将测试视为成功。如果请求被拒绝，则将测试视为失败。

可通过两种不同方式测试通讯簿下载 Web 服务：测试该服务自身或测试关联的 Web 服务。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsAddressBookService** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsAddressBookService"}

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
<td><p>要在其中测试通讯簿下载 Web 服务的注册器池的完全限定域名 (FQDN)。例如：-TargetFqdn &quot;atl-cs-001.litwareinc.com&quot;。</p>
<p>不能在同一个命令中同时使用 TargetUri 参数和 TargetFqdn 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>通讯簿 Web 查询服务的统一资源标识符 (URI)。例如：-TargetUri &quot;https://atl-cs-001.litwareinc.com/abs/handler&quot;。</p>
<p>不能在同一个命令中同时使用 TargetUri 参数和 TargetFqdn 参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>要在测试中使用的用户帐户的用户凭据对象。传递给 UserCredential 的值应是使用 <strong>Get-Credential</strong> cmdlet 获取的对象引用。例如，以下代码返回用户 litwareinc\kenmyer 的凭据对象，并将该对象存储在名为 $x 的变量中：</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>运行此命令时，您需要提供用户密码。</p></td>
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
<td><p><em>External</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>使您可以验证外部用户是否可以使用通讯簿下载 Web 服务。</p></td>
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
<td><p>注册器服务使用的 SIP 端口。如果 Registrar 使用默认端口 5061，则不需要指定此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要在测试中使用的用户的 SIP 地址。如果未指定此参数，则 <strong>Test-CsAddressBookService</strong> 将使用已登录用户的帐户进行检查。</p></td>
</tr>
<tr class="odd">
<td><p><em>WebCredential</em></p></td>
<td><p>可选</p></td>
<td><p>PSCredential</p></td>
<td><p>包含用于访问位置信息服务的用户凭据的对象。可通过调用 <strong>Get-Credential</strong> cmdlet 并提供相应的凭据来检索该对象。</p>
<p>如果指定 TargetUri 和 UserSipAddress 参数，并且从中运行此命令的计算机没有服务器证书，则需要此参数。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsAddressBookService** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsAddressBookService** cmdlet 返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)  
[Update-CsAddressBook](update-csaddressbook.md)

