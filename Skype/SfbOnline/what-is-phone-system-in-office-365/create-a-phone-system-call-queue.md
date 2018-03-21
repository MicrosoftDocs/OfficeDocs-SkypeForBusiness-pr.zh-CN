---
title: "创建电话系统调用队列"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: 363c6d7eefd63d1f89eb5d1420e516894d432b6b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="create-a-phone-system-call-queue"></a>创建电话系统调用队列

队列包含问候某人连接到您的组织，能够自动将呼叫置于保持状态，并搜索下一个可用的呼叫代理处理该调用时人的能力的电话号码时所使用的电话系统调用者调用欣赏音乐暂候状态。 您可以为您的组织创建单个或多个调用队列。
  
电话系统调用队列可以提供：
  
- 组织问候语。
    
- 在呼叫者保持等待时播放的音乐。
    
- 重定向的调用来调用已启用邮件的通讯组和安全组中的代理。
    
- 使调用队列最大大小、 超时值，以及调用处理选项设置。
    
当某人连接到设置电话号码向上与呼叫队列，他们会听到一句问候语第一个 （如果任何设置），然后他们将放入队列中，等待下一个可用的呼叫代理。 呼叫者在等待时会听到音乐，系统将按照 *先进先出*  (FIFO) 的方式为呼叫分配呼叫代理。
  
队列中等待的所有调用将使用助理路由模式或串行路由模式都分发：
  
- 使用助理路由时，队列中的第一个调用将在同一时间环所有代理。
    
- 使用串行路由时，队列中的第一个调用将自动震铃所有调用代理一个一个地。
    
    > [!NOTE]
    > 将不会调用调用代理人员处于**脱机状态**，已将其状态设置为**请勿打扰，**或已退出调用队列。
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
    
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。
    
## <a name="step-1---getting-started"></a>第 1 步 - 开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- 企业 E3 以及**电话系统**许可证或企业 E5 许可证，您的组织必须有 （最低要求）。 分配的**电话系统**用户许可证的数量会影响服务号可用于调用队列的数目。 您可以调用队列的数目是取决于**电话系统**和**音频会议**在您的组织中分配的许可证的数量。 若要了解有关许可、 转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!NOTE]
    > 要重定向调用的人在组织中处于在线状态，他们必须**电话系统**许可证和能够使用企业语音或让 Office 365 调用计划。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 调用计划的详细信息，请参阅[调用中 Office 365 计划是什么？](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)和[Office 365 调用计划](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)。
    
    > [!NOTE]
    > 用户承载内部使用 Lync Server 2010 为调用队列代理不支持。 
  
- 只可以指定收费和免费服务电话号码，陷入**业务管理中心的 Skype**或另一个服务提供商转移到电话系统调用队列。 要获取和使用免费电话服务号码，您需要设置通信贷。
    
    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。 
  
- 当分发从电话系统调用队列的传入呼叫时，呼叫代理支持这些客户端：
    
  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）
    
  - Lync 桌面客户端 2013（32 位和 64 位版本）
    
  - 支持 Skype for Business Online 的所有 IP 电话型号。 请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。
    
  - 业务客户端的 Mac Skype (版本 16.8.196 或更高版本) 
    
  - 业务客户端 android Skype (版本 6.16.0.9 或更高版本)
    
  - iPhone 业务客户端的 Skype (6.16.0 版及更高版本)
    
  - iPad Skype 业务客户端 (6.16.0 版及更高版本)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. 获取的收费或免费电话服务的电话号码后，它们将显示在**业务管理中心的 Skype** > **语音** > **电话号码**和**数字类型**列出将列为**服务-免费**. 若要获得服务号码，看到[Skype 业务和 Microsoft 团队的前服务电话号码](getting-service-phone-numbers.md)或者如果要传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您不在美国境内，不能使用业务管理中心为 Skype 来获得服务号码。 而转[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以查看如何做到从外面的美国。
  
## <a name="step-3---create-a-new-call-queue"></a>第 3 步 - 创建新的呼叫队列

In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>设置呼叫队列显示名称、电话号码和域（如有）

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![1 号](../images/sfbcallout1.png)<br/>
**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。<br/> 此名称将显示在传入呼叫的通知中。
***
![2 号](../images/sfbcallout2.png)<br/>**电话号码** 为呼叫队列选择收费或免费服务电话号码。 这是可选的。 <br/> 如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。 若要获得服务号码，请参阅[获得 Skype 业务和 Microsoft 团队的服务电话号码](getting-service-phone-numbers.md)
***
![数字 3](../images/sfbcallout3.png)<br/>**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。<br/> 例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**问候语**是可选设置。 这是呼叫队列编号为播放的调用中的人的问候语。 <br/> 您可以上载音频文件 （.wav、.mp3 或.wma 格式）。
***
![2 号](../images/sfbcallout2.png)<br/>**音乐上保存**您可以提供呼叫队列中，等待使用默认音乐也可以上载.wav、 mp3 或.wma 用作候您自定义音乐格式的音频文件。 
   

### <a name="select-the-call-distribution-method"></a>选择呼叫分发方法

![显示呼叫分发方法选项](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**调用分发方法**您可以为您呼叫队列的通讯方法选择**助理**或**串行**。 所有新的和现有的呼叫队列将具有助理路由默认选中的。 要使用串行传送，您必须显式选择在 UI 和 cmdlet 的**串行**路由选择选项。 <br/><br/> 当串行路由将选择并调用队列保存时，从队列调用将会响铃代理，逐一从代理列表的起始处开始。 如果代理关闭或不会不拿起电话，呼叫响铃列表上的下一个代理并将尝试所有代理逐个直到它拾取或在队列中等待的时间。  <br/><br/>  **注意：**串行路由将跳过代理处于**脱机状态**，其状态设置为**请勿打扰**，或有从该队列中获取调用的**取消**。  
   
### <a name="select-an-agent-opt-out-option"></a>选择代理选择退出选项

![显示代理退订复选框](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![1 号](../images/sfbcallout1.png)<br/>**代理选择退出选项**您可以选择允许呼叫队列代理选择不采用特定队列中的调用通过选择**代理选择退出选项**。  <br/> 启用该选项，将在此队列中的所有代理启动或停止从在此调用队列接收呼叫。 您可以撤消代理退出特权在任何时候通过清除该复选框，导致代理，让它们自动成为让此队列再次 （所有代理程序的默认设置）。  <br/><br/> 若要访问选择退出选项，工程师可以执行以下操作：
 1. 在其桌面 Skype 业务客户端中打开**选项**。 
 2. **来电转接**选项卡上，单击**编辑设置联机**链接。
 3. 在用户设置页上单击**调用队列**，，然后清除他们要退出任何队列对应的复选框。
   
### <a name="add-call-agents-to-a-call-queue"></a>向呼叫队列添加呼叫代理

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![1 号](../images/sfbcallout1.png)<br/><br/>可以调用代理 (最大 50):
*    在线用户使用**电话系统**许可证并启用企业语音或与调用计划。 <br/><br/> **注意：** 要重定向调用的人在组织中处于联机状态，它们必须拥有**电话系统**许可证和企业语音为启用或具有一个调用计划。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    与联机用户与**电话系统**许可证并调用计划添加到 Office 365 组、 已启用邮件的通讯组列表或安全组。 It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. 新创建的通讯组列表或安全组可能需要 48 小时变为可用于调用队列。 新创建的 Office 365 组会几乎立即可用。 <br/> 

    > [!NOTE] 
    > 用户承载内部使用 Lync Server 2010 中不受支持。           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>设置队列最大大小和最长等待时间。

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![1 号](../images/sfbcallout1.png)<br/><br/>**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。 默认值为 50，但其范围可以从 0 到 200.达到此限制时，将具有设置在**当达到最大重试次数**设置下面的方式处理呼叫。
***
![2 号](../images/sfbcallout2.png)<br/><br/>**当达到最大重试次数**当调用队列达到最大值 （设置使用**调用队列中的最大值**设置） 时，您可以选择新的传入呼叫会发生什么情况。
*    **断开连接并显示繁忙信号** 呼叫将断开连接。
*    **转发到此调用**当您选择此选项时，您将具有下列选项：
     *    **在您的公司的人**在线用户使用**电话系统**许可证和能够使用企业语音或者具有一个调用计划。 你可以通过此设置将呼叫者直接转到语音邮件。 这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。 <br/>
     
        > [!Note]
        > 用户承载内部使用 Lync Server 2010 中不受支持。<br/>
     
     *    **调用队列**您必须已创建了另一个调用队列，但执行操作后，您可以选择该呼叫队列。
     *    **自动助理**您必须已创建的自动助理，但执行操作后，您可以选择该自动助理。 请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
***
![数字 3](../images/sfbcallout3.png)<br/><br/>**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。<br/><br/> 以秒为单位，都可以设置超时值以 15 秒的时间间隔。 这使您可以使用细粒度操作调用流。 例如，您可以指定在 30 秒内由代理不回答任何调用进入目录搜索自动助理。 

***
![数字 4](../images/sfbcallout4.png)<br/><br/>**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：
*    **断开连接** 呼叫将断开连接。
*    **转发到此调用**当您选择此选项时，您将具有下列选项：
     *    **在您的公司的人**在线用户使用**电话系统**许可证和能够使用企业语音或者具有调用计划。 你可以通过此设置将呼叫者直接转到语音邮件。 这样做，请选择**您的公司中的人**并设置此人让其将直接转发至语音邮件的电话。 

        > [!Note]
        > 用户承载内部使用 Lync Server 2010 中不受支持。<br/>

     *    **调用队列**您必须已创建了另一个调用队列，但执行操作后，您可以选择该呼叫队列。
     *    **自动助理**您必须已创建的自动助理，但执行操作后，您可以选择该自动助理。 请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>更改用户的呼叫方 ID，才能调用队列的电话号码

您可以通过更改出站呼叫的呼叫队列及其呼叫方 ID 改为创建使用**New CallingLineIdentity** cmdlet 策略保护用户的标识。
  
若要执行此操作，请运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后将策略应用到用户使用**授予 CallingLineIdentity** cmdlet。 若要执行此操作，请运行：
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以了解有关如何更改您的组织中的呼叫方 ID 设置[此处](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [新 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [一组 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [获得 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [删除 CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[下面是 Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
