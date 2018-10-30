---
title: Set-CsRgsConfiguration
TOCTitle: Set-CsRgsConfiguration
ms:assetid: 259cec4c-0152-4c8f-8aa6-51cefc1b55c9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425728(v=OCS.15)
ms:contentKeyID: 49312274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRgsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies configuration settings for the 响应组应用程序. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRgsConfiguration -Identity <RgsIdentity> [-AgentRingbackGracePeriod <Int16>] [-DefaultMusicOnHoldFile <AudioFile>] [-DisableCallContext <$true | $false>] <COMMON PARAMETERS>

    Set-CsRgsConfiguration -Instance <ServiceSettings> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the AgentRingbackGracePeriod property for the 响应组应用程序 configuration settings found on the service ApplicationServer:atl-cs-001.litwareinc.com. In this example, AgentRingbackGracePeriod is set to 30 seconds.

    Set-CsRgsConfiguration -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -AgentRingbackGracePeriod 30

## EXAMPLE 2

Example 2 modifies the AgentRingbackGracePeriod for all the Response Group configuration settings in the organization. To do this, the command first uses the **Get-CsService** cmdlet and the ApplicationServer parameter to return information about all the computers in the organization that are running the 应用程序服务. The returned collection is then piped to the **Where-Object** cmdlet, which picks out only those computers where the Applications property contains the application "urn:application:RGS"; that value indicates that the 响应组应用程序 is running on the server.

In turn, those computers are piped to the **ForEach-Object** cmdlet. **ForEach-Object** then takes each computer in the collection and uses the **Set-CsRgsConfiguration** to set the value of the AgentRingbackGracePeriod of the computer’s Response Group configuration settings r to 30 seconds.

    Get-CsService -ApplicationServer | Where-Object {$_.Applications -contains "urn:application:RGS"} | ForEach-Object {Set-CsRgsConfiguration -Identity $_.Identity -AgentRingbackGracePeriod 30}

## EXAMPLE 3

The commands shown in Example 3 import an audio file (C:\\Media\\WhileYouWait.wav) and then assign that file to the DefaultMusicOnHoldFile property. To perform this task, the first command uses **Import-CsRgsAudioFile** to import the audio file to the 响应组应用程序 found on ApplicationServer:atl-cs-001.litwareinc.com. In addition to the Identity parameter (which specifies the service location), the FileName parameter is used to specify the file name of the file being imported.

Equally important, the Content parameter is used to import the audio file. File importing is carried out by calling the **Get-Content** cmdlet followed by the path to the file being imported. **Get-Content** also requires you to set the encoding type to byte and the ReadCount to 0. (Setting the ReadCount to 0 ensures that the entire file is read in in a single operation.) The imported file is then stored in a variable named $x.

After the file has been imported, **Set-CsRgsConfiguration** is called in order to set the DefaultMusicOnHoldFile property to the audio file stored in $x.

    $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -FileName "WhileYouWait.wav" -Content (Get-Content C:\Media\WhileYouWait.wav -Encoding byte -ReadCount 0)
    
    Set-CsRgsConfiguration -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -DefaultMusicOnHoldFile $x

## Detailed Description

The 响应组应用程序 provides a way for you to automatically route phone calls to entities such as a help desk or customer support line. When someone calls a designated phone number, that call can be automatically routed to the appropriate set of Response Group agents. Alternatively, the call might be routed to an interactive voice response (IVR) queue. In that queue, the caller would be asked a series of questions (for example, "Are you calling about an existing order?") and then, based on the answers to those questions, be given the asked-for information or be routed to a Response Group agent.

The **Set-CsRgsConfiguration** cmdlet provides a way for you to modify the properties of a 响应组应用程序 instance.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsRgsConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRgsConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Name of the service hosting the Response Group configuration settings. For example: -Identity &quot;service:ApplicationServer:atl-cs-001.litwareinc.com.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.ServiceSettings</p></td>
<td><p>Object reference to the Response Group configuration settings to be modified. An object reference is typically retrieved by using the <strong>Get-CsRgsConfiguration</strong> cmdlet and assigning the returned value to a variable; for example, this command returns an object reference to the configuration settings found on the service ApplicationServer:atl-cs-001.litwareinc.com and stores that object reference in a variable named $x:</p>
<p>$x = Get-CsRgsConfiguration -Identity service:ApplicationServer:atl-cs-001.litwareinc.com</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>AgentRingbackGracePeriod</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int16</p></td>
<td><p>If an agent declines a call, the AgentRingbackGracePeriod represents the amount of time (in seconds) that can elapse before the call returns to the same agent. The grace period can be set to any integer value between 30 and 600 seconds (10 minutes), inclusive. The default value is 60 seconds.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultMusicOnHoldFile</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile</p></td>
<td><p>Represents the music that, by default, will be played any time a caller is placed on hold. The default music will play only if a Response Group workflow has not defined its own music on hold.</p>
<p>The DefaultMusicOnHoldFile property must be configured using an object reference created by using the <strong>Import-CsRgsAudioFile</strong> cmdlet.</p>
<p>If DefaultMusicOnHold is equal to a null value (the default value) and if a workflow has not defined custom music on hold, then the default music on hold that is automatically configured when you install Lync Server will be played any time a caller is placed on hold.</p></td>
</tr>
<tr class="even">
<td><p><em>DisableCallContext</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to False (the default value), each agent is able to see the call context (information such as caller wait time or workflow questions and answers) whenever a call received. (This information is visible from within Lync.) If set to True, call context information is not relayed to agents when a call is received.</p>
<p>Note that the call context is only used with IVR queues.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Rgs.Management.WritableSettings.ServiceSettings object. **Set-CsRgsConfiguration** accepts pipelined instances of the 响应组应用程序 settings object.

## Return Types

**Set-CsRgsConfiguration** does not return any objects or values. Instead, the cmdlet configures existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.ServiceSettings object.

## 另请参阅

#### 其他资源

[Get-CsRgsConfiguration](get-csrgsconfiguration.md)  
[Move-CsRgsConfiguration](move-csrgsconfiguration.md)

