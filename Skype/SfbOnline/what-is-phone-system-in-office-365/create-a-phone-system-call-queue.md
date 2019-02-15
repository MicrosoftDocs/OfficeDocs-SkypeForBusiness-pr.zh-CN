---
title: 创建电话系统呼叫队列
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: phans, wasseemh
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
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 53d3eee97ba5fc396b47396b969fef6f2e899df1
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30046735"
---
# <a name="create-a-phone-system-call-queue"></a>创建电话系统呼叫队列

队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。 您可以为组织创建单个或多个呼叫的队列。
  
电话系统呼叫队列可提供：
  
- 组织问候语。
- 在呼叫者保持等待时播放的音乐。
- 重定向的呼叫已启用邮件的通讯组列表和安全组中代理的呼叫。
- 发出呼叫队列最大大小、 超时和呼叫处理选项设置。

当有人呼叫到电话号码的呼叫的队列设置时，它们将听到问候语 （如果任何设置），然后再它们都将在队列中并等待下一个可用呼叫代理。 呼叫者在等待时会听到音乐，系统将按照 *先进先出*  (FIFO) 的方式为呼叫分配呼叫代理。
  
将使用 attendant 的路由模式或串行路由模式分发队列中等待的所有呼叫：
  
- 助理路由队列中的第一个呼叫将同时拨打所有代理。
- 使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。

    > [!NOTE]
    > 不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。

## <a name="step-1---getting-started"></a>第 1 步 - 开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- 企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。 已分配的**电话系统**用户许可证数量影响服务号码可用于呼叫的队列数。 您可以呼叫队列数是取决于您的组织中分配的**电话系统**和**音频会议**的许可证数量。 若要了解有关授权的详细信息转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

    > [!NOTE]
    > 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 通话套餐的详细信息，请参阅 [Office 365 中有哪些通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365) 和 [Office 365 的通话套餐](/microsoftteams/calling-plans-for-office-365)。

    > [!NOTE]
    > 用户托管在本地为呼叫队列代理不支持使用 Lync Server 2010。 
  
- 你可以只分配在 **Skype for Business 管理中心**获取的或从另一个服务提供商转接到电话系统呼叫队列的收费和免费电话服务电话号码。 若要获取并使用免费电话号码，则需要设置通信点数。

    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。 
  
- 当您要分发从电话系统呼叫队列的传入呼叫时，呼叫代理支持这些客户端：

  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）

  - Lync 桌面客户端 2013（32 位和 64 位版本）

  - 支持 Skype for Business Online 的所有 IP 电话型号。 请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)。

  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本） 

  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）

  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）

  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）

  - Microsoft Teams Windows 客户端 （32 和 64 位版本）

  - Microsoft Teams Mac 客户端

  - Microsoft Teams iPhone 应用

  - Microsoft Teams Android 应用

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。 获得收费电话或免费电话服务电话号码后，他们会显示在 **Skype for Business 管理中心** > **语音** > **电话号码**，**号码类型**将列出**服务—免费电话**。 若要获取服务号码，请参阅 [从 Skype for Business 和 Microsoft Teams 获取服务电话号码](getting-service-phone-numbers.md) 或如果您希望进行转移现有服务号码，请参阅  [传输电话号码到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 。
  
> [!NOTE]
> 如果您在美国以外，您无法使用业务管理中心的 Skype 获取服务号码。 转到[管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)而是以了解如何执行从美国的外部。
  
## <a name="step-3---create-a-new-call-queue"></a>第 3 步 - 创建新的呼叫队列

 **使用 Microsoft 团队管理中心**

在**Microsoft 团队管理中心**中，单击![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **旧门户** >  **呼叫路由** > **呼叫队列**，然后单击 **+ 添加新**：
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>设置呼叫队列显示名称、电话号码和域（如有）

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![第一](../images/sfbcallout1.png)<br/>
**名称** 为呼叫队列输入描述性显示名称。此为必填字段，最多可以包含 64 个字符，其中包括空格。<br/> 此名称将显示在传入呼叫的通知中。
***
![第二](../images/sfbcallout2.png)<br/>**电话号码** 为呼叫队列选择收费或免费服务电话号码。 这是可选的。 <br/> 如果没有列出任何号码，则需要首先获取服务号码，然后才能创建此服务队列。 若要获取服务号码，请参阅[业务和 Microsoft 团队的 Skype 获取服务电话号码](getting-service-phone-numbers.md)
***
![第三](../images/sfbcallout3.png)<br/>**域** 如果此字段可用，请选择要使用的 Office 365 域。仅当你拥有多个用于 Office 365 的域时此字段才可用。如果你拥有多个域，必须从列表中选择域名。 <br/> 例如，你可能拥有类似以下名称的域： _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**问候语**是可选设置。 这是呼叫队列号码的呼叫中的人员播放问候语。 <br/> 您可以上载音频文件 （.wav、.mp3 或.wma 格式）。
***
![第二](../images/sfbcallout2.png)<br/>**音乐**您可以使用默认保持音乐置于保持状态提供与呼叫队列，或者可以上载.wav、 mp3 或.wma 格式用作您自定义保留音乐音频文件。

### <a name="select-the-call-distribution-method"></a>选择呼叫分发方法

![显示呼叫分发方法选项](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**呼叫分发方法**呼叫队列分发方法，可以选择**助理**或**串行**。 所有新的和现有呼叫队列将具有默认情况下选中的助理路由。 若要使用串行路由，必须明确在 UI 和 cmdlet 中选择 **串行** 路由选项。 <br/><br/> 当选取串行路由并保存呼叫队列时，来自队列的呼叫将从代理列表的开头开始逐个拨打各位代理。 如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。   

> [!NOTE]
> 串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。 

### <a name="select-an-agent-opt-out-option"></a>选择代理退出选项

![显示代理退出复选框](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![第一](../images/sfbcallout1.png)<br/>**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。  <br/> 启用此选项允许此队列中的所有代理随意开始或停止接收来自此呼叫队列的呼叫。 通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。  <br/><br/> 若要访问选择退出选项，代理可以执行以下操作：
 1. 在其桌面 Skype for Business 客户端中打开**选项**。 
 2. 在**呼叫转移**选项卡中，单击**在线编辑设置**链接。
 3. 在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。

    > [!NOTE] 
    > 使用 Mac、移动、Lync 2013 客户端的代理，或使用 Skype for Business 2015 服务器托管在本地的混合语音用户，可转到[https://aka.ms/cqsettings](https://aka.ms/cqsettings) 访问退出选项。

### <a name="add-call-agents-to-a-call-queue"></a>向呼叫队列添加呼叫代理

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![第一](../images/sfbcallout1.png)<br/><br/>呼叫代理 (200 最大)，可以：
* 拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。 <br/><br/> **注意：** 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其调用规划。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* 拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。 为通讯组列表或安全组添加一位新代理，以便开始接收来自呼叫队列的呼叫，这可能需要 30 分钟的时间。 新建通讯组列表或安全组可能需要长达 48 小时成为可用于呼叫的队列。 新创建的 Office 365 组几乎立即就可使用。 <br/> 

  > [!NOTE] 
  > 用户托管在本地不支持使用 Lync Server 2010。

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>设置队列最大大小和最长等待时间。

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![第一](../images/sfbcallout1.png)<br/><br/>**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。 默认值为 50，但它可以介于 0 到 200.达到此限制时，将设置下的**时达到的最大呼叫数**设置的方式处理呼叫。
***
![第二](../images/sfbcallout2.png)<br/><br/>**当达到的最大呼叫数**当呼叫队列达到其最大大小 （设置使用的**队列中的最大呼叫**设置） 时，您可以选择新的传入呼叫会发生什么情况。
* **断开连接并显示繁忙信号** 呼叫将断开连接。
* **此将呼叫转移到**选择此，您可以在这些选项：
  * **公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用规划。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。 <br/> <br/>若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。 

    > [!Note]
    > 用户托管在本地不支持使用 Lync Server 2010。<br/>

  * **呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。
  * **自动助理**您必须已创建自动助理，但您执行操作后，您可以选择的自动助理。 请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
***
![第三](../images/sfbcallout3.png)<br/><br/>**呼叫在队列中可以等待多长时间** 你还可以决定呼叫在超时和需要重新定向或断开连接前可以在队列中保留的时间。重新定向的目的地取决于" **当呼叫超时时**"中的设置。你可以将此时间设置为 0 到 45 分钟。 <br/><br/> 超时值可以以秒为单位按 15 秒间隔进行设置。 这样，你可以以更细的粒度操作呼叫流。 例如，你可以指定在 30 秒内代理不作应答的所有呼叫转到目录搜索自动助理。 

***
![第四](../images/sfbcallout4.png)<br/><br/>**当呼叫超时时** 当呼叫达到" **呼叫在队列中可以等待多长时间**"中设置的限制时，你可以选择如何处理此呼叫：
* **断开连接** 呼叫将断开连接。
* **此将呼叫转移到**选择此，您可以在这些选项：
  * **公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用计划。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。 </br><br/>  若要了解有关语音邮件所需授权的信息，请参阅[设置电话系统的语音邮件](/microsoftteams/set-up-phone-system-voicemail)。 

    > [!Note]
    > 用户托管在本地不支持使用 Lync Server 2010。<br/>

  * **呼叫队列**您必须已创建另一个呼叫队列，但执行操作后，您可以选择该呼叫的队列。
  * **自动助理**您必须已创建自动助理，但您执行操作后，您可以选择的自动助理。 请参阅[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>更改用户的来电显示为呼叫队列的电话号码

通过使用**新建 CallingLineIdentity** cmdlet 创建策略，可将出站呼叫的来电显示更改为呼叫队列，从而保护用户的身份。
  
若要执行此操作，请运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。 若要执行此操作，请运行：
  
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

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：

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
