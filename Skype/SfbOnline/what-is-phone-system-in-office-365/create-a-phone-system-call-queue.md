---
title: 创建电话系统呼叫队列
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: '了解如何设置 Office 365 (云 PBX) 呼叫队列以获得组织问候语、保持音乐和将呼叫重定向到通讯组列表和安全组中的呼叫代理。还可以设置最大队列大小、超时和呼叫处理选项。 '
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375146"
---
# <a name="create-a-phone-system-call-queue"></a>创建电话系统呼叫队列

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
电话系统呼叫队列可提供：
  
- 组织问候语。
    
- 在呼叫者保持等待时播放的音乐。
    
- 重定向的呼叫已启用邮件的通讯组列表和安全组中代理的呼叫。
    
- 发出呼叫队列最大大小、 超时和呼叫处理选项设置。
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
将使用 attendant 的路由模式或串行路由模式分发队列中等待的所有呼叫：
  
- 助理路由队列中的第一个呼叫将同时拨打所有代理。
    
- 使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。
    
    > [!NOTE]
    > 不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
    
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。
    
## <a name="step-1---getting-started"></a>第 1 步 - 开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 通话套餐的详细信息，请参阅 [Office 365 中有哪些通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365) 和 [Office 365 的通话套餐](/microsoftteams/calling-plans-for-office-365)。
    
    > [!NOTE]
    > 用户托管在本地为呼叫队列代理不支持使用 Lync Server 2010。 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。 
  
- 当您要分发从电话系统呼叫队列的传入呼叫时，呼叫代理支持这些客户端：
    
  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）
    
  - Lync 桌面客户端 2013（32 位和 64 位版本）
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本） 
    
  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）
    
  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）
    
  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）

  - Microsoft Teams Windows 客户端 （32 和 64 位版本）

  - Microsoft Teams Mac 客户端

  - Microsoft Teams iPhone 应用

  - Microsoft Teams Android 应用
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>第 3 步 - 创建新的呼叫队列

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>设置呼叫队列显示名称、电话号码和域（如有）

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![第一](../images/sfbcallout1.png)<br/>
**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。<br/> 此名称将显示在传入呼叫的通知中。
***
![第二](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![第三](../images/sfbcallout3.png)<br/>**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。 <br/> 例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> 您可以上载音频文件 （.wav、.mp3 或.wma 格式）。
***
![第二](../images/sfbcallout2.png)<br/>**音乐**您可以使用默认保持音乐置于保持状态提供与呼叫队列，或者可以上载.wav、 mp3 或.wma 格式用作您自定义保留音乐音频文件。 
   

### <a name="select-the-call-distribution-method"></a>选择呼叫分发方法

![显示呼叫分发方法选项](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> 串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。 
   
### <a name="select-an-agent-opt-out-option"></a>选择代理退出选项

![显示代理退出复选框](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> 若要访问选择退出选项，代理可以执行以下操作：
 1. 在其桌面 Skype for Business 客户端中打开**选项**。 
 2. 在**呼叫转移**选项卡中，单击**在线编辑设置**链接。
 3. 在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。
 
    > [!NOTE] 
    > 使用 Mac、移动、Lync 2013 客户端的代理，或使用 Skype for Business 2015 服务器托管在本地的混合语音用户，可转到[https://aka.ms/cqsettings](https://aka.ms/cqsettings) 访问退出选项。
   
### <a name="add-call-agents-to-a-call-queue"></a>向呼叫队列添加呼叫代理

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![第一](../images/sfbcallout1.png)<br/><br/>第一
* 拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。 <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > 用户托管在本地不支持使用 Lync Server 2010。           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>设置队列最大大小和最长等待时间。

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![第一](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![第二](../images/sfbcallout2.png)<br/><br/>**当达到的最大呼叫数**当呼叫队列达到其最大大小 （设置使用的**队列中的最大呼叫**设置） 时，您可以选择新的传入呼叫会发生什么情况。
* **断开连接并显示繁忙信号** 呼叫将断开连接。
* **此将呼叫转移到**选择此，您可以在这些选项：
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。 
     
    > [!Note]
    > 用户托管在本地不支持使用 Lync Server 2010。<br/>
     
  * **呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![第三](../images/sfbcallout3.png)<br/><br/>**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。 <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![第四](../images/sfbcallout4.png)<br/><br/>**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：
* **断开连接** 呼叫将断开连接。
* **此将呼叫转移到**选择此，您可以在这些选项：
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。 

    > [!Note]
    > 用户托管在本地不支持使用 Lync Server 2010。<br/>

  * **呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>更改用户的来电显示为呼叫队列的电话号码

通过使用**新建 CallingLineIdentity** cmdlet 创建策略，可将出站呼叫的来电显示更改为呼叫队列，从而保护用户的身份。
  
若要执行此操作，请运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

有关如何在组织中对来电显示设置进行更改的详细信息，可访问 [此处](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[Office 365 中的电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
