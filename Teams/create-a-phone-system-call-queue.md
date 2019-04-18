---
title: 创建呼叫队列
ms.author: jambirk
author: jambirk
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何设置电话系统的云呼叫队列将使您组织的问候语，保持音乐，并将重定向呼叫通讯组列表和安全组中的代理的呼叫。 You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: da178761658460812bc1d0330f3540be43c3e6e6
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914641"
---
# <a name="create-a-cloud-call-queue"></a>创建云呼叫队列

云呼叫队列包括有人呼叫到您的组织、 能够自动将呼叫置于保持状态，并进行搜索的下一个可用呼叫代理处理该呼叫时调用的人员的功能电话号码时使用的问候语收听保持音乐。 You can create single or multiple call queues for your organization.
  
云呼叫队列可提供：
  
- 组织问候语。
- 在呼叫者保持等待时播放的音乐。
- 重定向的呼叫已启用邮件的通讯组列表和安全组中代理的呼叫。
- 发出呼叫队列最大大小、 超时和呼叫处理选项设置。

当有人呼叫到与调用队列通过[资源帐户](manage-resource-accounts.md)相关联的电话号码时，它们将听到问候语 （如果任何设置），然后再它们都将在队列中并等待下一个可用呼叫代理。 保持等待，它们是和呼叫将拨打给*第一个中，先出*（先进先出） 顺序中的呼叫代理时，呼叫的人将听到保持音乐。
  
使用以下方法之一将分发队列中等待的所有呼叫：
  
- 助理路由队列中的第一个呼叫将同时拨打所有代理。
- 使用串行路由时，队列中的第一个呼叫将逐个拨打所有呼叫代理。
- 使用轮循机制的传入呼叫路由平衡使每个呼叫代理将获得相同的呼叫数从队列。

    > [!NOTE]
    > 不会呼叫处于**脱机**状态、已将其状态设置为 **请勿打扰**或已退出呼叫队列的呼叫代理。
  
- 同一时间只会向呼叫代理发送一个传入呼叫通知（队列最前面的呼叫）。
- 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。

> [!NOTE]
> 本文同时适用于 Microsoft 团队和 Skype 业务 online。

## <a name="step-1---get-started"></a>步骤 1-开始

要开始使用呼叫队列，记住以下几点至关重要：
  
- 呼叫队列需要具有关联的资源帐户。 有关资源帐户的详细信息，请参阅[团队中的管理资源帐户](manage-resource-accounts.md)。
- 如果您打算分配一个直接路由号，则需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项\)。
- 如果要改用分配 Microsoft 服务号码，您需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项调用规划\)。
- 您只需使用的电话号码分配给他们许可资源帐户。 在嵌套的自动助理或呼叫队列中，您不需要许可证自动助理的其余部分或呼叫队列，如果没有与其关联的电话号码。 

> [!NOTE] 
> 直接路由服务号码自动助理和呼叫队列此时仅支持的 Microsoft 团队用户和代理。

> [!NOTE] 
> 现在您需要使用用户授权模型，Microsoft 的协作的应用程序云自动助理和呼叫的队列，如适当许可模型中。

> [!NOTE]
> 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。 请参阅[业务许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要了解有关 Office 365 调用计划的详细信息，请参阅[电话系统，调用计划](calling-plan-landing-page.md)和[调用规划 Office 365](calling-plans-for-office-365.md)。

- 您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或从另一个服务提供商转接到云呼叫队列。 若要获取并使用免费电话号码，则需要设置通信点数。

    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。
  
- 当您要分发从云呼叫队列的传入呼叫时，呼叫代理支持这些客户端：

  - Skype for Business 桌面客户端 2016（32 位和 64 位版本）

  - Lync 桌面客户端 2013（32 位和 64 位版本）

  - 支持的 Microsoft 团队的所有 IP 电话型号。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。

  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本）

  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）

  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）

  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）

  - Microsoft Teams Windows 客户端 （32 和 64 位版本）

  - Microsoft Teams Mac 客户端

  - Microsoft Teams iPhone 应用

  - Microsoft Teams Android 应用

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>第 2 步 - 获取或转移收费或免费服务电话号码

在创建和设置呼叫队列之前，您需要获取或转移现有的收费或免费服务号码。 获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话****号码类型**列出将。 若要获取服务号码，请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)或如果您想要传输的现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。 转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。

如果您要设置自动助理，您可能只需要将电话号码分配给主自动助理的资源帐户，并使其直接主叫方到呼叫队列。 如果是这样，需要之前可以创建一个选项中选择呼叫队列的自动助理创建呼叫队列。
  
## <a name="step-3---create-a-new-call-queue"></a>步骤 3-创建新的呼叫队列

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 每个呼叫队列需要具有关联的[资源帐户](manage-resource-accounts.md)。 您必须首先，创建资源帐户，然后将其至呼叫的队列相关联。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

在**Microsoft 团队管理中心**，**语音** >  **呼叫队列**，然后单击 **+ 添加新**：

### <a name="set-the-call-queue-display-name-and-resource-account"></a>设置呼叫的队列显示名称和资源帐户

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![1 号](media/sfbcallout1.png)
**名称**输入呼叫队列的描述性的显示名称。 此为必填字段，最多可以包含 64 个字符，其中包括空格。

 此名称将显示在传入呼叫的通知中。

* * *

![第二](media/sfbcallout2.png)

**添加帐户**选择一个资源帐户。 资源帐户可能也可能不与服务收费电话或免费电话号码呼叫队列，但每个呼叫队列需要关联的资源帐户。

如果没有任何列出，您需要获取服务号码并将其分配给资源帐户才能创建此呼叫队列，如前面所述。 若要获取服务号码，请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。 您需要创建资源帐户中所述[在团队中的管理资源帐户](manage-resource-accounts.md)如果您希望您呼叫的队列具有关联的电话号码。

> [!NOTE]
> 如果您希望或需要分配**域**可以执行，将它分配给呼叫队列的资源帐户。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![第一](media/sfbcallout1.png)

**问候语**是可选设置。 这是呼叫队列号码的呼叫中的人员播放问候语。

您可以上载音频文件 （.wav、.mp3 或.wma 格式）。

![第二](media/sfbcallout2.png)

**音乐**您可以使用默认保持音乐置于保持状态提供与呼叫队列，或者可以上载.wav、 mp3 或.wma 格式用作您自定义保留音乐音频文件。

* * *

### <a name="select-the-call-answering-options"></a>选择呼叫应答选项

![显示呼叫分发方法选项](media/5d249515-d532-4af2-90da-011404028b89.png)

![第一](media/sfbcallout1.png)

您可以选择最多 200 属于指定的邮件列表或组的呼叫代理。 呼叫代理必须是：

- 拥有**电话系统**许可证和启用了企业语音或拥有通话套餐的在线用户。

  > [!NOTE]
  > 要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其调用规划。 请参阅[业务许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。

 要为他们启用企业语音，可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 拥有**电话系统**许可证和通话套餐（已添加到 Office 365 组、已启用邮件的通讯组列表或安全组）的在线用户。 为通讯组列表或安全组添加一位新代理，以便开始接收来自呼叫队列的呼叫，这可能需要 30 分钟的时间。 新建通讯组列表或安全组可能需要长达 48 小时成为可用于呼叫的队列。 新创建的 Office 365 组几乎立即就可使用。

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![第二](media/sfbcallout2.png)

**路由方法**呼叫队列分发方法，可以选择**Attendant**、**串行**、 或**轮循机制**。 所有新的和现有呼叫队列将具有默认情况下选中的助理路由。 使用助理路由时，在队列中的第一个呼叫将拨打的所有呼叫代理在同一时间。 若要选取呼叫的第一个呼叫代理获取呼叫。

- **助理路由**使要同时拨打所有呼叫代理的队列中的第一个呼叫。 若要选取呼叫的第一个呼叫代理获取呼叫。
- **串行路由**使传入呼叫拨打呼叫代理，逐个的开始处的呼叫代理列表。 如果代理挂断或不接听电话，电话将打给列表的下一位代理，并将尝试逐个拨打所有代理，直到有人接听或队列等待超时为止。
  > [!NOTE]
  > 串行路由将跳过处于**脱机**状态、已将其状态设置为 **请勿打扰**或**已选择退出**不从此队列获取呼叫的代理。
- 使每个呼叫代理将获得相同的呼叫数从队列路由的传入呼叫的负载平衡**循环**。 这可能是非常可取中的入站的销售环境，以确保所有呼叫代理之间的等于机会。

### <a name="select-an-agent-opt-out-option"></a>选择代理退出选项

![显示代理退出复选框](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![第一](media/sfbcallout1.png)

**代理退出选项**你可以选择允许呼叫队列代理通过选择**代理退出选项**，不接收来自特定队列的呼叫。
。

启用此选项允许将在此队列中的所有代理启动或停止在此呼叫队列接收呼叫。 通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。

若要访问选择退出选项，代理可以执行以下操作：

 1. 在其桌面 Skype for Business 客户端中打开**选项**。
 2. 在**呼叫转移**选项卡中，单击**在线编辑设置**链接。
 3. 在用户设置页中，单击**呼叫队列**，然后清除他们想要退出的任何队列对应的复选框。

    > [!NOTE]
    > 代理使用的应用程序或终结点以外的其他业务桌面的 Skype 可以访问选项出自愿加入，从用户设置门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)。

![2 号](media/sfbcallout2.png)
**代理警报设置**

这定义的调用序列之前收到通知代理的持续时间或循环路由方法将移至下一个代理。

默认设置为 30 秒，但为最多为 3 分钟。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>设置呼叫溢出和超时处理选项

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![第一](media/sfbcallout1.png)

**队列中的最大呼叫数** 使用此字段来设置同一时间可以在队列中等待的最大呼叫数。 默认值为 50，但它可以介于 0 到 200。 达到此限制后，将按照在后面的" **达到最大呼叫次数时**"设置中指定的方式来处理呼叫。

* * *

![第二](media/sfbcallout2.png)

**当达到的最大呼叫数**当呼叫队列达到其最大大小 （设置使用的**队列中的最大呼叫**设置） 时，您可以选择新的传入呼叫会发生什么情况。

- **断开连接** 呼叫将断开连接。
- **重定向到**当选择此操作时，选择下列选项之一：

  - **公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用规划。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。

  若要了解有关授权所需的语音邮件，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用程序**选择呼叫队列的之一的名称或自动助理已创建。

* * *

![第三](media/sfbcallout3.png)

**呼叫超时： 最长等待时间**您还可以决定呼叫多长时间可以保持在队列中之前超时和需要重定向或断开连接。 重新定向的目的地取决于" **当呼叫超时时**"中的设置。 你可以将此时间设置为 0 到 45 分钟。

超时值可以以秒为单位按 15 秒间隔进行设置。 这样，你可以以更细的粒度操作呼叫流。 例如，您可以指定在 30 秒内不被代理应答任何呼叫转到目录搜索自动助理。

![第四](media/sfbcallout4.png)

**呼叫超时时**当呼叫到达设置的**长呼叫可以在队列中等待**的设置的限制后时，您可以选择此呼叫时会发生什么情况：

- **断开连接** 呼叫将断开连接。
- **重定向到此呼叫**选择此，您可以在这些选项：
  - **公司内的人员**与**电话系统**许可证联机用户和启用了企业语音或其调用计划。 你可以通过此设置将呼叫者直接转到语音邮件。 要执行此操作，选择**您的公司的人员**，并设置此人要使其呼叫直接转接到语音邮件。

  若要了解有关授权所需的语音邮件，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用程序**选择呼叫队列的之一的名称或自动助理已创建。

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>更改用户的出站呼叫的呼叫者 ID 

您可以通过创建策略使用**新建 CsCallingLineIdentity** cmdlet 而更改其呼叫者 ID 的出站呼叫的呼叫队列、 自动助理或任何服务号码保护用户标识。

若要执行此操作，请运行：

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。 若要执行此操作，请运行：
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以获取有关如何对您[如何可以呼叫者 ID 是您组织中使用](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)一文中的组织中的呼叫者 ID 设置进行更改的详细信息。
  
## <a name="want-to-know-more"></a>希望了解更多信息吗？

还可以使用 Windows PowerShell 来创建和设置呼叫队列。
  
### <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

以下是管理呼叫队列时需要使用的 cmdlet。
  
- [新 CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [设置 CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [删除 CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，您可以管理 Office 365 和 Microsoft 团队使用单点管理，可以简化您的日常工作，如果您有多个要执行的任务。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过仅使用在 Microsoft 团队管理中心内，如时要进行设置更改多个用户一次。 通过以下主题了解这些优势：

  - [管理 Office 365 使用 Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [为 Windows PowerShell 设置计算机](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
