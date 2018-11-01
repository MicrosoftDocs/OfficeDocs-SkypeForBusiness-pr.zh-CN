---
title: New-CsAnnouncement
TOCTitle: New-CsAnnouncement
ms:assetid: 6e3699c6-cd2b-4842-99bc-3cf2578fbd65
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398522(v=OCS.15)
ms:contentKeyID: 49313177
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAnnouncement

 

_**上一次修改主题：** 2015-03-09_

Creates a new Lync Server announcement. Announcements are played when users dial a valid but unassigned phone number. An announcement can be a message (such as "This number is temporarily out of service") or a busy signal. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAnnouncement -Parent <String> <COMMON PARAMETERS>

    New-CsAnnouncement -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Name <String> [-AudioFilePrompt <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Language <String>] [-TargetUri <String>] [-TextToSpeechPrompt <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 demonstrates how you can create a new announcement that will play a TTS prompt in U.S. English. The first parameter we specify is Identity. The Identity must be at the service scope, followed by the service ID of the Application Server (ApplicationServer:redmond.litwareinc.com). Next we give the announcement a Name, in this case Help Desk Announcement. To assign a TTS prompt to this announcement we use the TextToSpeechPrompt parameter followed by a string with the announcement text. When a TTS prompt is used for an announcement you must specify a language, which we do here by including the Language parameter followed by a string representing U.S. English (en-US).

Note that announcement identities are composed of two parts: the service where the announcement is to be stored, and a 36-character GUID (globally unique identifier). You will see the full Identity after you create the new announcement, the GUID is generated and applied automatically. That Identity will be similar to this: service:ApplicationServer:redmond.litwareinc.com/1951f734-c80f-4fb2-965d-51807c792b90.

    New-CsAnnouncement -Identity ApplicationServer:redmond.litwareinc.com -Name "Help Desk Announcement" -TextToSpeechPrompt "Welcome to the Help Desk." -Language "en-US"

## EXAMPLE 2

Example 2 is similar to Example 1 in that we begin by entering the required parameters, Identity and Name. In this example, however, instead of a TTS prompt, we want the announcement to play an audio file. To do that we include the AudioFilePrompt parameter and pass it a string containing the name of the audio file (WelcomeMessage.wav). This file must be in the 文件存储 in order for this announcement to play. You can add audio files to the 文件存储 by calling the **Import-CsAnnouncementFile** cmdlet.

    New-CsAnnouncement -Identity ApplicationServer:redmond.litwareinc.com -Name "Welcome Announcement" -AudioFilePrompt "WelcomeMessage.wav"

## EXAMPLE 3

Like Example 2, this example creates an announcement that plays an audio file when the number is reached. However, in this example in addition to the Identity, Name, and AudioFilePrompt parameters, we also specify the TargetUri parameter. We pass this parameter the SIP URI of the user or phone to which the caller will be forwarded after the announcement has been played.

    New-CsAnnouncement -Identity ApplicationServer:redmond.litwareinc.com -Name "Forward Announcement" -AudioFilePrompt "WelcomeMessage.wav" -TargetUri sip:kmyer@litwareinc.com

## EXAMPLE 4

Example 4 is identical to Example 3 except that instead of forwarding the call based on a user’s SIP address, the call is forwarded to a phone number.

    New-CsAnnouncement -Identity ApplicationServer:redmond.litwareinc.com -Name "Forward Announcement" -AudioFilePrompt "WelcomeMessage.wav" -TargetUri "sip:+14255551212@litwareinc.com;user=phone"

## EXAMPLE 5

In this example we don’t specify a prompt or a target URI, we include only an Identity and a Name. That means the caller will hear a busy signal when a call to an unassigned number associated with this announcement is connected.

    New-CsAnnouncement -Identity ApplicationServer:redmond.litwareinc.com -Name "Busy"

## Detailed Description

An organization can own phone numbers that are not assigned to users or phones, but that are still valid numbers that can be called. By default when someone dials one of those numbers, that person will receive a busy signal and the call may result in an error returned to the SIP client. By applying announcement settings to unassigned numbers, administrators have the option of playing a message, returning a busy signal, or redirecting the call. This cmdlet creates these announcement settings.

You can assign announcements to unassigned numbers by calling the **New-CsUnassignedNumber** or the **Set-CsUnassignedNumber** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAnnouncement** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAnnouncement"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>A unique identifier for the Announcement. For this value you must enter the Identity of the Application Server running the Response Group application. For example, ApplicationServer:redmond.litwareinc.com.</p>
<p>More than one Announcement can be assigned to a single service. Thus, in order to make the Identity a unique value, a globally unique identifier (GUID) will be automatically generated and assigned to the Identity when you create the Announcement. The new Announcement will have an Identity in the format service:&lt;service ID&gt;/&lt;GUID&gt;. For example: service: ApplicationServer:redmond.litwareinc.com/bef5fa3b-3c97-4af0-abe7-611deee7616c. You do not need to supply a GUID when you call this cmdlet. Instead, supply the service Identity, and the GUID will be auto-generated and added to the Identity.</p>
<p>Although you don’t have to supply a GUID, you can. You might want to do this if an announcement was assigned to an unassigned number range, and then the announcement was deleted. You can create a new announcement with a matching Identity (including the GUID) and in that case not have to update the unassigned number range.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>A descriptive name for the Announcement. This name must be unique within the service. This name will be used in the call to the <strong>New-CsUnassignedNumber</strong> cmdlet or to the <strong>Set-CsUnassignedNumber</strong> cmdlet to specify the Announcement associated with an unassigned number range.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is identical to Identity, except that Identity will accept the service Identity and the GUID, whereas Parent will accept only the service Identity; the GUID will be automatically generated. You cannot specify an Identity and a Parent.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioFilePrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the audio file to be played for the announcement. Audio files are stored in the 文件存储. To save an audio file to the 文件存储, use the <strong>Import-CsAnnouncementFile</strong> cmdlet.</p>
<p>Valid file types: WAV and WMA</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>Language</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The language in which the text-to-speech (TTS) prompt will be played. If a value is entered for TextToSpeechPrompt, this parameter is required.</p>
<p>Values are entered as a string representing the language and locale to be used. The following is a list of valid values, followed by the language and locale in parentheses: ca-ES (Catalan, Spain); da-DK (Danish, Denmark); de-DE (German, Germany); en-AU (English, Australia); en-CA (English, Canada); en-GB (English, United Kingdom); en-IN (English, India); en-US (English, United States); es-ES (Spanish, Spain); es-MX (Spanish, Mexico); fi-FI (Finnish, Finland); fr-CA (French, Canada); fr-FR (French, France); it-IT (Italian, Italy); ja-JP (Japanese, Japan); ko-KR (Korean, Korea); nb-NO (Norwegian, Bokmal, Norway); nl-NL (Dutch, Netherlands); pl-PL (Polish, Poland); pt-BR (Portuguese, Brazil); pt-PT (Portuguese, Portugal); ru-RU (Russian, Russia); sv-SE (Swedish, Sweden); zh-CN (Chinese, People’s Republic of China); zh-HK (Chinese, Hong Kong SAR); zh-TW (Chinese, Taiwan)</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The Uniform Resource Identifier (URI) to which the caller will be transferred after the announcement has been played. This value must be a SIP address entered in the format sip: followed by the SIP address. For example, sip:kmyer@litwareinc.com. Note that the SIP address can also be a telephone number or voice mail, for example sip:+14255551212@litwareinc.com;user=phone for a phone number or sip:kmyer@litwareinc.com;opaque=app:voicemail for voice mail.</p></td>
</tr>
<tr class="even">
<td><p><em>TextToSpeechPrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A text-to-speech (TTS) prompt. This is a string that will be converted to audio and played as the announcement.</p>
<p>If both AudioFilePrompt and TextToSpeechPrompt are specified for a single announcement, you will receive a warning that the audio file will take precedence and the TTS prompt will be ignored.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.AnnouncementServiceSettings.Announcement.

## 另请参阅

#### 其他资源

[Remove-CsAnnouncement](remove-csannouncement.md)  
[Set-CsAnnouncement](set-csannouncement.md)  
[Get-CsAnnouncement](get-csannouncement.md)  
[Import-CsAnnouncementFile](import-csannouncementfile.md)  
[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Set-CsUnassignedNumber](set-csunassignednumber.md)

