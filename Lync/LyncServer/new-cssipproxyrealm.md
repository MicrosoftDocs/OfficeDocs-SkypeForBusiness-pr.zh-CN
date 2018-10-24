---
title: New-CsSipProxyRealm
TOCTitle: New-CsSipProxyRealm
ms:assetid: fedf9c71-5a23-4818-9f98-db5008a2ba74
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413084(v=OCS.15)
ms:contentKeyID: 49314845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsSipProxyRealm

 

_**上一次修改主题：** 2015-03-09_

Used to assign the default realm (SIP Communications Service) to a collection of proxy configuration settings. Realms (also known as protection domains) are used to authenticate user credentials during logon. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsSipProxyRealm -RealmChoice <IRealmChoice>

## Examples

## EXAMPLE 1

The commands shown in Example 1 assign the default realm (SIP Communications Service) to a variable named $y. To do this, the first command calls the **New-CsSipProxyUseDefault** cmdlet in order to create a SipProxy.UseDefault object; this object is stored in a variable named $x.

In the second command, $x is used as the parameter value for the **New-CsSipProxyRealm** cmdlet and the RealmChoice parameter. In turn, this creates a new proxy realm object that is stored in a variable named $y.

    $x = New-CsSipProxyUseDefault
    $y = New-CsSipProxyRealm -RealmChoice $x

## EXAMPLE 2

The commands shown in Example 2 assign a custom realm (Litwareinc Communications Service) to a variable named $y. To do this, the first command calls the **New-CsSipProxyCustom** cmdlet in order to create a SipProxy.Custom object; this object (which uses the CustomValue Litwareinc Communications Service) is stored in a variable named $x.

In the second command, $x is used, along with the **New-CsSipProxyRealm** cmdlet and the RealmChoice parameter, to create a new custom realm object.

    $x = New-CsSipProxyCustom -CustomValue "Litwareinc Communications Service"
    $y = New-CsSipProxyRealm -RealmChoice $x

## Detailed Description

Proxy servers provide a way for users outside your internal network to access resources on your internal network. Each proxy server must be associated with a realm; realms (also known as protection domains) indicate where a user’s logon credentials should be processed. By default, Lync Server uses SIP Communications Service as its default realm; however, it is possible to change the realm used by a proxy server. The **New-CsSipProxyUseDefault** cmdlet and the **New-CsSipProxyCustom** cmdlet provide a way for you to change the realm used by a proxy server. These changes can also be made by using the **New-CsSipProxyRealm** cmdlet. However, because this cmdlet requires an additional step you might want to use the other two cmdlets any time you need to change the realm used by a proxy server.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSipProxyRealm** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSipProxyRealm"}

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
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>RealmChoice</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.IRealmChoice</p></td>
<td><p>Object representing the realm to be used by a proxy server. The RealmChoice must be created by using either the <strong>New-CsSipProxyUseDefault</strong> or the <strong>New-CsSipProxyCustom</strong> cmdlet.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsSipProxyRealm** cmdlet does not accept pipelined input.

## Return Types

The **New-CsSipProxyRealm** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.Realm object.

## 另请参阅

#### 其他资源

[New-CsSipProxyCustom](new-cssipproxycustom.md)  
[New-CsSipProxyUseDefault](new-cssipproxyusedefault.md)

