---
title: Test-CsExStorageNotification
TOCTitle: Test-CsExStorageNotification
ms:assetid: d8fe3b22-7a76-4d70-9bc1-b54b37f68449
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205331(v=OCS.15)
ms:contentKeyID: 49314416
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsExStorageNotification

 

_**上一次修改主题：** 2015-03-09_

Verifies that the Lync Server Storage Service running on a Front End server can subscribe to the Microsoft Exchange Server 2013 mailbox notification service. This is done by having the cmdlet subscribe to the service, create an item, verify that notification of the new item is received, and then, optionally, delete that item unsubscribe from the service. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsExStorageNotification -SipUri <String> [-Binding <String>] [-DeleteItem <SwitchParameter>] [-Force <SwitchParameter>] [-HostNameStorageService <String>]

## Examples

## Example 1

The command shown in Example 1 tests to see if the Lync Server Storage Service can connect to the Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com. In this example, NetNamedPipe is used as the WCF binding.

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

## Detailed Description

The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service is able to notify Lync Server 2013 any time updates are made to a user's Contact List. This cmdlet is valid only if you are using the unified contact store.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsExStorageNotification"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsExStorageNotification** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>SipUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the Exchange Server mailbox where the test item should be created.</p></td>
</tr>
<tr class="even">
<td><p><em>Binding</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Windows Communication Foundation (WCF) binding. A WCF binding determines the transport, encoding, and protocol details required for clients and services to communicate with each other. valid values are:</p>
<p>* NetNamedPipe</p>
<p>* NetTCP</p></td>
</tr>
<tr class="odd">
<td><p><em>DeleteItem</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, the test item will be deleted from the Exchange mailbox at the end of the text.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>HostNameStorageService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the server where the Lync Server Storage Service is running. This parameter is required if the Binding is set to NetTCP.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsExStorageNotification** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsExStorageNotification** cmdlet returns instances of the Microsoft.Rtc.Management.ResourceData object.

## 另请参阅

#### 其他资源

[Test-CsExStorageConnectivity](test-csexstorageconnectivity.md)

