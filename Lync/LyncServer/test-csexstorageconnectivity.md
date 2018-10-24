---
title: Test-CsExStorageConnectivity
TOCTitle: Test-CsExStorageConnectivity
ms:assetid: 20fda110-5e09-4453-bb7b-a062abaab87f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204740(v=OCS.15)
ms:contentKeyID: 49312229
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsExStorageConnectivity

 

_**上一次修改主题：** 2015-03-09_

Verifies that the Lync Server Storage Service is working on a 前端服务器. This is done by creating a test email message in the specified Exchange mailbox and then optionally deleting that message at the end of the text. **Test-CsExStorageConnectivity** also verifies that Exchange archiving is working as expected. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsExStorageConnectivity -SipUri <String> [-Binding <String>] [-DeleteItem <SwitchParameter>] [-Folder <ConversationHistory | Inbox | Dumpster>] [-Force <SwitchParameter>] [-HostNameStorageService <String>] [-UseCache <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 tests to see if the Lync Server Storage Service can connect to the Exchange mailbox for the user sip:kenmyer@litwareinc.com. In this example, NetNamedPipe is used as the WCF binding.

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

## Example 2

Example 2 verifies that the Lync Server Storage Service can connect to the archiving store on Exchange 2013. (Note that this command will fail if the specified user has not been enabled for Exchange archiving.) In this example, a connection is made to the Dumpster folder: the Recoverable Items purge folder, a folder that stores deleted items and is not visible to end users.

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe" -Folder Dumpster

## Detailed Description

The **Test-CsExStorageConnectivity** cmdlet is used to verify that server-to-server authentication is working between Lync Server 2013 and Exchange 2013. To verify server-to-server authentication, the cmdlet logs on to Exchange 2013, writes an item to the Conversation History folder in the specified mailbox, and then deletes that item.

The **Test-CsExStorageConnectivity** cmdlet can also be used to verify that connections can be made to the archiving store on Exchange 2013.

If you receive an “Access Denied” error message when running this cmdlet that typically means that you are not a member of the local group RTC Local User Administrators. You can either be added to that group or to the Active Directory group RTCUniversalUserAdmins (which is a member of the RTC Local User Administrators) in order to get the required permissions to run the **Test-CsExStorageConnectivity** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsExStorageConnectivity"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsExStorageConnectivity** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>SIP address of the Exchange 2013 mailbox where the test item should be created.</p></td>
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
<td><p>When present, the test item will be deleted from the Exchange 2013 mailbox at the end of the text.</p></td>
</tr>
<tr class="even">
<td><p><em>Folder</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Lyss.Cmdlets.ExchFolder</p></td>
<td><p>Specifies the Exchange 2013 archiving folder that the cmdlet should connect to. Allowed values are:</p>
<p>* ConversationHistory</p>
<p>* Inbox</p>
<p>* Dumpster</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HostNameStorageService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the server where the Lync Server Storage Service is running. This parameter is required if the Binding is set to NetTCP.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseCache</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When presents, instructs the cmdlet to used cached auto discovery results when attempting to connect to Exchange.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The Test-CsExStorageConnectivity cmdlet does not accept pipelined input.

## Return Types

The **Test-CsExStorageConnectivity** cmdlet returns instances of the Microsoft.Rtc.Management.ResourceData object.

## 另请参阅

#### 其他资源

[Test-CsExStorageNotification](test-csexstoragenotification.md)

