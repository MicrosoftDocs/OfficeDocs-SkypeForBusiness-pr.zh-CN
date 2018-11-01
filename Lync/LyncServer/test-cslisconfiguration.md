---
title: Test-CsLisConfiguration
TOCTitle: Test-CsLisConfiguration
ms:assetid: 6983d42e-6b93-4365-b0f1-81031d6e251b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398497(v=OCS.15)
ms:contentKeyID: 49313122
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsLisConfiguration

 

_**上一次修改主题：** 2015-03-09_

测试位置信息服务器 (LIS) 配置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsLisConfiguration -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsLisConfiguration -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsLisConfiguration -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BssId <String>] [-ChassisId <String>] [-Force <SwitchParameter>] [-Mac <String>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-PortId <String>] [-PortIdSubType <InterfaceAlias | InterfaceName | LocallyAssigned>] [-Subnet <String>]

## 示例

## 示例 1

此示例在 FQDN atl-cs-001.litwareinc.com 上测试 LIS 配置。如果可以使用当前用户凭据与该 FQDN 上的 LIS Web 服务建立连接，则测试将成功。如果可以找到映射到子网 IP 地址 192.168.0.0 的位置，则将返回该位置地址。

要使此命令成功，必须存在包含综合事务用户的运行状况监控配置。要查看运行状况监控配置是否存在，请运行 **Get-CsHealthMonitoringConfiguration** cmdlet。要创建新的运行状况监控配置，请运行 **New-CsHealthMonitoringConfiguration** cmdlet。

    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0

## 示例 2

此示例与示例 1 相同，只是添加了 UserSipAddress 参数。在尚未设置任何综合事务用户，但从中运行此命令的计算机具有服务器证书时，使用此命令。

    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0 -UserSipAddress sip:kmyer@litwareinc.com

## 示例 3

此示例的第一行调用 Windows PowerShell cmdlet **Get-Credential** cmdlet，它会提示用户输入用户 ID 和密码。此信息以加密方式存储在变量 $cred 中。

第二行与示例 2 中的命令相同，只是添加了 UserSipAddress 参数。在尚未设置任何综合事务用户，并且从中运行此命令的计算机不具有服务器证书时，使用此命令。

    $cred = Get-Credential
    Test-CsLisConfiguration -TargetFqdn atl-cs-001.litwareinc.com -Subnet 192.168.0.0 -UserSipAddress sip:kmyer@litwareinc.com -UserCredential $cred

## 示例 4

此示例的第一行调用 **Get-Credential** cmdlet，它会提示用户输入用户 ID 和密码。此信息以加密方式存储在变量 $cred 中。

第 2 行通过调用基于远程用户的 SIP 地址 (sip:kmyer@litwareinc.com) 的 Web 服务 URI (https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc)，并使用在第 1 行中获取的凭据（通过将凭据传递给 WebCredential 参数）来测试 LIS 配置。如果可以使用给定的用户凭据与该 URI 上的 LIS Web 服务建立连接，则测试将成功。如果可以找到映射到子网 IP 地址 192.168.0.0、MAC 地址 0A-23-00-00-00-AA 或端口 ID 4500 和机架 ID 0A-23-00-00-00-AA 的位置，将会返回该位置地址。

在从中运行此命令的计算机不具有服务器证书时使用此命令。

    $cred = Get-Credential
    Test-CsLisConfiguration -TargetUri https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc -UserSipAddress sip:kmyer@litwareinc.com -WebCredential $cred -Subnet 192.168.0.0 -Mac 0A-23-00-00-00-AA -PortId 4500 -ChassisId 0A-23-00-00-00-AA

## 示例 5

此示例与示例 4 相同，但此命令不使用 WebCredential 参数（因此也不调用 **Get-Credential** cmdlet）。在运行此命令的计算机具有服务器证书时使用此命令。

    Test-CsLisConfiguration -TargetUri https://atl-cs-001.litwareinc.com/locationinformation/lisservice.svc -UserSipAddress sip:kmyer@litwareinc.com -Subnet 192.168.0.0 -Mac 0A-23-00-00-00-AA -PortId 4500 -ChassisId 0A-23-00-00-00-AA

## 详细说明

此 cmdlet 根据所提供参数中的信息确定是否可以联系位置信息服务器 (LIS) Web 服务。如果可以联系该 Web 服务，而且找到了与所提供的任一参数对应的位置，则测试将视为已通过并显示该位置。即使未找到该位置，如果可以联系该 Web 服务，测试仍将通过，但是不会返回任何位置信息。此外，如果您调用此 cmdlet 而不提供任何可选参数，只要可以联系该 Web 服务，测试仍将通过，但是不会返回任何位置信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsLisConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsConfiguration"}

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
<td><p>要针对其运行测试的服务器的完全限定域名 (FQDN)（格式为 server.litwareinc.com）。</p>
<p>除非您指定 TargetUri 参数（在此情况下无法指定 TargetFqdn），否则需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>位置信息服务的统一资源标识符 (URI)。可通过运行以下命令检索位置信息服务的 URI：Get-CsService –WebServer | Select-Object LIServiceInternalUri</p>
<p>如果为该参数指定了值，还必须指定 UserSipAddress 参数。如果运行此命令的计算机没有服务器证书，则您还必须为 WebCredential 参数指定值。</p>
<p>除非您指定了 TargetFqdn 参数，否则必须指定此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>必需</p></td>
<td><p>PSCredential</p></td>
<td><p>包含用于访问位置信息服务的用户凭据的对象。可通过调用 <strong>Get-Credential</strong> cmdlet 并提供相应的凭据来检索该对象。</p>
<p>如果指定 TargetFqdn 和 UserSipAddress 参数，并且从中运行 cmdlet 的计算机没有服务器证书，则需要此参数。</p></td>
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
<td><p><em>BssId</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>无线接入点的基本服务集标识符 (BSSID)。该值的格式必须为 nn-nn-nn-nn-nn-nn，例如 12-34-56-78-90-ab。</p></td>
</tr>
<tr class="even">
<td><p><em>ChassisId</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>网络交换机的媒体访问控制 (MAC) 地址。该值的格式必须为 nn-nn-nn-nn-nn-nn，例如 12-34-56-78-90-ab，或者是 IP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>External</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>位置信息服务器不支持此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Mac</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>端口交换机的 MAC 地址。该值的格式必须为 nn-nn-nn-nn-nn-nn，例如 12-34-56-78-90-ab。</p></td>
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
<td><p><em>PortId</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与要测试的位置关联的端口的 ID。该值还可包含 MAC 地址或 IP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>PortIdSubType</em></p></td>
<td><p>可选</p></td>
<td><p>PortIDSubType</p></td>
<td><p>端口的子类型。输入的值可以是数值或字符串，但必须是有效的子类型。有效的子类型包括：</p>
<p>1: InterfaceAlias</p>
<p>5: InterfaceName</p>
<p>7: LocallyAssigned</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>注册器服务的端口号。</p></td>
</tr>
<tr class="odd">
<td><p><em>Subnet</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>子网的 IP 地址。该值应以 IPv4 地址形式输入（数字由句点分隔，例如 192.0.2.0）。</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>远程用户的 SIP 地址。</p>
<p>如果为此参数指定值，则还需要 TargetFqdn 或 TargetUri 参数。</p>
<p>仅当尚未设置综合事务用户时，如果指定 TargetFqdn 参数，才需要此参数。要查看是否已设置综合事务用户，请运行 <strong>Get-CsHealthMonitoringConfiguration</strong> cmdlet。</p></td>
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

无。

## 返回类型

**Test-CsLisConfiguration** cmdlet 返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Debug-CsLisConfiguration](debug-cslisconfiguration.md)  
[Publish-CsLisConfiguration](publish-cslisconfiguration.md)  
[Unpublish-CsLisConfiguration](unpublish-cslisconfiguration.md)  
[Import-CsLisConfiguration](import-cslisconfiguration.md)  
[Export-CsLisConfiguration](export-cslisconfiguration.md)

