---
title: New-CsConferencingPolicy
TOCTitle: New-CsConferencingPolicy
ms:assetid: f343bfcc-f296-4935-aa4c-94658dacace7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413019(v=OCS.15)
ms:contentKeyID: 49314727
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsConferencingPolicy

 

_**上一次修改主题：** 2016-12-08_

Creates a new conferencing policy for use in your organization. Conferencing policies determine the features and capabilities that can be used in a conference; this includes everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsConferencingPolicy -Identity <XdsIdentity> [-AllowAnnotations <$true | $false>] [-AllowAnonymousParticipantsInMeetings <$true | $false>] [-AllowAnonymousUsersToDialOut <$true | $false>] [-AllowConferenceRecording <$true | $false>] [-AllowExternalUserControl <$true | $false>] [-AllowExternalUsersToRecordMeeting <$true | $false>] [-AllowExternalUsersToSaveContent <$true | $false>] [-AllowIPAudio <$true | $false>] [-AllowIPVideo <$true | $false>] [-AllowLargeMeetings <$true | $false>] [-AllowMultiView <$true | $false>] [-AllowNonEnterpriseVoiceUsersToDialOut <$true | $false>] [-AllowOfficeContent <$true | $false>] [-AllowParticipantControl <$true | $false>] [-AllowPolls <$true | $false>] [-AllowQandA <$true | $false>] [-AllowSharedNotes <$true | $false>] [-AllowUserToScheduleMeetingsWithAppSharing <$true | $false>] [-AppSharingBitRateKb <Int64>] [-AudioBitRateKb <UInt32>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-DisablePowerPointAnnotations <$true | $false>] [-EnableAppDesktopSharing <None | SingleApplication | Desktop>] [-EnableDataCollaboration <$true | $false>] [-EnableDialInConferencing <$true | $false>] [-EnableFileTransfer <$true | $false>] [-EnableMultiViewJoin <$true | $false>] [-EnableOnlineMeetingPromptForLyncResources <$true | $false>] [-EnableP2PFileTransfer <$true | $false>] [-EnableP2PRecording <$true | $false>] [-EnableP2PVideo <$true | $false>] [-FileTransferBitRateKb <Int64>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaxMeetingSize <UInt32>] [-MaxVideoConferenceResolution <CIF | VGA>] [-TotalReceiveVideoBitRateKb <Int64>] [-VideoBitRateKb <Int64>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 uses the **New-CsConferencingPolicy** cmdlet to create a new conferencing policy with the Identity SalesConferencingPolicy. This policy will use all the default values for a conferencing policy except one: MaxMeetingSize; in this example, the maximum size for a meeting will be set to 50 instead of the default value of 250.

    New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50

## EXAMPLE 2

In Example 2, the **New-CsConferencingPolicy** cmdlet is used to create a conferencing policy with the Identity site:Redmond. In this example two different property values are configured: MaxMeetingSize is set to 100 and AllowParticipantControl is set to False. All other policy properties will use the default values.

    New-CsConferencingPolicy -Identity site:Redmond -MaxMeetingSize 100 -AllowParticipantControl $False

## Detailed Description

Conferencing is an important part of Lync Server: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.

It’s important for administrators to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In other cases, there might be bandwidth concerns: having a multitude of simultaneous meetings, each involving hundreds of participants and each featuring video feeds and file sharing, has the potential to cause problems with your network. In addition, there might be occasional legal concerns. For example, by default meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.

Needing to manage conferencing settings is one thing; actually managing these settings is another. In Lync Server, conferences are managed by using conferencing policies. (In previous versions of the software, these were known as meeting policies.) As noted, conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope; at the site scope; or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.

The **New-CsConferencingPolicy** cmdlet enables you to create new conferencing policies at either the site or the per-user scope. You cannot create a new global policy because the global policy already exists. However, you can modify the property values of the global policy by using the **Set-CsConferencingPolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsConferencingPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsConferencingPolicy"}

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
<td><p>Unique identifier for the conferencing policy to be created. Conferencing policies can be created at the site or per-user scopes. To create a site policy, use syntax similar to this: -Identity site:Redmond. To create a per-user policy, use syntax similar to this: -Identity SalesConferencingPolicy.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowAnnotations</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not participants are allowed to make on-screen annotations on any content shared during the meeting; in addition, this setting determines whether or not whiteboarding is allowed in the conference. The default value is True.</p>
<p>Note that annotations are not archived along with other meeting content.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will include annotations. However, the user can participate in other conferences where annotations are allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowAnonymousParticipantsInMeetings</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether anonymous users are allowed to participate in the meeting. If set to False then only authenticated users (that is, users logged on to your Active Directory 域服务 or the Active Directory of a federated partner) are allowed to attend the meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow anonymous participants. However, the user can take part in other conferences where anonymous participants are allowed.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>AllowAnonymousUsersToDialOut</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not anonymous users (unauthenticated users) are allowed to use dial-out phoning when they join a conference. With dial-out phoning, the conferencing server telephones the user; when the user answers the phone, he or she will be joined to the conference.</p>
<p>Note that dial-in conferencing is allowed even if this setting is False.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow anonymous participants to join the conference via dial-out phoning. However, the user can take part in other conferences where anonymous users can join via dial out.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowConferenceRecording</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users are allowed to record the meeting. The default value is False.</p>
<p>This setting applies to all users taking part in the conference.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowExternalUserControl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether external users (either anonymous users or federated users) are allowed to take control of shared applications or desktops. The default value is False.</p>
<p>This setting is enforced at the per-user level, and for both conferences and peer-to-peer communication sessions. That means that some users in a session might be allowed to give up control of a shared application or desktop to an external user while other users might not be allowed to give up control.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>AllowExternalUsersToRecordMeeting</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether external users (either anonymous users or federated users) are allowed to record the meeting. The default value is False.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow external users to record conferences. However, the user can take part in other conferences where external users are allowed to record meetings.</p>
<p>Note that this setting takes effect only if the AllowConferenceRecording property is set to True.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowExternalUsersToSaveContent</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether external users (that is, users not currently logged-on to your network) are allowed to save handouts, slides, and other meeting content. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow external users to save content. However, the user can take part in other conferences where external users are allowed to save content.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>AllowIPAudio</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not computer audio is allowed in the meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow IP audio. However, the user can take part in other conferences where IP audio is allowed.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowIPVideo</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not computer video is allowed in the meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow IP video. However, the user can take part in other conferences where IP video is allowed.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>AllowLargeMeetings</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, all online meetings are treated as &quot;large meeting.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants as well as the size of the meeting roster that is transmitted by default.</p>
<p>The default value is False ($False).</p></td>
</tr>
<tr class="even">
<td><p><em>AllowMultiView</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) enables users to schedule conferences that allow multiview; that is, clients can receive multiple video streams during a given conference. This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy can include multiview. However, the user can participate in other conferences where multiview is allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowNonEnterpriseVoiceUsersToDialOut</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or users who have not been enabled for Enterprise Voice are allowed to join a conference using dial-out phoning. With dial-out phoning the conferencing server will telephone the user; when the user answers the phone, he or she will be joined to the conference.</p>
<p>Note that dial-in conferencing is allowed even when this setting is False.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow users who have not been enabled for Enterprise Voice to join the conference via dial-out phoning. However, the user can take part in other conferences where users who have not been enabled for Enterprise Voice can join via dial out.</p>
<p>The default value is False ($False).</p></td>
</tr>
<tr class="even">
<td><p><em>AllowOfficeContent</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to False, prevents users from using Office content in their conferences.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowParticipantControl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not meeting participants are allowed to take control of applications or desktops shared during the meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow participant control. However, the user can take part in other conferences where participant control is allowed.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>AllowPolls</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not users are allowed to conduct online polls during a meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow polls. However, the user can take part in other conferences where polls are allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowQandA</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) the user will be able to include the Questions and Answers Manager in any online conference that he or she organizes. When set to False, the user will be prohibited from including Questions and Answers Manager in any of his or her conferences.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow the use of the Questions and Answers Manager. However, the user can make use of the Questions and Answers Manager in other conferences where polls are allowed.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowSharedNotes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowUserToScheduleMeetingsWithAppSharing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not users are allowed to organize meetings that include application sharing. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow application sharing. However, the user can take part in other conferences where application sharing is allowed.</p></td>
</tr>
<tr class="even">
<td><p><em>AppSharingBitRateKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Bit rate (in kilobits) used for application sharing. The default value is 50000.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioBitRateKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Bit rate (in kilobits) used for audio transmissions. The audio bit rate can be any whole number between 20 and 200, inclusive; the default value is 200.</p>
<p>This setting is enforced at the per-user level, and for both conferences and peer-to-peer communication sessions.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provider explanatory text about the conferencing policy. For example, the Description might indicate the users the policy should be assigned to.</p></td>
</tr>
<tr class="even">
<td><p><em>DisablePowerPointAnnotations</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True) users will not be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableAppDesktopSharing</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Meeting.EnableAppDesktopSharing</p></td>
<td><p>Indicates whether participants are allowed to share applications (or their desktop) during the course of a meeting. Allowed values are:</p>
<p>Desktop. Users are allowed to share their entire desktop.</p>
<p>SingleApplication. Users are allowed to share a single application.</p>
<p>None. Users are not allowed to share applications or their desktop.</p>
<p>This setting is enforced at the per-user level. That means that some users in a conference might be allowed to share their desktop or applications while other users in the same conference might not be allowed to do so.</p>
<p>The default value is Desktop.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDataCollaboration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users can organize meetings that include data collaboration activities such as whiteboarding and annotations.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow data collaboration. However, the user can take part in other conferences where data collaboration is allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableDialInConferencing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users are able to join the meeting by dialing in with a public switched telephone network (PSTN) telephone. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow dial-in conferencing. However, the user can take part in other conferences where dial-in conferencing is allowed.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableFileTransfer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether file transfers to all the meeting participants are allowed during the meeting. The default value is True.</p>
<p>This setting applies to the user who organizes the conference: if set to False, no conference created by a user affected by this policy will allow file transfers. However, the user can take part in other conferences where file transfers are allowed.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMultiViewJoin</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) clients will attempt to join a conference using multiview (which allows the client to receive multiple video streams during the conference). This parameter will be ignored if multiview is not allowed in the conference being joined. This setting is enforced at the per-user level, and for both conferences and peer-to-peer communication sessions. That means that some users in a session might be allowed to have multiple video streams while other users in the same conference might not.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableOnlineMeetingPromptForLyncResources</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users will be prompted any time they schedule a meeting in Outlook that includes invitees (such as a meeting room) that would benefit from having the meeting held online. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableP2PFileTransfer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether peer-to-peer file transfers (that is, file transfers that do not involve all participants) are allowed during the meeting. The default value is True.</p>
<p>This setting is enforced at the per-user level. That means that one user in a peer-to-peer communication session might be allowed to transfer files while the other user is not.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableP2PRecording</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, users will be able to record peer-to-peer conferencing sessions. The default value is False.</p>
<p>This setting is enforced at the per-user level. That means that one user in a peer-to-peer communication session might be allowed to record the session while the other user is not.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableP2PVideo</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, users will be able to take part in peer-to-peer video conferencing sessions. The default value is False.</p>
<p>This setting is enforced at the per-user level. That means that one user in a peer-to-peer communication session might be allowed to use video the session while the other user is not.</p></td>
</tr>
<tr class="even">
<td><p><em>FileTransferBitRateKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Bit rate (in kilobits) used for file transfers. The default value is 50000.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxMeetingSize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum number of people who are allowed to attend a meeting. After the maximum number of participants has been reached, anyone else who tries to join the meeting will be turned away with the notice that the meeting is full. The number of participants specified in this value can be any 32-bit whole number (any value between 1 and 4,294,967,295), but the recommended size is between 2 and 250, inclusive; the default value is 250.</p>
<div>

> [!NOTE]  
> 250 is the maximum for shared pool deployments, based on Microsoft testing. For information about supporting meeting with more than 250 participants, see &quot;Microsoft Lync Server 2010 Support for Large Meetings&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=242073">https://go.microsoft.com/fwlink/p/?linkId=242073</a>.

</div>
<p>This setting applies to the user who organizes the conference: no conference created by a user affected by this policy will allow more than the specified number of participants. However, the user can take part in other conferences where additional participants are allowed.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxVideoConferenceResolution</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Meeting.MaxVideoConferenceResolution</p></td>
<td><p>Indicates the maximum resolution for meeting video. Allowed values are:</p>
<p>CIF. Common Intermediate Format (CIF) has a resolution of 352 pixels by 288 pixels.</p>
<p>VGA. VGA has a resolution of 640 pixels by 480 pixels.</p>
<p>The default value is VGA.</p></td>
</tr>
<tr class="odd">
<td><p><em>TotalReceiveVideoBitRateKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Indicates the maximum allowed bitrate (in kilobytes per second) for all the video used in a conference; that is, the combined total for all the video streams. The default value is 50000 kilobytes per second.</p></td>
</tr>
<tr class="even">
<td><p><em>VideoBitRateKb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Bit rate (in kilobits) used for video transmissions. The default value is 50000.</p>
<p>This setting is enforced at the per-user level, and for both conferences and peer-to-peer communication sessions.</p></td>
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

None. The **New-CsConferencingPolicy** cmdlet does not accept pipelined input.

## Return Types

The **New-CsConferencingPolicy** cmdlet creates a new instance of the Microsoft.Rtc.Management.WritableConfig.Policy.Meeting.MeetingPolicy object.

## 另请参阅

#### 其他资源

[Get-CsConferencingPolicy](get-csconferencingpolicy.md)  
[Grant-CsConferencingPolicy](grant-csconferencingpolicy.md)  
[Remove-CsConferencingPolicy](remove-csconferencingpolicy.md)  
[Set-CsConferencingPolicy](set-csconferencingpolicy.md)

