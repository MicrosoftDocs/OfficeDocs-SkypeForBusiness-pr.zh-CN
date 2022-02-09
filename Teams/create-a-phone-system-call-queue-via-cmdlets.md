---
title: 通过 cmdlet 创建呼叫队列
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 了解如何通过 cmdlet 配置呼叫队列
ms.openlocfilehash: aa3330af2a47c87fc71f63396b84f8ad017e19b5
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457442"
---
# <a name="create-a-call-queue-via-cmdlets"></a>通过 cmdlet 创建呼叫队列

## <a name="assumptions"></a>假设
1)  PowerShell 已安装在计算机上
- 为计算机[设置Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- 已安装 MSTeams 模块 ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- 已安装 MSOnline 模块 ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  你拥有租户管理权限
3)  你已购买Microsoft Teams 电话
4)  已创建Teams代理、通讯组列表和频道

注意：下面Teams频道 cmdlet 是 PowerShell 模块的公共预览Teams的一部分。  有关详细信息，请参阅安装 Teams [PowerShell 公共预览](teams-powershell-install.md)版，Microsoft Teams [PowerShell 发行说明](teams-powershell-release-notes.md)。

已安装 MicrosoftTeams 模块 ````Update-Module MicrosoftTeams```` 的用户应确保已安装最新版本。


## <a name="scenario"></a>使用场景

将创建以下三个调用队列：

销售呼叫队列信息：
- 前端自动助理：是
- 从 PSTN 直接呼叫：否
- 语言：美国英语
- 问候语：无
- 音乐保持：播放音频文件
- - 文件名：sales-hold-in-queue-music.wav
- 呼叫应答：用户
- - Bill@contoso.com
- - Mary@contoso.com
- 会议模式：打开
- 路由方法：Attendant
- 基于状态路由：关闭
- 呼叫代理可以选择不接听呼叫：是
- 呼叫代理警报时间：15
- 呼叫溢出处理：200
- - 重定向到：Adele@contoso.com
- 调用超时处理：120 秒
- - 重定向到：Adele@contoso.com

支持呼叫队列信息：
- 前端自动助理：是
- 从 PSTN 直接呼叫：否
-   语言：英国英语
-   问候语：播放音频文件
-   - 文件名：support-greeting.wav
-   音乐保持：播放音频文件
-   - 文件名：support-hold-in-queue-music.wav
-   呼叫应答：支持通讯组列表
-   - Support@contoso.com
-   会议模式：打开
-   路由方法：最长空闲
-   基于状态路由：N/A – 默认启用，因为最长空闲
-   呼叫代理可以选择不接听呼叫：否
-   呼叫代理警报时间：15
-   呼叫溢出处理：200
-   - 重定向：支持共享语音邮件
- - -   使用 support-shared-voicemail-greeting.wav (播放音频文件) 
- - -   已启用听录
-   调用超时处理：45 分钟
-   - 重定向：支持共享语音邮件
- - - TTS："很抱歉，我们一直等待你，现在将你的呼叫转接到语音邮件。"
- - - 已启用听录


设施协作呼叫队列信息：
- 前端自动助理：否
- 从 PSTN 直接呼叫： (内部呼叫) 
-   语言：法语 FR
-   问候语：无
-   音乐保留：默认值
-   呼叫应答：团队：设施
-   呼叫应答渠道：技术支持
-   - 频道所有者：Fred@contoso.com
-   会议模式：打开
-   路由方法：轮循机制
-   基于状态路由：打开
-   呼叫代理可以选择不接听呼叫：否
-   呼叫代理警报时间：15
-   呼叫溢出处理：200
-   - 断开连接
-   调用超时处理：45 分钟
-   - 断开连接


## <a name="login"></a>登录
系统会提示输入管理员Teams凭据。
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>销售队列
### <a name="create-audio-files"></a>创建音频文件
将"d：\\"替换为将 wav 文件存储在计算机上的路径。

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>获取用户 ID
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>获取支持的语言列表
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>创建呼叫队列
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>获取许可证类型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>创建和分配资源帐户
注意：电话呼叫队列是前端的，因此此处不需要自动助理
- ApplicationID
- - 自动助理：ce933385-9390-45d1-9512-c8d228074e07
- - 呼叫队列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：下面显示的许可证 (PHONESYSTEM_VIRTUALUSER) 必须是上面 cmdlet Get-MsolAccountSku的许可证类型。

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>支持队列
### <a name="create-audio-files"></a>创建音频文件
将"d：\\"替换为将 wav 文件存储在计算机上的路径。

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>获取支持团队组 ID
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>获取支持的语言列表
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>创建呼叫队列
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>获取许可证类型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>创建和分配资源帐户
注意：电话呼叫队列是前端的，因此此处不需要自动助理
- ApplicationID
- - 自动助理：ce933385-9390-45d1-9512-c8d228074e07
- - 呼叫队列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：下面显示的许可证 (PHONESYSTEM_VIRTUALUSER) 必须是由上述 cmdlet Get-MsolAccountSku的许可证类型。

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>设施协作呼叫队列
### <a name="get-facilities-team-group-id"></a>获取设施团队组 ID
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>获取设施技术支持团队频道 ID
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>获取设施技术支持频道所有者用户 ID
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>代表调用资源帐户 ID 获取
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>获取支持的语言列表
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>创建呼叫队列
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>获取许可证类型
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>创建和分配资源帐户
注意：电话呼叫队列是前端的，因此此处不需要自动助理
- ApplicationID
- - 自动助理：ce933385-9390-45d1-9512-c8d228074e07
- - 呼叫队列：11cd3e2e-fccb-42ad-ad00-878b93575e07

注意：下面显示的许可证 (PHONESYSTEM_VIRTUALUSER) 必须是由上述 cmdlet Get-MsolAccountSku的许可证类型。

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
