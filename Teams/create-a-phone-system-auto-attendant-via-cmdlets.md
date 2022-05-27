---
title: 通过 cmdlet 创建自动助理
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: 了解如何通过 cmdlet 配置自动助理
ms.openlocfilehash: a3f669a6540e42cd0ff4a016da0215ca79f3bd22
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676608"
---
# <a name="create-an-auto-attendant-via-cmdlets"></a>通过 cmdlet 创建自动助理

## <a name="assumptions"></a>假设

1. PowerShell 安装在计算机上

   - 为计算机设置[Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - 已安装 MSTeams 模块

     ```PowerShell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - 已安装 MSOnline 模块

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. 你拥有租户管理权限
3. 已购买Microsoft Teams 电话
4. 下面提到的呼叫队列已按照 [PowerShell cmdlet 创建呼叫队列](create-a-phone-system-call-queue-via-cmdlets.md) 指南进行设置。

**注意**：下面引用的某些 cmdlet 可能是公共预览版 Teams PowerShell 模块的一部分。 有关详细信息，请参阅[“安装Teams PowerShell 公共预览版](teams-powershell-install.md)”，另请参阅 [Microsoft Teams PowerShell 发行说明](teams-powershell-release-notes.md)。

已安装 MicrosoftTeams 模块的用户应 `Update-Module MicrosoftTeams` 确保安装最新版本。

## <a name="scenario"></a>使用场景

将生成以下自动助理调用流：

![使用 cmdlet 生成的自动助理呼叫流图。](media/create-a-phone-system-auto-attendant-via-cmdlets.png)

其他配置信息：

- 自动助理：Contoso Main
  - 运算符：阿黛尔·万斯
  - 启用语音输入：关闭
  - 目录搜索：无
  - 假期：
    - 2022 年 1 月 1 日
    - 2022 年 12 月 24 日
    - 2022 年 12 月 25 日

- 自动助理：Contoso 按名称拨号
  - 运算符：阿黛尔·万斯
  - 时区：UTC
  - 语言：美国英语
  - 启用语音输入：打开
  - 问候语：无
  - 菜单：TTS，“请说出或输入要联系的人员的姓名。 若要返回到上一个菜单，请按 9”
  - 目录搜索：按名称拨号
  - 拨号范围：销售&支持成员

## <a name="login"></a>登录

系统将提示输入Teams管理员凭据。

```PowerShell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="get-operator-information"></a>获取操作员信息

```PowerShell
$operatorID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
```

## <a name="dial-by-name-auto-attendant---resource-account-creation"></a>按名称拨号自动助理 - 创建资源帐户

**注意**：在此处创建资源帐户，以便可以在主自动助理上引用它。 稍后将创建实际的“按名称拨号”自动助理。

### <a name="get-license-types"></a>获取许可证类型

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>创建和分配资源帐户

**注意**：此处不需要电话号码，因为呼叫队列由自动助理预先结束

- ApplicationID
  - 自动助理：ce933385-9390-45d1-9512-c8d228074e07
  - 呼叫队列：11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").ObjectID
```

## <a name="contoso-main-menu-auto-attendant"></a>Contoso 主菜单自动助理

### <a name="create-holiday-schedules"></a>创建假日计划

```PowerShell
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
```

### <a name="create-address-fax-and-email-information-prompt"></a>创建地址、传真和电子邮件信息提示

```PowerShell
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
```

### <a name="create-holiday-prompts-and-menu-options"></a>创建假日提示和菜单选项

```PowerShell
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year's holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
```

### <a name="create-after-hours-schedules"></a>创建下班后计划

```PowerShell
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
```

### <a name="create-after-hours-prompts-and-menu-options"></a>创建下班后提示和菜单选项

```PowerShell
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To leave a voicemail for our sales team press 1.To leave a message for our support team press 2.If you know the name of the person you would like to reach, press 3.For our address, email and fax information press 4."

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity "ContosoDialByNameAA-RA@contso.com").Identity

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
```

### <a name="create-after-hours-menu-and-call-flow"></a>创建“下班后”菜单和呼叫Flow

```PowerShell
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
```

### <a name="create-open-hours-prompts-and-menu-options"></a>创建开放时间提示和菜单选项

```PowerShell
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator."

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").ObjectID

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").ObjectID

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
```

### <a name="create-open-hours-menu"></a>“创建开放时间”菜单

```PowerShell
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
```

### <a name="create-auto-attendant"></a>创建自动助理

```PowerShell
$autoAttendant = New-CsAutoAttendant -Name "Contoso Main" -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId "en-US" -TimeZoneId "Eastern Standard Time" -Operator $operatorEntity
```

### <a name="get-license-types"></a>获取许可证类型

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>创建和分配资源帐户

- ApplicationID
  - 自动助理：ce933385-9390-45d1-9512-c8d228074e07
  - 呼叫队列：11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoMainAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoMainAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
```

### <a name="get-list-of-unassigned-service-numbers"></a>获取未分配服务号码的列表

```PowerShell
Get-CsOnlineTelephoneNumber -IsNotAssigned -InventoryType Service
```

#### <a name="assign-available-phone-number"></a>分配可用电话号码
注意：分配给电话号码的使用情况位置必须与分配给资源帐户的使用位置匹配。

```PowerShell
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
```

## <a name="dial-by-name-auto-attendant---completion"></a>按名称拨号自动助理 - 完成

### <a name="create-dial-scope"></a>创建拨号范围

```PowerShell
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
```

### <a name="create-prompts-and-menu-options"></a>创建提示和菜单选项

```PowerShell
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9"

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name "Contoso Dial By Name" -DefaultCallFlow $dialByNameCallFlow -LanguageId "en-US" -TimeZoneId "UTC" -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
```

### <a name="assign-resource-account"></a>分配资源帐户

```PowerShell
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
```
