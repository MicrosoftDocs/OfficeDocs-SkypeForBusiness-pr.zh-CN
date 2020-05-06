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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 了解如何设置 Microsoft 团队的 "云呼叫" 队列的电话系统，这些团队提供问候语、举行音乐、呼叫重定向和其他功能。
ms.openlocfilehash: 8d7001d3e4052eddcfce1d3dfa3da845bce3af66
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44047389"
---
# <a name="create-a-cloud-call-queue"></a>创建云呼叫队列

云呼叫队列可以提供：

- 一条问候语。
- 在呼叫者保持等待时播放的音乐。
- 使用启用邮件的通讯组列表和安全组将呼叫重定向到呼叫代理。
- 设置不同的参数，例如队列最大大小、超时和通话处理选项。
- 面向呼叫者的共享语音邮件为组织留下消息。

您不会直接将电话号码与呼叫队列相关联，而是将电话号码与[资源帐户](manage-resource-accounts.md)相关联。 可通过自动助理上的选择直接拨打或访问呼叫队列。

呼叫者在处于暂停状态时将听到音乐，并且呼叫将首先连接到呼叫代理，*即先出*（FIFO）订单。

通过以下方法之一将队列中的所有调用发送到代理：

- 通过助理路由，队列中的第一个通话将同时响铃所有代理。
- 通过串行路由，队列中的第一次呼叫将每个呼叫代理逐一响铃一次。
- 通过循环复用，传入呼叫的路由是平衡的，以便每个呼叫代理从队列中获得相同数量的通话。

你可以设置呼叫处理选项，如代理选择加入/选择退出、基于状态的路由、呼叫等待时间以及用上述任何方法调用超时选项。

一次仅有一个传入呼叫通知（在队列的头呼叫）转到呼叫代理。 呼叫代理接受呼叫后，队列中的下一个传入呼叫开始拨叫所有代理。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

## <a name="step-1--get-started"></a>步骤 1-入门

要开始使用呼叫队列，记住以下几点至关重要：

- 通话队列必须具有关联的资源帐户。 有关资源帐户的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。
- 将电话号码分配给资源帐户时，您现在可以使用 "免费电话系统[虚拟用户" 许可证](teams-add-on-licensing/virtual-user.md)。 电话系统允许组织级别的电话号码与低成本的自动助理和呼叫队列服务配合使用。

> [!NOTE]
> 只有 Microsoft 团队用户和代理才支持直接路由呼叫队列服务号码。

> [!NOTE]
> 若要将呼叫重定向到您的组织中联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。 请参阅[分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。 To enable them for Enterprise Voice, you can use Windows PowerShell. 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 若要了解有关 Office 365 呼叫计划的详细信息，请参阅[手机系统和通话计划](calling-plan-landing-page.md)和[Office 365 的呼叫计划](calling-plans-for-office-365.md)。

- 您只能将云呼叫队列分配给您在**Microsoft 团队管理中心**或从另一个服务提供商转移的收费电话号码和免费服务电话号码。 免费服务号码需要通讯信用点数。

    > [!NOTE]
    > [!注释] 不能将用户（订阅者）的电话号码分配给呼叫队列 - 只能使用收费或免费服务电话号码。

- 以下客户端支持与云呼叫队列关联的呼叫代理：

  - Skype for Business 桌面客户端2016（32位和64位版本）

  - Lync 桌面客户端2013（32位和64位版本）

  - Microsoft 团队支持的所有 IP 电话模式。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。

  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本）

  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）

  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）

  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）

  - Microsoft 团队 Windows 客户端（32位和64位版本）

  - Microsoft Teams Mac 客户端

  - Microsoft Teams iPhone 应用

  - Microsoft Teams Android 应用

    > [!NOTE]
    > 分配了直接路由号码的呼叫队列将不支持 Skype for business 客户端、Lync 客户端或 Skype for business IP 手机用作代理。

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>步骤 2-获取或转移收费或免费服务电话号码

在创建和设置呼叫队列之前，您需要获取或转移现有收费或免费服务号码。 若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码，请参阅[将电话号码转移到 Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。 获得收费或免费服务电话号码后，他们将显示在**Microsoft 团队管理中心** > 的**语音** > **电话号码**中。 免费电话将列出一**种数字类型**的**服务-免费电话**号码。

> [!NOTE]
> 如果您在美国以外，则不能使用 Microsoft 团队管理中心获取服务号码。 转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。

设置多个自动助理时，通常会将电话号码分配给主自动助理的资源帐户。 与嵌套的自动助理或呼叫队列相关联的资源帐户通常不需要电话号码。 该自动助理可以将呼叫者定向到呼叫队列或嵌套的自动助理，即使他们没有电话号码也是如此。 在这些情况下，你可以在系统中创建所有自动助理和呼叫队列，而无需分配拨号键盘选项，然后在稍后编辑设置。 必须存在呼叫队列或自动助理才能将其设置为菜单选项。

## <a name="step-3--create-a-call-queue"></a>步骤3—创建呼叫队列

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 每个通话队列都必须具有关联的[资源帐户](manage-resource-accounts.md)。 必须先创建资源帐户，然后才能将其关联到呼叫队列。

### <a name="use-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心

在**Microsoft 团队管理中心**、**语音** > **呼叫队列**中，单击 " **+ 添加新**"：

### <a name="set-the-display-name-and-resource-account"></a>设置显示名称和资源帐户

![带有编号标注的新通话队列的屏幕截图](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
**名称**中的标注输入呼叫队列的描述性显示名称。 此名称是必需的，最多可包含64个字符，包括空格。

 此名称显示在传入呼叫的通知中。

* * *

![数字2的图标在前面的屏幕截图](media/teamscallout2.png)
中引用标注**添加帐户**选择资源帐户。 所有通话队列都必须有一个资源帐户。 资源帐户不需要拥有服务收费电话号码或免费电话号码。

如果没有列出任何服务号码，请在创建呼叫队列之前将其分配给资源帐户，如前文所述。 若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)。 有关如何分配电话号码的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。

> [!NOTE]
> 如果你希望或需要分配**域**，你可以将其分配给呼叫队列的资源帐户。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>设置通话保持时播放的问候语和音乐

![带有编号标注的问候和音乐选项的屏幕截图](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**问候语**呼叫呼叫队列号码的用户可以播放的可选问候语。

你可以上载音频文件（.wav、mp3 或 .wma 格式）。

![数字2的图标在上一个屏幕截图](media/teamscallout2.png)
**音乐保留**中引用标注你可以使用随呼叫队列提供的默认音乐保持通话。 你还可以将 .wav、mp3 或 .wma 格式中的音频文件上传到保留时使用的自定义音乐。

* * *

### <a name="select-the-call-answering-options"></a>选择呼叫应答选项

![呼叫应答选项的屏幕截图](media/teams-cq-call-answering-options.png)

![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**调用代理和组**直接添加单个代理，而不将它们添加到组中，请单击 "**添加用户**"。 按希望接收呼叫的顺序放置单个代理。 您最多可以添加20个单独的代理（若要添加20个以上的代理，请将它们放在一个组中）。

调用首先路由到单个代理，然后路由到组中的代理。 

你可以选择多达200个呼叫代理，该代理属于以下任意邮件列表或组：

- Office 365 组
- 安全组
- 通讯组列表

所选呼叫代理必须是以下各项之一：

- 使用电话系统许可证和启用企业语音的联机用户
- 使用呼叫计划的在线用户
- 本地 Skype for Business 服务器用户

  > [!NOTE]
  > 如果您想要将呼叫重定向到您的组织中联机的人员，也可以使用此操作。 这些人必须具有**电话系统**许可证，并且已启用企业语音*或*有呼叫计划。 有关详细信息，请参阅[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)、[分配 Microsoft 团队许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)或适合[您的通话计划？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 若要启用企业语音代理，你可以使用 Windows PowerShell。 例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 具有**电话系统**许可证或添加到 Office 365 组的呼叫计划的用户;启用邮件的通讯组列表;或安全组。 将通讯组列表或安全组中的代理添加为呼叫队列代理时，首次通话最多可能需要3个小时。 新创建的通讯组列表或安全组可能需要长达48小时才能与通话队列一起使用。 新创建的 Microsoft 365 组几乎立即可用。

- 如果你的代理正在使用 Microsoft 团队应用进行呼叫队列呼叫，则他们必须处于 TeamsOnly 模式。

![数字2的图标引用上一个屏幕截图](media/teamscallout2.png)
**路由方法**中的标注，你可以选择 "**助理**"、"**串行**" 或 "**循环" 机制**作为分发方法。 默认情况下，所有新的和现有的通话队列均已选中 "助理路由"。 使用 "助理路由" 时，队列中的第一次呼叫将同时响铃所有呼叫工程师。 获取呼叫的第一个呼叫代理将获取呼叫。

- **助理路由**使队列中的第一次通话同时拨打所有呼叫工程师。 获取呼叫的第一个呼叫代理将获取呼叫。
- **串行路由**传入呼叫将所有呼叫代理从呼叫代理程序列表的开始处拨打一次。 不能在 "呼叫代理程序" 列表中订购代理。 如果代理程序已关闭或未接听呼叫，则呼叫将拨打下一个代理，并且将尝试所有代理，直到它已被获取或超时。
- **循环法**平衡传入呼叫的路由，以便每个呼叫代理从队列中获得相同数量的通话。 这在入站销售环境中可能需要确保所有呼叫代理的同等机遇。

![数字3的图标在上一个屏幕截图](media/teamscallout3.png)
基于状态的路由状态的**基于**状态的路由中引用标注使用呼叫代理的可用性状态来确定是否应将代理包含在所选路由方法的 "呼叫" 路由列表中。 其可用性状态设置为 "**可用**" 的呼叫代理包括在 "呼叫" 传送列表中，并且可以接收呼叫。 其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在其可用性状态更改为 "**可用**" 之前不会收到呼叫。

你可以使用任何路由方法启用基于状态的呼叫路由。

如果某个代理选择退出呼叫，则无论其可用性状态如何设置，它们都不会包含在 "呼叫" 传送列表中。

> [!IMPORTANT]
> 启用基于状态的路由时，"呼叫" 传送列表中不包含使用 Skype for Business 客户端的代理，无论其可用性状态如何。 不在呼叫传送列表中的代理将无法接收呼叫。 如果您有使用 Skype for Business 的工程师，请不要启用基于状态的呼叫路由。

### <a name="select-an-agent-opt-out-option"></a>选择代理选择退出选项

![代理选择退出选项（带有编号标注）的屏幕截图](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![数字1的图标，引用上一个屏幕截图](media/teamscallout1.png)
代理中的标注可以选择不**获取呼叫**，您可以选择允许呼叫队列代理通过启用此选项来选择允许呼叫队列代理取消来自特定队列的呼叫。

如果启用此选项，将允许此队列中的所有代理从该呼叫队列开始或停止接收呼叫。 通过清除此复选框，你可以随时撤消代理选择退出特权，这将导致所有代理自动选择再加入此队列 （所有代理的默认设置）。

若要访问选择退出选项，代理可以：

 1. 在其桌面 Skype for Business 客户端中打开**选项**。
 2. 在**呼叫转移**选项卡中，单击**在线编辑设置**链接。
 3. 在 "用户设置" 页面上，单击 "**呼叫队列**"，然后清除复选框以选择退出队列。

    > [!NOTE]
    > 使用 Skype for Business 桌面之外的应用或终结点的代理可以从 "用户设置" 门户[https://aka.ms/cqsettings](https://aka.ms/cqsettings)访问 "退出" 选项。
    >
    > 如果代理位于 Microsoft 团队桌面客户端，则他们可以使用呼叫设置选择退出。 

![数字2的图标在上一个屏幕截图](media/teamscallout2.png)
中引用标注**Agent 警报设置**

这定义了在串行或循环路由方法移到下一个代理之前通知呼叫的代理的持续时间。

默认设置为30秒，但最多可设置3分钟。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>设置呼叫溢出和超时处理选项

![带有编号标注的溢出处理选项的屏幕截图](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![数字1的图标引用上一个屏幕截图](media/teamscallout1.png)
中的标注**最大通话在队列中**使用此设置可设置可同时在队列中等待的最大通话次数。 默认值为50，但范围可以从0到200。 当达到此限制时，将按照在 "**达到最大通话次数时**" 设置中设置的方式处理呼叫。

* * *

![数字2的图标当呼叫队列达到其最大大小（](media/teamscallout2.png)
使用**队列设置中的最大通话**设置）时，**当达到最大调用数**时，将在上面的屏幕截图中引用标注，您可以选择新的传入呼叫所发生的操作。

- **断开连接**通话断开。
- **重定向到**选择此项时，请选择下列操作之一：

  - **公司中的人员**具有**电话系统**许可证并启用企业语音或具有呼叫计划的在线用户。 您可以对其进行设置，以便呼叫者可以发送到语音邮件。 若要执行此操作，请选择**您的公司中的人员**，并将其呼叫直接转发到语音邮件。

  若要了解语音邮件所需的许可证，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。

* * *

![数字3的图标引用上一个屏幕截图](media/teamscallout3.png)
调用超时中的标注 **：最长等待时间**您还可以确定在队列超时和需要重定向或断开连接的情况下，呼叫可以在队列中保留多长时间。 重定向的位置取决于设置**通话超时**设置的方式。 你可以将此时间设置为 0 到 45 分钟。

超时值可以以秒为单位按 15 秒间隔进行设置。 这样，你可以以更细的粒度操作呼叫流。 例如，您可以指定30秒内代理未接听的任何通话转到目录搜索自动助理。

![数字4的图标](media/teamscallout4.png)
**当**调用达到您在呼叫**可以在队列设置中等待的时间**时，当调用达到所设置的限制时，将在上一个屏幕截图中引用标注，您可以选择对呼叫执行的操作：

- **断开连接**通话断开。
- **将此呼叫重定向到**如果选择此选项，则可以使用以下选项：
  - **公司中的人员**具有**电话系统**许可证并启用企业语音或具有通话计划的在线用户。 若要对其进行设置，以便可以将拨入的人发送到语音邮件，请选择**您公司中的人员**，并将其设置为将呼叫直接转发到语音邮件。

  若要了解语音邮件所需的许可证，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。

  - **语音应用**选择与已创建的通话队列或自动助理相关联的资源帐户的名称。

## <a name="change-caller-id-for-outbound-calls"></a>更改出站呼叫的来电显示

若要保护呼叫代理的身份，请使用**CsCallingLineIdentity** cmdlet 将呼叫者 ID 更改为拨出电话、自动助理或任何服务号码，如下例所示：

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后使用**CallingLineIdentity** cmdlet 将该策略应用于用户，如下例所示： 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

有关详细信息，请参阅[如何在组织中使用呼叫者 ID](/microsoftteams/how-can-caller-id-be-used-in-your-organization)。

## <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

还可以使用 Windows PowerShell 来创建和设置呼叫队列。 下面是用于管理呼叫队列的 cmdlet。

- [新-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>有关 Windows PowerShell 的详细信息

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以通过单个管理点管理 Office 365 和 Microsoft 团队。 当有多个任务需要执行时，它可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- 当您同时为多个用户进行更改时，Windows PowerShell 在速度、简洁性和工作效率方面具有许多优势。 通过以下主题了解这些优势：

  - [通过 Windows PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [为 Windows PowerShell 设置计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
