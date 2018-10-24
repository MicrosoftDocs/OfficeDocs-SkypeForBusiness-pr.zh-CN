---
title: Set-CsAnnouncement
TOCTitle: Set-CsAnnouncement
ms:assetid: 286cb990-844e-4b87-bdaf-4a75456d8c60
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425752(v=OCS.15)
ms:contentKeyID: 49312314
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAnnouncement

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values of an existing Lync Server announcement. Announcements are played when users dial a valid but unassigned phone number. An announcement can be a message (such as "This number is temporarily out of service") or a busy signal. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAnnouncement [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsAnnouncement [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AudioFilePrompt <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Language <String>] [-Name <String>] [-TargetUri <String>] [-TextToSpeechPrompt <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 assigns a new audio file to the Help Desk announcement. To perform this task, the command first uses the **Get-CsAnnouncement** cmdlet, without any parameters, to return a collection of all the announcements currently available. This collection is then piped to the **Where-Object** cmdlet, which picks the one announcement where the Name is equal to (-eq) "Help Desk Announcement". In turn, that announcement is then piped to the **Set-CsAnnouncement** cmdlet, which sets the value of the AudioFilePrompt property to helpdesk.wav.

Note that if this announcement already has a TextToSpeechPrompt value assigned to it, this command will generate a warning that the TextToSpeechPrompt value will be ignored.

    Get-CsAnnouncement | Where-Object {$_.Name -eq "Help Desk Announcement"} | Set-CsAnnouncement -AudioFilePrompt "helpdesk.wav"

## EXAMPLE 2

In Example 2, the TextToSpeechPrompt property for the announcement Help Desk Announcement is set to a null value; this effectively erases the property value. To do this, the command first uses the **Get-CsAnnouncement** cmdlet to return a collection of all the announcements currently available. This collection is then piped to the **Where-Object** cmdlet, which selects the announcement where the Name is equal to (-eq) "Help Desk Announcement". This announcement is then piped to the **Set-CsAnnouncement** cmdlet, which sets the TextToSpeechPrompt property to a null value ($Null).

    Get-CsAnnouncement | Where-Object {$_.Name -eq "Help Desk Announcement"} | Set-CsAnnouncement -TextToSpeechPrompt $Null

## EXAMPLE 3

This example updates the TargetUri for the Announcement with the name Help Desk Announcement. The command first uses the **Get-CsAnnouncement** cmdlet to return a collection of all the announcements currently available. This collection is then piped to the **Where-Object** cmdlet, which selects the announcement where the Name is equal to (-eq) "Help Desk Announcement". This announcement is then piped to the **Set-CsAnnouncement** cmdlet, which sets the TargetUri property to a voice mail location (sip:kmyer@litwareinc.com;opaque=app:voicemail).

    Get-CsAnnouncement | Where-Object {$_.Name -eq "Help Desk Announcement"} | Set-CsAnnouncement -TargetUri "sip:kmyer@litwareinc.com;opaque=app:voicemail"

## Detailed Description

An organization can own phone numbers that are not assigned to users or phones, but that are still valid numbers that can be called. By default when someone dials one of those numbers, that person will receive a busy signal and the call may result in an error returned to the SIP client. By applying announcement settings to unassigned numbers, administrators have the option of playing a message, returning a busy signal, or redirecting the call. This cmdlet modifies these announcement settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAnnouncement** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAnnouncement"}

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
<td><p><em>AudioFilePrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>The name of the audio file to be played for the announcement. Audio files are stored in the 文件存储. To save an audio file to the 文件存储, use the <strong>Import-CsAnnouncementFile</strong> cmdlet.</p>
<p>Valid file types: WAV and WMA</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>XdsIdentity</p></td>
<td><p>A unique identifier for the Announcement. This value will always be in the format &lt;serviceID&gt;/&lt;GUID&gt;, where serviceID is the Identity of the Application Server running the Announcement service and GUID is a globally unique identifier associated with these announcement settings. For example: ApplicationServer:redmond.litwareinc.com/bef5fa3b-3c97-4af0-abe7-611deee7616c.</p>
<p>Because GUIDs can be difficult to enter correctly at the command line, you’ll most likely retrieve announcements by using the <strong>Get-CsAnnouncement</strong> cmdlet and pipe them to the <strong>Set-CsAnnouncement</strong> cmdlet for modification. (For details, see the Examples section.)</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Announcement</p></td>
<td><p>A reference to the Announcement object you want to change. This object must be of type Microsoft.Rtc.Management.WritableConfig.Settings.AnnouncementServiceSettings.Announcement, which can be retrieved by calling the <strong>Get-CsAnnouncement</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Language</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>The language in which the TTS prompt will be played. If a value is entered for TextToSpeechPrompt this parameter is required.</p>
<p>Values are entered as a string representing the language and locale to be used. The following is a list of valid values, followed by the language and locale in parentheses: ca-ES (Catalan, Spain); da-DK (Danish, Denmark); de-DE (German, Germany); en-AU (English, Australia); en-CA (English, Canada); en-GB (English, United Kingdom); en-IN (English, India); en-US (English, United States); es-ES (Spanish, Spain); es-MX (Spanish, Mexico); fi-FI (Finnish, Finland); fr-CA (French, Canada); fr-FR (French, France); it-IT (Italian, Italy); ja-JP (Japanese, Japan); ko-KR (Korean, Korea); nb-NO (Norwegian, Bokmal, Norway); nl-NL (Dutch, Netherlands); pl-PL (Polish, Poland); pt-BR (Portuguese, Brazil); pt-PT (Portuguese, Portugal); ru-RU (Russian, Russia); sv-SE (Swedish, Sweden); zh-CN (Chinese, People’s Republic of China); zh-HK (Chinese, Hong Kong SAR); zh-TW (Chinese, Taiwan)</p></td>
</tr>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Enter a value for this parameter to change the name of the announcement. Names must be unique within a service.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>The URI to which the caller will be transferred after the announcement has been played. This value must be a SIP address entered in the format sip: followed by the SIP address. For example, sip:kmyer@litwareinc.com. Note that the SIP address can also be a telephone number or voice mail, for example sip:+14255551212@litwareinc.com;user=phone for a phone number or sip:kmyer@litwareinc.com;opaque=app:voicemail for voice mail.</p></td>
</tr>
<tr class="odd">
<td><p><em>TextToSpeechPrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>A text-to-speech (TTS) prompt. This is a string that will be converted to audio and played as the announcement.</p>
<p>If both AudioFilePrompt and TextToSpeechPrompt are specified for a single announcement, you will receive a warning that the audio file will take precedence and the TTS prompt will be ignored.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.AnnouncementServiceSettings.Announcement object. Accepts pipelined input of announcement objects.

## Return Types

The **Set-CsAnnouncement** cmdlet does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.AnnouncementServiceSettings.Announcement object.

## 另请参阅

#### 其他资源

[New-CsAnnouncement](new-csannouncement.md)  
[Remove-CsAnnouncement](remove-csannouncement.md)  
[Get-CsAnnouncement](get-csannouncement.md)  
[Import-CsAnnouncementFile](import-csannouncementfile.md)

