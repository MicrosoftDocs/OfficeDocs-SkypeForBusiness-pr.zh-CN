---
title: Set up a Phone System auto attendant
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up and test Phone System (Cloud PBX) auto attendants for efficient call handling for your organization. '
ms.openlocfilehash: 456c60fb02b3ef63b14b2ff2e369c78a90edeb0d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Set up a Phone System auto attendant

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.
  
If you want to learn more about auto attendants, see [What are Phone System auto attendants?](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>第 1 步 - 开始

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service numbers, they will show up on the **Skype for Business admin center** > **Voice** > **Phone numbers** page. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md), or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). **User (subscriber)** numbers can't be assigned to auto attendants. If you are outside the United States, you can't use the Skype for Business admin center to get service numbers; go [here](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead.
    
    > [!CAUTION]
    > To get and use toll-free phone numbers, you need to set up Communications Credits. To do this see [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) and [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for auto attendants. The numbers of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 你还可以使用 Windows PowerShell。 For example, run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>第 2 步 - 创建新的自动助理

In the **Skype for Business admin center**, click **Call routing** > **Auto attendants**, then click **Add new**:
  
### <a name="edit-general-info-page"></a>"编辑常规信息"页面
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Name** Enter a descriptive display name for your auto attendant. 此名称为必填字段，最多可以包含 64 个字符，其中包括空格。 此名称将显示在" **自动助理**"选项卡的" **名称**"列中。
***

![Number 2](../images/sfbcallout2.png)<br/>**Phone number** This setting is optional. If you like, select a phone number for your auto attendant. You can pick any available service toll or toll-free phone number that you have for your organization. 如果没有列出任何电话号码，则需要获取收费或免费服务电话号码。 Go [here](getting-service-phone-numbers.md) to get them. <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![Number 3](../images/sfbcallout3.png)<br/>**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。每个自动助理可以有不同的时区，为自动助理设置的营业时间将根据你在此处选择的时区进行设置。
***
![14](../images/sfbcallout4.png)<br/>**语言** 从列出的可用语言列表中选择自动助理使用的语言。 The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.
***
![Number 5](../images/sfbcallout5.png)<br/>**Speech recognition** Speech recognition is available and if this option is selected. People that call in can use voice input in the language you set. You can disable speech recognition by clearing it if you want to only let people use their phone keypad.
***
![Number 6](../images/sfbcallout6.png)<br/>**接线员** 此为可选字段，无须为自动助理设置。 However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them. <br/> <br/> 键 0 自动分配给接线员。 <br/> <br/> If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page. If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option. 例如，"如需接线员，请按零"。 <br/><br/>  可以将以下项设置为接线员： 
*    **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. <br/>

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 isn't supported. <br/> 

*    A **Call Queue** that you have set up. 
*    你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail. 
   
### <a name="select-hours-of-operation-page"></a>"选择营业时间"页面

By default, business hours are set to 24 hours a day, 7 days a week, so all hours are considered business hours. 营业时间以外的所有时间为非营业时间。 If you select the **Custom** option and set your business hours, then a new page called **After hours call handling** will be added where you can configure the call handling for after business hours for the auto attendant.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Number 1](../images/sfbcallout1.png)<br/>选择" **自定义**"选项可在日历中选择特定的营业时间。选择" **自定义**"后，默认情况下将营业时间设置为周一至周五，上午 9:00 - 下午 5:00。
***
![Number 2](../images/sfbcallout2.png)<br/>要更改营业时间，请使用日历突出显示希望设置的营业时间。 The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page. 要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。 You can set multiple breaks within business hours. 
   
### <a name="select-business-hours-call-handling-page"></a>Select business hours call handling page

> [!TIP]
> [!提示] 如果使用自定义营业时间表，则还需要设置非营业时间的呼叫处理方式。将增加一个" **非营业时间呼叫处理**"页面以便你配置这些选项，此页面提供的选项与设置" **营业时间呼叫处理**"的选项相同。 
  
You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Company greeting** Business hours greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **None** No greeting will be played when people call in to the auto attendant phone number.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Welcome to Contoso. Your call is important to us." in the **Callers will hear** box.
*    **Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).
***
![Number 2](../images/sfbcallout2.png)<br/>You can select what happens to calls that arrive during business hours. You can chose from the following options:
*    **Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.
*    **Redirect call** This can be used to automatically send the call to:
     *    **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. 你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/><br/>   
        > [!Note]
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

     *    A **Call Queue** Using a Call Queue allows the call to be transferred to an existing Call Queue that you have set up.
     *    Another **Auto attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.
*    **Play menu options prompt** These can also be used to let you set up a prompt you want played.
***
![Number 3](../images/sfbcallout3.png)<br/>**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。可以在 **呼叫者将听到**框中输入提示或录制音频文件并播报，例如"如需销售，请按或报 1。如需服务，请按或报 2。如需客户支持，请按或报 3。如需接线员，请按或报 0。如需重听此菜单，请按星号键或报'重复'。" **创建自定义提示** 如果选择此选项，应输入希望系统播报的文本（最多 1000 个字符）。 **上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。
***
![Number 4](../images/sfbcallout4.png)<br/>**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search. You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page. Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.<br/><br/>  **Caution:** Users hosted on-premises using Lync 2010 **can't be reached** with Dial by Name.
***

![Number 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. To add a menu option, press the corresponding key on the keypad. The keys in use will change in color and the corresponding row of options will appear below. To delete a menu option, simply click on the corresponding key on the keypad control to deselect this key. The key mapping row will be removed.<br/><br/>  **Tip:** You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.  <br/><br/>  Any menu option can be added and removed in any order, and the key mappings don't have to be continuous. It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

To set up your menu options, after you select the key(s), you will need to: 
- **Enter the Name of the option** This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds." If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3. 
- The next step is to select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition. The call can be sent to: 
    - **Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365. 你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.<br/><br/> 
    
        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

    - **Call Queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>
    
        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.         
   
### <a name="select-holidays-page"></a>Select holidays page 

You can add up to 20 scheduled holidays to each auto attendant.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Add a holiday** Enter a name for your new holiday in the **Holiday name** field.<br/><br/> Holiday names may consist of up to 64 characters and must be unique for the same auto attendant. For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.  
***
![Number 2](../images/sfbcallout2.png)<br/>**Holiday Greeting** The Holiday Greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **None** No greeting will be played when people call in to the auto attendant phone number.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Happy New Year! Our offices are currently closed." in the **Callers will hear** box.
*    **Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format).  
***
![Number 3](../images/sfbcallout3.png)<br/>**What happens to the calls after the greeting?** You can select what happens to the calls that arrive during this holiday. You can chose from the following options:
*    **Disconnect** The person calling in will be disconnected after hearing the holiday greeting.
*    **Redirect call** This can be used to automatically send the call to:
     *    A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. 你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail. <br/><br/> 
     
         > [!Note] 
         > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported.<br/><br/>

     *    A **Call Queue** to transfer the call to an existing Call Queue that you have set up.
     *    Another **Auto attendant**, to create a second level of menu options containing a submenu. These are called nested auto attendants. <br/><br/>
     
         > [!Note]
         > By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.

***
![Number 4](../images/sfbcallout4.png)<br/>**When do you want the holiday to start and end?** Enter your holiday start date in dd/mm/yyyy format, and then select a start time, end date, and end time, as prompted in the date range table.<br/><br/>You can specify up to 10 different date ranges for a holiday. For example, you could add date ranges for New Year's Eve holidays for up to 10 years. A holiday can span multiple days.<br/><br/>To add additional holiday date ranges (for example, for the next year), click **Add another**, and then enter a new set of start and end dates for the holiday.<br/><br/>Nested holidays are also supported. For example, you could nest multiple holidays within one "holiday break" time frame: 
*    **December 24 through January 3:** "Happy Holidays! Our offices are currently closed. We will reopen on January 4th."
*    **December 25:** "Merry Christmas! Our offices are currently closed. We will reopen on January 4th."
*    **January 1:** "Happy New Year! Our offices are currently closed. We will reopen on January 4th."
   
After you save your auto attendant, your holidays appear on the **Holidays** tab, where you can edit, add, or modify holiday settings.
  
### <a name="select-dial-scope-page"></a>"选择拨叫范围"页面

On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>使用" **包括**"选项时，可以从两个选项中选择：
*    **所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。 All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed. 
*    **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

    > [!Caution]
    > On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name. 
***
![Number 2](../images/sfbcallout2.png)<br/>Using the **Exclude** option, you have two options:
*    **无** 使用此选项表示不会将任何在线用户从目录搜索中排除。 
*    **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

    > [!Caution]
    > On-premises users from deployments of Lync Server 2010 won't be listed when someone searches the directory using Dial by Name.          
   
> [!NOTE]
> It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition. 
  
After you enter all the required fields and set up call handling menus and options, click **Save**.
  
## <a name="editing-and-testing-auto-attendants"></a>Editing and testing auto attendants

保存自动助理后，自动助理将在" **自动助理**"页面列出。 This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.
  
If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.
  
You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置自动助理。
  
### <a name="auto-attendant-cmdlets"></a>自动助理 cmdlet

以下是管理自动助理时需要使用的 cmdlet。
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[下面是 Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
