---
title: Set-CsAnalogDevice
TOCTitle: Set-CsAnalogDevice
ms:assetid: b05e729e-cdef-4c78-8ce7-b183c3208a93
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412843(v=OCS.15)
ms:contentKeyID: 49313939
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAnalogDevice

 

_**上一次修改主题：** 2015-03-09_

修改可使用 Lync Server 管理的模拟设备集合中的现有设备。模拟设备是指连接到公用电话交换网 (PSTN) 的电话或其他设备。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAnalogDevice -Identity <UserIdParameter> [-AnalogFax <$true | $false>] [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-Gateway <Fqdn>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 为 Identity 是 CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com 的模拟设备更改 LineUri 属性的值。

    Set-CsAnalogDevice -Identity "CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com" -LineUri "TEL:+14255551298"

## 示例 2

示例 2 中显示的命令更改当前正在使用网关 192.168.0.240 的每个模拟设备的网关。为执行此任务，调用带有 Filter 参数的 **Get-CsAnalogDevice** cmdlet；筛选器值 {Gateway -eq "192.168.0.240"} 可确保仅返回 Gateway 等于 (-eq) 192.168.0.240 的设备。然后，将筛选出的集合通过管道传递到 **Set-CsAnalogDevice** cmdlet，后者会选取集合中的每一项并将 Gateway 属性的值更改为 192.168.1.100。

    Get-CsAnalogDevice -Filter {Gateway -eq "192.168.0.240"} | Set-CsAnalogDevice -Gateway "192.168.1.100"

## 详细说明

模拟设备包括连接到公用电话交换网 (PSTN) 的电话、传真机、调制解调器和失聪人士专用电传/电信设备 (TTY/TTD) 设备。与利用企业语音（即 Microsoft 提供的 IP 语音 (VoIP) 解决方案）的设备不同，模拟设备不使用数字数据包传输信息，而是使用连续的信号传输信息。此信号通常称为模拟信号；因此产生了术语“模拟设备”。

为了使管理员能够管理模拟设备，您可以使用 Lync Server 将模拟设备与 Active Directory 联系对象关联。将设备与联系对象关联后，就可以通过向联系人分配策略和拨号计划来管理模拟设备。

**Set-CsAnalogDevice** cmdlet 提供了一种方法，用于修改与模拟设备关联的联系对象的属性。例如，可以更改联系人的 Active Directory 显示名称或与设备关联的线路统一资源标识符 (URI)。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsAnalogDevice** cmdlet：RTCUniversalUserAdmins。可以使用 **Grant-CsOUPermission** cmdlet 分配对特定站点或特定 Active Directory 组织单位 (OU) 运行此 cmdlet 的权限。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAnalogDevice"}

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
<td><p>UserIdParameter</p></td>
<td><p>要修改的模拟设备的唯一标识符。模拟设备是使用关联的联系对象的 Active Directory 可分辨名称 (DN) 进行标识的。默认情况下，模拟设备使用 GUID（全局唯一标识符）作为其公用名；这意味着设备通常会带有一个以下类似标识：CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com。因此您可能会发现使用 <strong>Get-CsAnalogDevice</strong> cmdlet 返回模拟设备对象，然后将这些对象通过管道传递到 <strong>Set-CsAnalogDevice</strong> cmdlet 来修改模拟设备会更容易一些。</p></td>
</tr>
<tr class="even">
<td><p><em>AnalogFax</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果模拟设备是传真机，则设置为 True ($True)。如果设备不是传真机，则设置为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>配置模拟设备的 Active Directory 显示名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>显示在 Lync 中的电话号码。您可以采用所喜欢的任意方式设置 DisplayNumber 属性的格式；例如 1-800-555-1234、1-(800)-555-1234、1.800.555.1234 等。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Fqdn</p></td>
<td><p>使您可以连接到指定的域控制器，以便修改联系人信息。要连接到特定的域控制器，请包含 DomainController 参数，后跟计算机名称（例如 atl-mcs-001）或其完全限定域名 (FQDN)（例如 atl-mcs-001.litwareinc.com）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True ($True) 时，模拟设备将可以用于 Lync。</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示模拟设备的联系对象是否已启用企业语音，即 Microsoft 提供的 VoIP 解决方案。通过企业语音，可以使用 Internet 而不是标准电话网络发出电话呼叫。</p></td>
</tr>
<tr class="odd">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>指定是否存档联系人的即时消息会话。允许的值是：</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* ArchivingToExchange</p>
<p>* NoArchiving</p></td>
</tr>
<tr class="even">
<td><p><em>Gateway</em></p></td>
<td><p>可选</p></td>
<td><p>Fqdn</p></td>
<td><p>模拟设备要使用的 PSTN 网关的 IP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>模拟设备的电话号码。应该使用 E.164 格式指定线路 URI，并加上“TEL:”前缀。例如：TEL:+14255551297。应将所有分机号添加到线路 URI 的末尾；例如：TEL:+14255551297;ext=51297。</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>返回代表公用区域电话的对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>使模拟设备可以与 SIP 设备（如 Lync 2013）通信的唯一标识符。SIP 地址必须以“sip:”作为前缀。例如：sip:bldg14lobby@litwareinc.com。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact 对象。**Set-CsAnalogDevice** cmdlet 接受通过管道传递的模拟设备对象的实例。

## 返回类型

默认情况下，**Set-CsAnalogDevice** cmdlet 不会返回任何对象或值。但是，如果包含 PassThru 参数，该 cmdlet 将返回 Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsAnalogDevice](get-csanalogdevice.md)  
[Move-CsAnalogDevice](move-csanalogdevice.md)  
[New-CsAnalogDevice](new-csanalogdevice.md)  
[Remove-CsAnalogDevice](remove-csanalogdevice.md)

