---
title: Set-CsClientPolicy
TOCTitle: Set-CsClientPolicy
ms:assetid: 4b7eac0c-50e9-443a-b474-5c4e0c286028
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398300(v=OCS.15)
ms:contentKeyID: 49312767
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientPolicy

 

_**上一次修改主题：** 2016-04-11_

Modifies the property values of an existing client policy. Among other things, client policies help determine the features of Lync Server that are available to users; for example, you might give some users the right to transfer files while denying this right to other users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsClientPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClientPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AddressBookAvailability <WebSearchAndFileDownload | WebSearchOnly | FileDownloadOnly>] [-AttendantSafeTransfer <$true | $false>] [-AutoDiscoveryRetryInterval <TimeSpan>] [-BlockConversationFromFederatedContacts <$true | $false>] [-CalendarStatePublicationInterval <UInt32>] [-ConferenceIMIdleTimeout <TimeSpan>] [-Confirm [<SwitchParameter>]] [-CustomizedHelpUrl <String>] [-CustomLinkInErrorMessages <String>] [-CustomStateUrl <String>] [-Description <String>] [-DGRefreshInterval <TimeSpan>] [-DisableCalendarPresence <$true | $false>] [-DisableContactCardOrganizationTab <$true | $false>] [-DisableEmailComparisonCheck <$true | $false>] [-DisableEmoticons <$true | $false>] [-DisableFederatedPromptDisplayName <$true | $false>] [-DisableFeedsTab <$true | $false>] [-DisableFreeBusyInfo <$true | $false>] [-DisableHandsetOnLockedMachine <$true | $false>] [-DisableHtmlIm <$true | $false>] [-DisableInkIM <$true | $false>] [-DisableMeetingSubjectAndLocation <$true | $false>] [-DisableOneNote12Integration <$true | $false>] [-DisableOnlineContextualSearch <$true | $false>] [-DisablePhonePresence <$true | $false>] [-DisablePICPromptDisplayName <$true | $false>] [-DisablePoorDeviceWarnings <$true | $false>] [-DisablePoorNetworkWarnings <$true | $false>] [-DisablePresenceNote <$true | $false>] [-DisableRTFIM <$true | $false>] [-DisableSavingIM <$true | $false>] [-DisplayPhoto <NoPhoto | PhotosFromADOnly | AllPhotos>] [-EnableAppearOffline <$true | $false>] [-EnableCallLogAutoArchiving <$true | $false>] [-EnableClientMusicOnHold <$true | $false>] [-EnableConversationWindowTabs <$true | $false>] [-EnableEnterpriseCustomizedHelp <$true | $false>] [-EnableEventLogging <$true | $false>] [-EnableExchangeContactSync <$true | $false>] [-EnableExchangeDelegateSync <$true | $false>] [-EnableFullScreenVideo <$true | $false>] [-EnableHighPerformanceConferencingAppSharing <$true | $false>] [-EnableHighPerformanceP2PAppSharing <$true | $false>] [-EnableHotdesking <$true | $false>] [-EnableIMAutoArchiving <$true | $false>] [-EnableMediaRedirection <$true | $false>] [-EnableNotificationForNewSubscribers <$true | $false>] [-EnableSQMData <$true | $false>] [-EnableTracing <$true | $false>] [-EnableUnencryptedFileTransfer <$true | $false>] [-EnableURL <$true | $false>] [-EnableVOIPCallDefault <$true | $false>] [-ExcludedContactFolders <String>] [-Force <SwitchParameter>] [-HelpEnvironment <String>] [-HotdeskingTimeout <TimeSpan>] [-IMWarning <String>] [-MAPIPollInterval <TimeSpan>] [-MaximumDGsAllowedInContactList <UInt32>] [-MaximumNumberOfContacts <UInt16>] [-MaxPhotoSizeKB <UInt32>] [-MusicOnHoldAudioFile <String>] [-P2PAppSharingEncryption <Supported | Enforced | NotSupported>] [-PlayAbbreviatedDialTone <$true | $false>] [-PolicyEntry <PSListModifier>] [-SearchPrefixFlags <UInt16>] [-ShowManagePrivacyRelationships <$true | $false>] [-ShowRecentContacts <$true | $false>] [-ShowSharepointPhotoEditLink <$true | $false>] [-SPSearchCenterExternalURL <String>] [-SPSearchCenterInternalURL <String>] [-SPSearchExternalURL <String>] [-SPSearchInternalURL <String>] [-TabURL <String>] [-TracingLevel <Off | Light | Full>] [-WebServicePollInterval <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the client policy RedmondClientPolicy. In this example, the WebServicePollInterval property is set to 15 minutes (00 hours: 15 minutes: 00 seconds).

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00"

## EXAMPLE 2

In Example 2, three different property values are modified for the client policy RedmondClientPolicy: the properties DisableEmoticons, DisableHtmlIm, and DisableRTFIm are all set to True.

    Set-CsClientPolicy -Identity RedmondClientPolicy -DisableEmoticons $True -DisableHtmlIm $True -DisableRTFIm $True

## EXAMPLE 3

Example 3 also modifies the properties DisableEmoticons, DisableHtmlIm, and DisableRTFIm. In this example, however, the modifications are made to all the client policies that have been configured at the site scope. To do this, the command first uses the **Get-CsClientPolicy** cmdlet and the Filter property to return all the client policies where the Identity begins with the characters "site:"; by definition, those are policies configured at the site scope. This filtered collection is then piped to the **Set-CsClientPolicy** cmdlet, which takes each policy in the collection and modifies the values of DisableEmoticons, DisableHtmlIm, and DisableRTFIm.

    Get-CsClientPolicy -Filter "*site:*" | Set-CsClientPolicy -DisableEmoticons $True -DisableHtmlIm $True -DisableRTFIm $True

## EXAMPLE 4

In Example 4, all the client policies that allow for photos larger than 10 kilobytes are modified; after the modifications these policies will have a maximum photo size of 10 KB. To carry out this task, the **Get-CsClientPolicy** cmdlet is first called without any parameters in order to return a collection of all the client policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the MaxPhotoSizeKb property is greater than (-gt) 10 KB. The filtered collection is then piped to the **Set-CsClientPolicy** cmdlet, which sets the value of the MaxPhotoSizeKb property for each policy in the collection to 10 KB.

    Get-CsClientPolicy | Where-Object {$_.MaxPhotoSizeKb -gt 10} | Set-CsClientPolicy -MaxPhotoSizeKb 10

## Detailed Description

In Lync Server, client policies replace the Group Policy settings used in previous versions of the product. In Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2, Group Policy helped determine what users could do with Communicator and other clients; for example, there were Group Policy settings that determined whether or not users could save a transcript of their instant messaging sessions; whether information from Microsoft Outlook was incorporated into their presence information; and whether or not users could include emoticons or formatted text in instant messages.

As useful as Group Policy can be, however, the technology does have some limitations when applied to Lync Server. For one thing, Group Policy is designed to be applied on a per-domain or per-organizational unit (OU) basis, which makes it difficult to target policies toward a more select group of users (for example, all the users who work in a particular department, or all the users who have a particular job title). For another, Group Policy is only applied to users who log on to the domain and who log on using a computer; Group Policy is not applied to users who access Lync Server over the Internet or who access the system by using a mobile phone. This means that the same user can have a different experience depending on the device he or she uses to log on, and where he or she logs on from.

To help address these inconsistencies, Lync Server uses client policies instead of Group Policy. Client policies are applied each time a user accesses the system, regardless of where the user logs on from and regardless of the type of device the user logs on with. In addition, client policies, like other Lync Server policies, can readily be targeted toward selected groups of users. You can even create a custom policy that gets assigned to a single user.

Client policies can be configured at the global, site, and per-user scopes. The **Set-CsClientPolicy** cmdlet enables you to modify any (or all) of the client policies that have been configured for use in your organization.

Keep in mind that client policies differ from many other policies in that most of the policy settings do not have default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsClientPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClientPolicy"}

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
<td><p><em>AddressBookAvailability</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Client.AddressBookAvailability</p></td>
<td><p>Indicates how users are allowed to access information in the Address Book server (that is, by using the 通讯簿 Web 查询服务 and/or by downloading a copy of the Address Book to their local computer). AddressBookAvailability must be set to one of the following values:</p>
<p>WebSearchAndFileDownload</p>
<p>WebSearchOnly</p>
<p>FileDownloadOnly</p></td>
</tr>
<tr class="even">
<td><p><em>AttendantSafeTransfer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync Attendant operates in &quot;safe transfer&quot; mode; this means that transferred calls that do not reach the intended recipient will reappear in the incoming area along with a &quot;Failed Transfer&quot; notice. When set to False, transferred calls that fail to reach the intended recipient will not reappear in the incoming area.</p></td>
</tr>
<tr class="odd">
<td><p><em>AutoDiscoveryRetryInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>After a failed connection attempt, specifies the amount of time Lync waits before again trying to connect to Lync Server. The AutoDiscoveryRetryInterval can be set to value between 1 second and 60 minutes (1 hour), inclusive.</p>
<p>When specifying the AutoDiscoveryRetryInterval you must use the format hours:minutes:seconds. For example, to set the interval to 25 minutes use this syntax:</p>
<p>- AutoDiscoveryRetryInterval 00:25:00</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Time interval to try autodiscovery.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>BlockConversationFromFederatedContacts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, contacts from outside your organization will not be allowed to initiate instant message conversations with any user that this policy applies to. However, outside users will be able to participate in conversations as long the internal user initiates that conversation. When set to False, outside contacts are allowed to send unsolicited instant messages to users in your organization.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Block conversation from federated contacts.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>CalendarStatePublicationInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the amount of time, in seconds, that Lync waits before retrieving calendar information from Microsoft Outlook and adding this data to your presence information.</p>
<p>For example, to set the CalendarStatePublicationInterval to 10 minutes (600 seconds) use this syntax:</p>
<p>- CalendarStatePublicationInterval 600</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Time interval to publish calendar data to presence.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ConferenceIMIdleTimeout</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates the number of minutes that a user can remain in an instant messaging session without either sending or receiving an instant message.</p>
<p>The ConferenceIMIdleTimeout must be less than or equal to 1 hour, and must be specified using the format hours:minutes:seconds. For example, this syntax sets the timeout value to 45 minutes:</p>
<p>-ConferenceIMIdleTimeout 00:45:00</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>CustomizedHelpUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for custom Lync help set up by an organization. This help, rather than the default product help, will be displayed any time a user clicks the Help menu in Lync. This parameter has been deprecated for use with Lync Server 2013.</p>
<p>Customized help will not be available unless you also set EnableEnterpriseCustomizedHelp to True.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Help menu.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>CustomLinkInErrorMessages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the website that can be added to error messages that appear in Lync. If a URL is specified, that URL will appear at the bottom of any error message that occurs in Lync. Users can then click that link and be taken to a custom website that contains additional information, troubleshooting tips, etc.</p></td>
</tr>
<tr class="even">
<td><p><em>CustomStateUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Specifies the location of the XML file used to add custom presence states to Lync. (Lync allows up to four custom presence states in addition to the built-in states such as Available, Busy, and Do Not Disturb.) The location of the XML file should be specified using the HTTPS protocol.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Custom presence states URL.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Allows administrators to provide additional information about a policy. For example, the Description might indicate the users that the policy should be assigned to.</p></td>
</tr>
<tr class="even">
<td><p><em>DGRefreshInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates the amount of time Lync waits before automatically refreshing the membership list of any distribution group that has been &quot;expanded&quot; in the Contacts list. (Expanding a distribution group means displaying all the members in that group.) DGRefreshInterval can be set to any integer value between 30 seconds and 28,800 seconds (8 hours), inclusive. The default value is 28,800 seconds.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Time interval to refresh the membership of each distribution group.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableCalendarPresence</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, calendar data taken from Microsoft Outlook will not be included in your presence information. When set to False, calendar data will be included in your presence information. For example, free/busy information will be reported in your contact card; likewise, your status will automatically be set to Busy any time Outlook shows that you are in a meeting.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable calendar presence.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableContactCardOrganizationTab</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, the contact card organization tab is not visible within the Lync user interface. When set to False, the contact card organization tab is available in Lync.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableEmailComparisonCheck</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync will not attempt to verify that any currently running instance of Microsoft Outlook belongs to the same user running Lync; for example, the software will not verify that both Outlook and Lync are running under Ken Myer’s user account. Instead, it will be assumed that the two applications are running under the same account and, in turn, will include contact and calendar data in Outlook with Lync.</p>
<p>When set to False, Lync will use SMTP addresses to verify that Outlook and Lync are running under the same account. If the SMTP addresses do not match then contact and calendar data in Outlook will not be incorporated into Lync.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>DisableEmoticons</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users will not be able to send or receive emoticons in their instant messages; instead they will be see the text equivalent of those emoticons. For example, instead of seeing a graphical &quot;smiley face&quot; users will see the text equivalent:</p>
<p>: )</p>
<p>When set to False users will be able to include emoticons in their instant messages, and to view emoticons in instant messages they receive.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable emoticons in instant messages.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableFederatedPromptDisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, any notification dialog generated when you are added to a federated user’s Contacts list will use the federated user’s SIP address (for example, sip:kenmyer@fabrikam.com). When set to False, the notification dialog will use the federated user’s display name (for example, Ken Myer) instead.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Prevent showing the display name of federated, non-PIC contacts in the notification dialog.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableFeedsTab</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, the activity feeds tab will not be displayed in Lync. When set to False, the feeds tab will be available within Lync.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableFreeBusyInfo</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, free/busy information retrieved from Microsoft Outlook will not be displayed in your contact card. When set to False, free/busy information is displayed in your contact card. For example, your contact card might include a note similar to this:</p>
<p>Calendar: Free until 2:00 PM</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable publishing free/busy info.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableHandsetOnLockedMachine</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users will not be able to use their Polycom handset if the computer that the handset is connected to is locked. To use the handset, users will first have to unlock the computer.</p>
<p>When set to False, users will be allowed to use their handset even if the computer the handset is connected to is locked.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Configure handset use on locked machine.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableHtmlIm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, any HTML text copied from a webpage will be converted to plain text when pasted into an instant message. When set to False, HTML formatting (such as font size and color, drop-down lists and buttons, etc.) will be retained when pasted into an instant message.</p>
<p>Note that, even when set to False, scripts and other potentially malicious items (such as tags that play a sound) will not be copied into an instant message. You can copy and paste buttons and other controls into a message, but any scripts attached to those controls will automatically be removed.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Prevent HTML text in instant messages.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableInkIM</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users will not be allowed to receive instant messages containing Tablet PC ink. (Ink is a technology that enables you to insert handwritten notes into a document.) When set to False, users will be allowed to receive messages that contain Table PC ink.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Prevent ink in instant messages.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableMeetingSubjectAndLocation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to False, detailed information about a meeting -- namely, the meeting subject and the location where the meeting is being held -- will be displayed as a tooltip when you view free/busy information in a contact card. When set to True, this detailed information will not be displayed. To completely prevent the display of meeting-related information you should also set DisableCalendarPresence to True.</p>
<p>This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Disable publishing meeting subject and location information.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableOneNote12Integration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><div>

> [!NOTE]  
> This setting applies to the Lync 2010 Client only. Lync 2013 or higher clients do not implement this setting. To disable Shared Notes in conference, refer to <a href="set-csconferencingpolicy.md">Set-CsConferencingPolicy</a> parameter AllowSharedNotes.

</div>
<p>When set to True, the ability to start Microsoft OneNote from within Lync (and the ability to automatically link instant message sessions and OneNote notes) is disabled. When set to False, the option Take Notes Using One Note is enabled in Lync. In addition, if you locate an instant message transcript in Microsoft Outlook’s Conversation History you can retrieve any OneNote notes associated with that conversation just by clicking the Edit conversation notes button.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable OneNote 12 integration.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableOnlineContextualSearch</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, disables the Find Previous Conversations menu option that appears when you right-click a user in your Contacts list. (This option enables you to search the Microsoft Outlook Conversation History folder for previous instant messaging sessions involving the user in question.) When set to False, the Find Previous Conversations option will be available when you right-click a user in your Contacts list.</p>
<p>Note that this setting only applies to users who are not running Microsoft Outlook in cached mode. That’s because any searches conducted by those users must take place on the Exchange Servers, and administrators might want to limit the network traffic causes by these searches. If you are running Outlook in cached mode, searches take place on a user’s locally-cached copy of his or her Inbox. Cached searches are not affected by this setting.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable online contextual search.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisablePhonePresence</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync does not take phone calls into consideration when determining your current status. When set to False, phone calls are taken into consideration when determining your status. For example, any time you are on the phone your status will automatically be set to Busy.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable call presence.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisablePICPromptDisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, any notification dialog box generated when you are added to the Contacts list of a user with an account on a public instant messaging service such as MSN will display that person’s SIP address (for example, sip:kenmyer@litwareinc.com). When set to False, the notification dialog box will use the person’s display name (for example, Ken Myer) instead.</p>
<p>This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Prevent showing the display name of PIC contacts in the notification dialog.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisablePoorDeviceWarnings</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync will not issue warnings (upon startup, in the Tuning Wizard, in the Conversation window, etc.) if an audio or video device is not working correctly. When set to False, these warnings will be issued.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisablePoorNetworkWarnings</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync will not display warnings about poor network quality.</p></td>
</tr>
<tr class="even">
<td><p><em>DisablePresenceNote</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, any Out of Office message you configure in Microsoft Outlook will not be displayed as part of your presence information. When set to False, your Out of Office message will be displayed any time a user holds the mouse over your name in their Contacts list.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Disable presence note.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisableRTFIM</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When both this setting and the DisableHtmlIm settings are set to True, prevents rich text formatting (for example, different fonts, font sizes, and font colors) from being used in instant messages; instead, all messages sent and received will be converted to plain text format. When set to False, rich text formatting will be allowed in instant messages.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Prevent rich text in instant messages.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DisableSavingIM</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, the options for saving an instant message session are removed from the menu bar in the Lync Conversation window. When set to False, these options are available in the Conversation window.</p>
<p>Note that setting this value to True removes the menu options that make it easy for users to save instant message transcripts. However, it does not prevent users from copying all the text in a transcript to the clipboard, pasting that text into another application, and then saving the transcript that way.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Prevent users from saving instant messages.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayPhoto</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Client.DisplayPhoto</p></td>
<td><p>Determines whether or not photos (of both the user and his or her contacts) will be displayed in Lync. Valid settings are:</p>
<p>NoPhoto - Photos are not displayed in Lync.</p>
<p>PhotosFromADOnly - Only photos that have been published in Active Directory 域服务 can be displayed.</p>
<p>AllPhotos - Either Active Directory photos or custom photos can be displayed.</p>
<p>The default value is AllPhotos.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableAppearOffline</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True an additional presence state -- Appear Offline -- is available in Lync. This state makes it appear as though the user is offline; however, he or she will actually be online and available to answer phone calls, respond to instant messages, etc. When set to False, the Appear Offline presence state will not be available in Lync.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Enable the state Appear Offline.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableCallLogAutoArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, information about your incoming and outgoing phone calls is automatically saved to the Conversation History folder in Microsoft Outlook. (The actual call itself is not recorded. What is recorded is information such as who took part in the call; the length of the call; and whether this was an incoming or an outgoing call.) When set to False, this information is not saved to Outlook.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Enable/disable automatic archiving of call logs to Outlook mailbox.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>EnableClientMusicOnHold</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, music will be played any time a caller is placed on hold. When set to False, music will not be played any time a caller is placed on hold. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableConversationWindowTabs</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, supplemental information related to an instant messaging session will be displayed in a separate browser window. This type of information is available only for custom applications that use the Microsoft 统一通信托管 API (UCMA). For example, customer service or help desk personnel, can automatically access related information while chatting with someone.</p>
<p>When set to False, supplemental information will not be displayed in a separate browser window. Although the user can still take part in an instant message session, he or she will not have access to any additional information that accompanies the session.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Enable conversation window tabs.&quot; This parameter has been deprecated for use with Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableEnterpriseCustomizedHelp</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users who click the Help menu in Lync will be given custom help set up by the organization. When set to False, users who click the Help menu will be given the default Lync product help.</p>
<p>When you enable customized help you must also specify the URL for the custom help website; this is done using the CustomizedHelpUrl parameter. If this parameter is not specified, or if the URL is not valid, errors will likely occur when users try to schedule or join meetings.</p>
<p>This parameter has been deprecated for use with Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableEventLogging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, detailed information about Lync will be recorded in the Application event log. When set to False, only major events (such as the failure to connect to Lync Server) are recorded in the event log.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Turn on event logging for Communicator 2007.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>EnableExchangeContactSync</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) Lync creates a corresponding personal contact in Microsoft Outlook for each person on a user’s Lync Contacts list.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableExchangeDelegateSync</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, a user that has been configured in Outlook will be allowed to schedule online Lync Calendar meetings for that user (this happens via Lync UCMAPI delegation, without the need of the Enterprise Voice feature).</p></td>
</tr>
<tr class="even">
<td><p><em>EnableFullScreenVideo</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, this parameter does two things: 1) enables full-screen video (with the correct aspect ratio) for Lync calls; and, 2) disables video preview for Lync calls. When set to False then full-screen video is not available in Lync, but video preview is available.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Enable full screen video and video preview disabled for all OC video calls.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableHighPerformanceConferencingAppSharing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, enables better performance in applications (such as CAD/CAM applications) that have a high screen refresh rate. However, this improved performance will reduce the system resources and network bandwidth available to other applications.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableHighPerformanceP2PAppSharing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, allows a peer-to-peer application sharing session to exceed the maximum frame rate of 2.5 frames per second. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableHotdesking</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, enables users to log on to a phone running Lync Phone Edition in a shared workspace by using their Lync Server account. (Among other things, this provides the user access to his or her contacts.) When set to False, users are not allowed to log on to a phone in a shared workspace by using their own credentials.</p>
<p>Note that this setting applies only to common area (shared workspace) accounts and not to user accounts. When set to True and applied to a common area account for a phone in a shared workspace, any user will be able to log on to that phone by using his or her credentials. When set to False, no one will be allowed to log on to that phone.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>EnableIMAutoArchiving</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, a transcript of every instant message session that a user takes part in will be saved to the Conversation History folder in Microsoft Outlook. When set to False, these transcripts will not be saved automatically. (However, users will have the option to manually save instant message transcripts.)</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Enable/disable automatic archiving of IM conversations to Outlook mailbox.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMediaRedirection</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True) allows audio and video streams to be separated from other network traffic; in turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableNotificationForNewSubscribers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True you will receive notification any time you are added to someone else's Contacts list. In addition, the notification dialog box will provide options for you to add that person to your Contacts list, or to block them from viewing your presence information.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableSQMData</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Note: This setting has been deprecated for Lync Server 2013.</p>
<p>The Customer Experience Improvement Program (CEIP) is designed to help Microsoft collect data on the real-world use of Lync. When a user is enrolled in CEIP, then each time the user runs Lync information about what that user does, and how often they do it, will be sent back to Microsoft, stored in a database, and then analyzed to help identify usage trends.</p>
<p>When EnableSQMData is set to True, the user will not automatically be enrolled in the Customer Experience Improvement Program. However, Lync will provide the user with the option to join the program.</p>
<p>When set to False, the user will not be enrolled in the Customer Experience Improvement Program. In addition, Lync will not give users the option of joining the program. The only way for a user to participate in the CEIP program is for EnableSQMData to be set to True and the user to then manually opt-in to the program.</p>
<p>Note that no personally-identifiable information is sent to the CEIP. The CEIP does not keep track of such things as who you send instant messages to, and vice-versa. Instead, the program tracks information such how often people use Lync to transfer files or the average number of contacts that people have on their Contacts Lists.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Specify instrumentation.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>EnableTracing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, software tracing will be enabled in Lync; when set to False software tracing will be disabled. Software tracing involves keeping an extremely detailed record of everything that a program does (including tracking API calls). As such tracing is mostly useful to developers and to application support personnel.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator 2007.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableUnencryptedFileTransfer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users will be allowed to exchange files with external users whose instant messaging software does not support encrypted file transfers. When set to False, users will only be able to exchange files with external users who have software that supports encrypted file transfers.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Allow transferring unencrypted files.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>EnableURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, hyperlinks embedded in an instant message will be &quot;clickable;&quot; that is, users can click that link and their web browser will open to the specified location. When set to False, hyperlinks appear in instant messages as plain text. To navigate to the location, users will need to copy the link text and paste it into their web browser.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Allow hyperlinks in instant messages.&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableVOIPCallDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, a Lync call will be placed any time a user employs the click-to-call feature.</p>
<p>This policy setting only affects the initial state of the click-to-call feature. If the user modifies the value of the click-to-call setting then the user-selected value will override this policy setting. After a user has modified the click-to-call setting that setting will remain in use and will not be affected by the EnableVOIPCallDefault policy.</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludedContactFolders</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates which Microsoft Outlook contact folders (if any) should not be searched any time Lync searches for new contacts. Multiple folders can be specified by separating the folder names using semicolons; for example: -ExcludedContactFolders &quot;SenderPhotoContacts;OtherContacts&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HelpEnvironment</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When set to &quot;Office 365&quot;, the Office 365 client help documentation for Lync Server 2013 will be shown to users rather than the on-premises help shown by default. You can either set HelpEnvironment to &quot;Office 365&quot; or to a null value ($Null). If set to a null value (the default value) then the on-premises help will be shown to users.</p></td>
</tr>
<tr class="odd">
<td><p><em>HotdeskingTimeout</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Timeout interval for a user logged on to a &quot;hot-desk&quot; phone. (A hot-desk phone is a phone running Lync Phone Edition that is located in a shared workspace, and that users can log on to using their Lync Server account.) The hot-desk timeout specifies the number of minutes that can elapse before a user is automatically logged off of a hot-desk phone. When specifying a hot desking timeout you must use the format hours:minutes:seconds. For example, this syntax sets the hot desking timeout interval to 45 minutes:</p>
<p>-HotdeskingTimeout 00:45:00</p>
<p>Note that this policy setting applies only to common area phones and not to users. The default value is 5 minutes (00:05:00), and the minimum value is 30 seconds (00:00:30).</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier assigned to the new policy. To reference the global policy, use this syntax: -Identity global. To reference a site policy, use the prefix &quot;site:&quot; and the name of the site as your Identity; for example: -Identity site:Redmond. To reference a per-user policy, use syntax similar to this: -Identity SalesClientPolicy.</p></td>
</tr>
<tr class="odd">
<td><p><em>IMWarning</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When configured, the specified message appears in the Conversation window each time a user takes part in an instant messaging session. For example, if IMWarning is set to &quot;All information is the property of Litwareinc&quot; then that message will appear in the Conversation window each time a user takes part in an instant messaging session.</p>
<p>Your warning message should be limited to 256 characters, and can only contain plain text. You cannot use any formatting (such as boldface or italics) and you cannot clickable URLs within the text.</p>
<p>If set to a null value ($Null) then no message appears in the Conversation window.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Warning text.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ClientPolicy</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>MAPIPollInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Important: This parameter has been deprecated for use with Lync Server 2013.</p>
<p>For users of Microsoft Exchange Server 2003, MAPIPollInterval specifies how often Lync retrieves calendar data from the Exchange public folders. MAPIPollInterval can be set to any value between 1 second and 1 hour; inclusive. To configure the MAPI poll interval, use the format hours:minutes:seconds. For example, this command sets the MAPI poll interval to 45 minutes:</p>
<p>-MapiPollInterval 00:45:00</p>
<p>Note that this setting does not apply to users whose email account is on Microsoft Exchange Server 2010 or Microsoft Exchange Server 2007. For those users, calendar retrieval is managed using WebServicePollInterval</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Time interval to load calendar data from MAPI provider.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>MaximumDGsAllowedInContactList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum number of distribution groups that a user can configure as a contact. MaximumDGsAllowedInContactList can be set to any integer value between 0 and 64, inclusive. The default value is 10.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaximumNumberOfContacts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Indicates the maximum number of contacts a user is allowed to have. The maximum contacts can be set to any integer value between 0 and 1000, inclusive. When set to 0, that prevents the user from having any contacts.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Maximum allowed number of contacts.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>MaxPhotoSizeKB</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum size (in kilobytes) for photos displayed in Lync.</p>
<p>The default value is 30 kilobytes.</p></td>
</tr>
<tr class="odd">
<td><p><em>MusicOnHoldAudioFile</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Path to the audio file to be played when a caller is placed on hold. If a value is configured for this property then music on hold will be enabled and users will not be allowed to disable the feature. If no value is configured for this property then users can specify their own music on hold file, assuming that EnableClientMusicOnHold is set to True.</p></td>
</tr>
<tr class="even">
<td><p><em>P2PAppSharingEncryption</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Client.P2PAppSharingEncryption</p></td>
<td><p>Indicates whether or not desktop and application sharing data exchanged during a peer-to-peer conversation is encrypted. Allowed values are:</p>
<p>Supported. Desktop and application sharing data will be encrypted, if possible.</p>
<p>Enforced. Desktop and application sharing data must be encrypted. If the data cannot be encrypted then desktop and application sharing will not be enabled for the conversation.</p>
<p>NotSupported. Desktop and application sharing data will not be encrypted.</p></td>
</tr>
<tr class="odd">
<td><p><em>PlayAbbreviatedDialTone</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, a 3-second dial tone will be played any time a Lync-compatible handset is taken off the hook. (A Lync-compatible handset looks like a standard telephone, but plugs into a USB port on your computer and is used to make Lync calls rather than &quot;regular&quot; phone calls.) When set to False, a 30-second dial tone is played any time a Lync-compatible handset is taken off the hook.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Play abbreviated dial done.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>PolicyEntry</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Provides a way to add settings not covered by the default parameters. For example, when testing pre-release versions Microsoft Lync Server 2010 it was possible to add a Send Feedback option to Microsoft Lync 2010. That was done by using code similar to this:</p>
<p>$x = New-CsClientPolicyEntry -Name &quot;OnlineFeedbackURL&quot; -Value &quot;http://www.litwareinc.com/feedback&quot;Set-CsClientPolicy -Identity global -PolicyEntry @{Add=$x}</p>
<p>For more details and examples, see the <a href="new-csclientpolicyentry.md">New-CsClientPolicyEntry</a> cmdlet help topic.</p></td>
</tr>
<tr class="odd">
<td><p><em>SearchPrefixFlags</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Represents the Address Book attributes that should be used any time a user searches for a new contact. The search prefix flags are constructed as a binary number such as 1110111, in which a 1 indicates that the attribute should be searched and a 0 indicates that the attribute should not be searched. The attributes in the binary value are (from right to left):</p>
<p>Primary email address</p>
<p>Email alias</p>
<p>All email addresses</p>
<p>Company</p>
<p>Display name</p>
<p>First name</p>
<p>Last name</p>
<p>The binary value 1110111 means that all attributes should be searched except attribute 4: Company. To search only display name, first name, and last name you would construct this value:</p>
<p>1110000</p>
<p>After the binary value has been constructed it must then be converted to a decimal value before being assigned to SearchPrefixFlags. To convert a binary number to a decimal number you can use the following Windows PowerShell command:</p>
<p>[Convert]::ToInt32(&quot;1110111&quot;, 2)</p>

> [!NOTE]  
> Manual registry key creation is required for the search prefix flags to be implemented. A SearchPrefixFlags key must be created for either the machine or user as in the following examples. The &quot;119&quot; value is the integer equivalent of a &quot;1110111&quot; SearchPrefixFlags binary. The integer you enter will be based on your own search preferences.<br />
Use the appropriate Office version in the registry keys.
> <ul>
> <li><p>14.0 – Office 2010</p></li>
> </ul>
> <code>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Communicator\SearchPrefixFlags</code>
> <ul>
> <li><p>15.0 – Office 2013</p></li>
> <li><p>16.0 – Office 2016</p></li>
> </ul>
> <code>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\&lt;Office Version&gt;\Lync\SearchPrefixFlags --&gt; DWORD 119</code><br />
> <code>HKEY_LOCAL_USER\SOFTWARE\Policies\Microsoft\Office\&lt;Office Version&gt;\Lync\SearchPrefixFlags --&gt; DWORD 119</code>

</td>
</tr>
<tr class="even">
<td><p><em>ShowManagePrivacyRelationships</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, shows the Relationships option in the Lync Contacts list window. When set to False, hides the Relationships option.</p>
<p>Note that this setting applies only to Lync 2010. Lync 2013 will not show these relationships even if ShowManagePrivacyRelationships has been set to True.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>ShowRecentContacts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has no effect on the client.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>ShowSharepointPhotoEditLink</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, Lync will include a link that enables users to edit the personal photo stored on their SharePoint MySite. The default value is False, which means that Lync will not include a link to the SharePoint MySite.</p></td>
</tr>
<tr class="odd">
<td><p><em>SPSearchCenterExternalURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>External URL for the SharePoint site used for keyword searches (also known as expert searches). This URL will appear at the bottom of any keyword search results that appear in Lync. If the user clicks this URL, his or her web browser will open up to the SharePoint site, giving the user the opportunity to conduct searches using SharePoint’s search capabilities. (SharePoint offers more search options than Lync does.)</p>
<p>SPSearchCenterExternalURL represents the URL for external users; that is, for users logging on from outside the organization’s firewall. The parameter SPSearchCenterInternalURL is for users who log on from inside the firewall.</p></td>
</tr>
<tr class="even">
<td><p><em>SPSearchCenterInternalURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Internal URL for the SharePoint site used for keyword searches (also known as expert searches). This URL will appear at the bottom of any keyword search results that appear in Lync. If the user clicks this URL, his or her web browser will open up to the SharePoint site, giving the user the opportunity to conduct searches using SharePoint’s search capabilities. (SharePoint offers more search options than Lync does.)</p>
<p>SPSearchCenterInternalURL represents the URL for internal users; that is, for users logging on from inside the organization’s firewall. The parameter SPSearchCenterExternalURL is for users who log on from outside the firewall.</p></td>
</tr>
<tr class="odd">
<td><p><em>SPSearchExternalURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>External URL for the SharePoint site used for keyword searches (also known as expert searches). Lync will use the SharePoint site located at this URL any time an external user (that is, a user who has accessed the system from outside the organization’s firewall) conducts a keyword search.</p></td>
</tr>
<tr class="even">
<td><p><em>SPSearchInternalURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Internal URL for the SharePoint site used for keyword searches (also known as expert searches). Lync will use the SharePoint site located at this URL any time an internal user (that is, a user who has logged on from inside the organization’s firewall) conducts a keyword search.</p></td>
</tr>
<tr class="odd">
<td><p><em>TabURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Specifies the location of the XML file used to create custom tabs located at the bottom of the Lync Contacts list window. Custom tabs provide access to webpages (for example, help desk webpages) from within Lync. This parameter has been deprecated for use with Lync Server 2013.</p>
<p>This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting &quot;Tab URL.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>TracingLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Client.TracingLevel</p></td>
<td><p>Enables Administrators to manage event tracing and logging in Lync 2013. Allowed values are:</p>
<p>* Off – Tracing is disabled and the user cannot change this setting.</p>
<p>* Light – Minimal tracing is performed, and the user cannot change this setting.</p>
<p>* Full – Verbose tracing is performed, and the user cannot change this setting.</p>
<p>By default TracingLevel is set to Light.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebServicePollInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>For users of Microsoft Exchange Server 2007 and later versions of the product, WebServicePollInterval specifies how often Lync retrieves calendar data from Microsoft Exchange Server Web Services. WebServicePollInterval can be set to any value between 1 second and 1 hour; inclusive. To configure the Web Service poll interval, use the format hours:minutes:seconds. For example, this command sets the Web Service poll interval to 45 minutes:</p>
<p>-WebServicePollInterval 00:45:00</p>
<p>Note that this setting does not apply to users whose email account is on Exchange 2003. For those users, calendar retrieval is managed using MAPIPollInterval.</p>
<p>This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Time interval to load calendar data from Web service provider.&quot;</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Client.ClientPolicy object. The **Set-CsClientPolicy** cmdlet accepts pipelined instances of the client policy object.

## Return Types

The **Set-CsClientPolicy** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Client.ClientPolicy object.

## 另请参阅

#### 其他资源

[Get-CsClientPolicy](get-csclientpolicy.md)  
[Grant-CsClientPolicy](grant-csclientpolicy.md)  
[New-CsClientPolicy](new-csclientpolicy.md)  
[Remove-CsClientPolicy](remove-csclientpolicy.md)

