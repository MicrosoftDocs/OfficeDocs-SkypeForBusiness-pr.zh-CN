
可以通过自定义资源帐户响应和处理会议邀请的方式来改进Teams 会议室会议体验。 使用 Exchange Online PowerShell，可以设置以下资源帐户属性：

- **AutomateProcessing： `AutoAccept`** 会议组织者在没有人工干预的情况下直接收到会议室预留决定。

- **AddOrganizerToSubject： `$false`** 会议组织者不会添加到会议请求的主题中。

- **DeleteComments： `$false`** 将任何文本保留在传入会议请求的消息正文中。 这是处理外部 Teams 和第三方会议以提供 One Touch Join 体验所必需的。

- **DeleteSubject： `$false`** 保留传入会议请求的主题。

- **ProcessExternalMeetingMessages： `$true`** 指定是否处理源自 Exchange 组织外部的会议请求。 外部 Teams 会议和第 [三方会议](/microsoftteams/rooms/third-party-join)是必需的。

- **RemovePrivateProperty： `$false`** 确保会议组织者在原始会议请求中发送的私有标志保持指定状态。

- **AddAdditionalResponse： `$true`** AdditionalResponse 参数指定的文本将添加到会议请求中。

- **AdditionalResponse：“这是一个 Microsoft Teams 会议室！** 要添加到会议接受响应的其他文本。

若要配置这些属性，需要连接到 Exchange Online PowerShell。 有关详细信息，请参阅[“连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)”。

连接到 Exchange Online PowerShell 后，可以使用 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing) cmdlet 在资源帐户上配置邮箱属性。

以下示例设置资源帐户的 `ConferenceRoom01` 属性：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

