---
title: 创建呼叫队列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何为云呼叫队列设置电话系统, 以便为你提供组织问候语、保持的音乐以及将呼叫重定向到通讯组列表和安全组中的呼叫代理。 You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: e32ab12c63f20439d21c9c1829cd4b32bdd34d70
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344682"
---
# <a name="create-a-cloud-call-queue"></a>创建云呼叫队列

云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能, 以及搜索下一个可用的呼叫代理以处理呼叫, 而通话的人员在保持状态时收听音乐。 You can create single or multiple call queues for your organization.
  
云呼叫队列可以提供:
  
- 组织问候语。
- 在呼叫者保持等待时播放的音乐。
- 将呼叫重定向到启用邮件的通讯组列表和安全组中的呼叫代理。
- 为呼叫队列设置最大大小、超时和呼叫处理选项。

当某人通过[资源帐户](manage-resource-accounts.md)拨打与呼叫队列相关联的电话号码时, 他们将首先听到问候语 (如果已设置), 然后将其放入队列, 然后等待下一个可用的呼叫代理。 拨入的人员将在处于等待状态时听到音乐, 并且将在先进*先出*(FIFO) 订单中向呼叫代理提供呼叫。
  
在队列中等待的所有通话都将使用下列方法之一进行分发:
  
- 通过助理路由, 队列中的第一个呼叫将同时拨打所有代理。
- 使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。
- 通过循环复用, 传入呼叫的路由将平衡, 以便每个呼叫代理将从队列中获得相同数量的通话。

    > [!NOTE]
    > 不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

## <a name="step-1---get-started"></a>步骤 1-入门

要开始使用呼叫队列，记住以下几点至关重要：
  
- 通话队列必须具有关联的资源帐户。 有关资源帐户的详细信息, 请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。
- 如果你计划分配直接路由号码, 你需要使用手机系统加载项获取以下许可证并将其分配给\(你的资源帐户 Office 365 企业版 E1、E3 或 E5\)。
- 如果你改为分配 Microsoft 服务号码, 你需要使用手机系统加载项和呼叫计划\(\)获取并将以下许可证分配给你的资源帐户 Office 365 企业版 E1、E3 或 E5。
- 您只需向分配了电话号码的资源帐户授予许可证。 在嵌套的自动助理或呼叫队列中, 如果自动助理或呼叫队列没有与之关联的电话号码, 则无需向其授予许可证。 

> [!NOTE] 
> 只有 Microsoft 团队用户和代理才支持自动助理和呼叫队列的直接路由服务号码。

> [!NOTE] 
> Microsoft 正在致力于应用程序 (如云自动助理和呼叫队列) 的无成本许可模型, 现在您需要使用用户许可模型。

> [!NOTE]
> 若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。 请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 呼叫计划的详细信息, 请参阅[手机系统和通话计划](calling-plan-landing-page.md)和[Office 365 的呼叫计划](calling-plans-for-office-365.md)。

- 您只能分配您在**Microsoft 团队管理中心**或从另一个服务提供商转移到云呼叫队列的收费和免费服务电话号码。 若要获取并使用免费电话号码，则需要设置通信点数。

    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。
  
- 当您从云呼叫队列分配传入呼叫时, 呼叫代理支持这些客户端:

  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）

  - Lync 桌面客户端 2013（32 位和 64 位版本）

  - Microsoft 团队支持的所有 IP 电话模式。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。

  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本）

  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）

  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）

  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）

  - Microsoft Teams Windows 客户端 （32 和 64 位版本）

  - Microsoft Teams Mac 客户端

  - Microsoft Teams iPhone 应用

  - Microsoft Teams Android 应用

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。 获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。 若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外, 则不能使用 Microsoft 团队管理中心获取服务号码。 转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。

如果你还设置自动助理, 你可能只需要将电话号码分配给主自动助理的资源帐户, 然后将呼叫者直接加入呼叫队列。 如果是这种情况, 则需要创建呼叫队列, 然后才能在自动助理中创建选择呼叫队列的选项。
  
## <a name="step-3---create-a-new-call-queue"></a>步骤 3-创建新的呼叫队列

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 每个通话队列都必须具有关联的[资源帐户](manage-resource-accounts.md)。 必须先创建资源帐户, 然后才能将其关联到呼叫队列。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

在**Microsoft 团队管理中心**、**语音** >  **呼叫队列**中, 单击 " **+ 添加新**":

### <a name="set-the-call-queue-display-name-and-resource-account"></a>设置呼叫队列显示名称和资源帐户

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![数字 1](media/sfbcallout1.png)
**名称**输入呼叫队列的描述性显示名称。 此为必填字段，最多可以包含 64 个字符，其中包括空格。

 此名称将显示在传入呼叫的通知中。

* * *

![第二](media/sfbcallout2.png)

**添加帐户**选择资源帐户。 资源帐户可能与呼叫队列的服务收费或免费电话号码相关联, 但是每个通话队列都需要关联的资源帐户。

如果未列出任何列表, 则需要先获取服务号码并将其分配给资源帐户, 如前文所述。 若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)。 如果您希望通话队列具有相关联的电话号码, 请按照在[团队中管理资源帐户](manage-resource-accounts.md)中所述创建资源帐户。

> [!NOTE]
> 如果你希望或需要分配**域**, 你可以通过将其分配给呼叫队列的资源帐户来执行此操作。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![第一](media/sfbcallout1.png)

**问候语**是可选设置。 这是呼叫呼叫队列号码的用户所播放的问候语。

你可以上载音频文件 (.wav、mp3 或 .wma 格式)。

![第二](media/sfbcallout2.png)

**暂停的音乐**你可以使用与呼叫队列一起提供的默认音乐保持通话, 也可以将音频文件上载为 .wav、mp3 或 .wma 格式, 用作保留的自定义音乐。

* * *

### <a name="select-the-call-answering-options"></a>选择呼叫应答选项

![显示呼叫分发方法选项](media/5d249515-d532-4af2-90da-011404028b89.png)

![第一](media/sfbcallout1.png)

您最多可以选择属于指定邮寄列表或组的200呼叫代理。 通话代理必须是:

- 拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。

  > [!NOTE]
  > 若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或有呼叫计划。 请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。

 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。 为通讯组列表或安全组添加的新代理最多可能需要3小时才能开始从呼叫队列接收呼叫。 新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。 新创建的 Office 365 组几乎立即就可使用。

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![第二](media/sfbcallout2.png)

**路由方法**您可以为您的通话队列分发方法选择 "**助理**"、"**串行**" 或 "**循环**"。 所有新的和现有呼叫队列将具有默认情况下选中的助理路由。 使用 "助理路由" 时, 队列中的首次呼叫将同时拨打所有呼叫代理。 获取呼叫的第一个呼叫代理将获取呼叫。

- **助理路由**使队列中的第一次通话同时拨打所有呼叫工程师。 获取呼叫的第一个呼叫代理将获取呼叫。
- **串行路由**传入呼叫将从呼叫代理列表的开头开始, 逐个拨打呼叫代理。 不能在 "呼叫代理程序" 列表中订购代理。 如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。
  > [!NOTE]
  > 串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。
- **循环法**平衡传入呼叫的路由, 以便每个呼叫代理将从队列中获得相同数量的通话。 这在入站销售环境中可能非常可取, 可确保所有呼叫代理中的同等商机。

### <a name="select-an-agent-opt-out-option"></a>选择代理退出选项

![显示代理退出复选框](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![第一](media/sfbcallout1.png)

**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。

如果启用此选项, 将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。 通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。

若要访问选择退出选项，代理可以执行以下操作：

 1. 在其桌面 Skype for Business 客户端中打开**选项**。
 2. 在**呼叫转移**选项卡中，单击**在线编辑设置**链接。
 3. 在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。

    > [!NOTE]
    > 使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 "退出" 选项。

![第 2](media/sfbcallout2.png)
号码**代理警报设置**

这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。

默认设置为30秒, 但最多可设置3分钟。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>设置呼叫溢出和超时处理选项

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![第一](media/sfbcallout1.png)

**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。 默认值为 50, 但范围可以从0到200。 达到此限制后，将按照在后面的" **达到最大呼叫次数时**"设置中指定的方式来处理呼叫。

* * *

![第二](media/sfbcallout2.png)

**达到最大通话次数时**当通话队列达到最大值 (使用 **"队列" 设置中的最大通话**设置) 时, 您可以选择新的传入呼叫发生的情况。

- **断开连接** 呼叫将断开连接。
- **重定向到**选择此项时, 请选择下列操作之一:

  - **公司中的人员**具有**电话系统**许可证并启用企业语音或具有呼叫计划的在线用户。 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作, 请选择**您的公司中的人员**, 并将其呼叫直接转发到语音邮件。

  若要了解语音邮件所需的许可, 请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用程序**选择已创建的通话队列或自动助理的名称。

* * *

![第三](media/sfbcallout3.png)

**呼叫超时: 最长等待时间**您还可以决定呼叫在队列中保留多长时间, 并且需要重定向或断开连接。 重新定向的目的地取决于" **当呼叫超时时**"中的设置。 你可以将此时间设置为 0 到 45 分钟。

超时值可以以秒为单位按 15 秒间隔进行设置。 这样，你可以以更细的粒度操作呼叫流。 例如, 您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。

![第四](media/sfbcallout4.png)

**拨出的时间**当呼叫达到您在 "队列" 设置**中呼叫可以等待的时间**限制时, 您可以选择对此呼叫执行的操作:

- **断开连接** 呼叫将断开连接。
- **将此呼叫重定向到**如果选择此选项, 将使用以下选项:
  - **公司中的人员**具有**电话系统**许可证并启用企业语音或具有通话计划的在线用户。 你可以通过此设置将呼叫者直接转到语音邮件。 若要执行此操作, 请选择**您的公司中的人员**, 并将其呼叫直接转发到语音邮件。

  若要了解语音邮件所需的许可, 请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用程序**选择已创建的通话队列或自动助理的名称。

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>更改用于出站呼叫的用户来电显示 

你可以通过使用**CsCallingLineIdentity** cmdlet 创建策略来将呼叫者的呼叫方 ID 更改为呼叫队列、自动助理或任何服务号码, 从而保护用户的身份。

若要执行此操作, 请运行:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。 若要执行此操作, 请运行:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

有关如何在[组织中使用来电](/microsoftteams/how-can-caller-id-be-used-in-your-organization)显示功能的详细信息, 请了解如何在组织中对呼叫方 id 设置进行更改。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [新-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell, 你可以使用单一的管理点管理 Office 365 和 Microsoft 团队, 这样你有多个任务需要执行这些任务即可。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 团队管理中心, 例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：

  - [通过 Windows PowerShell 管理 Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [为 Windows PowerShell 设置计算机](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
