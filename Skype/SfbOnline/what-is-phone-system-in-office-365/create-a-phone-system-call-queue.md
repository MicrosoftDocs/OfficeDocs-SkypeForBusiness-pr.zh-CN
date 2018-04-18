---
title: Create a Phone System call queue
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 3396d7d56adc6fb8ecd531e17284e48bbee5edbf
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="create-a-phone-system-call-queue"></a>Create a Phone System call queue

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Phone System call queues can provide:
  
- 组织问候语。
    
- 在呼叫者保持等待时播放的音乐。
    
- Redirecting of calls to call agents in mail-enabled distribution lists and security groups.
    
- 设置呼叫队列的大小、超时时间和处理选项。
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. 呼叫者在等待时会听到音乐，系统将按照 *先进先出*  (FIFO) 的方式为呼叫分配呼叫代理。
  
All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:
  
- With attendant routing, the first call in the queue will ring all agents at the same time.
    
- With serial routing, the first call in the queue will ring all call agents one by one.
    
    > [!NOTE]
    > Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
    
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。
    
## <a name="step-1---getting-started"></a>第 1 步 - 开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。 
  
- When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:
    
  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）
    
  - Lync 桌面客户端 2013（32 位和 64 位版本）
    
  - 支持 Skype for Business Online 的所有 IP 电话型号。 请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。
    
  - Mac Skype for Business Client (version 16.8.196 and later) 
    
  - Android Skype for Business Client (version 6.16.0.9 and later)
    
  - iPhone Skype for Business Client (version 6.16.0 and later)
    
  - iPad Skype for Business Client (version 6.16.0 and later)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>第 3 步 - 创建新的呼叫队列

In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>设置呼叫队列显示名称、电话号码和域（如有）

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Number 1](../images/sfbcallout1.png)<br/>
**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。<br/> 此名称将显示在传入呼叫的通知中。
***
![Number 2](../images/sfbcallout2.png)<br/>**电话号码** 为呼叫队列选择收费或免费服务电话号码。 This is optional. <br/> 如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。 To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Number 3](../images/sfbcallout3.png)<br/>**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。<br/> 例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**问候语**是可选设置。 This is the greeting that is played for people who call in to the call queue number. <br/> You can upload an audio file (.wav, .mp3, or .wma formats).
***
![Number 2](../images/sfbcallout2.png)<br/>**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold. 
   

### <a name="select-the-call-distribution-method"></a>Select the call distribution method

![Shows the call distribution method options](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.  <br/><br/>  **Note:** Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.  
   
### <a name="select-an-agent-opt-out-option"></a>Select an agent opt out option

![Shows the agent opt out check box](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/>**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> To access the opt-out option, agents can do the following:
 1. Open **Options** in their desktop Skype for Business client. 
 2. On the **Call Forwarding** tab, click the **Edit settings online** link.
 3. On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.
 
    > [!NOTE] 
    > Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.
   
### <a name="add-call-agents-to-a-call-queue"></a>向呼叫队列添加呼叫代理

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/><br/>Call agents (50 maximum) can be:
*    An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Online users with a with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

    > [!NOTE] 
    > Users hosted on-premises using Lync Server 2010 aren't supported.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>设置队列最大大小和最长等待时间。

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Number 1](../images/sfbcallout1.png)<br/><br/>**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。 The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Number 2](../images/sfbcallout2.png)<br/><br/>**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.
*    **断开连接并显示繁忙信号** 呼叫将断开连接。
*    **Forward this call to** When you choose this, you will have these options:
     *    **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. 你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Users hosted on-premises using Lync Server 2010 aren't supported.<br/>
     
     *    **Call Queue** You must have already created another call queue, but after you do, you can select that call queue.
     *    **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Number 3](../images/sfbcallout3.png)<br/><br/>**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。<br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Number 4](../images/sfbcallout4.png)<br/><br/>**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：
*    **断开连接** 呼叫将断开连接。
*    **Forward this call to** When you choose this, you will have these options:
     *    **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. 你可以通过此设置将呼叫者直接转到语音邮件。 To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Users hosted on-premises using Lync Server 2010 aren't supported.<br/>

     *    **Call Queue** You must have already created another call queue, but after you do, you can select that call queue.
     *    **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Changing the user's Caller ID to be a call queue's phone number

You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.
  
To do this, run:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
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

  
 