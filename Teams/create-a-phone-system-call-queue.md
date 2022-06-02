---
title: 在Microsoft Teams中创建呼叫队列
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
- Phone System - seo-marvel-apr2020
description: 了解如何在Microsoft Teams中为大型组织设置呼叫队列，这些组织提供问候消息、保持音乐、呼叫重定向和其他功能。
ms.openlocfilehash: 7678d132b8711ea828bf643201df5501323ab77e
ms.sourcegitcommit: 18a26d07a335184dbcda71908452e82a6ddc3158
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840984"
---
# <a name="create-a-call-queue"></a>创建呼叫队列

呼叫队列提供一种将呼叫者路由到组织中可帮助处理特定问题或问题的人员的方法。 呼叫一次分发给队列 (称为 *代理*) 的人员。 

> [!TIP]
> 本文适用于大型组织。 如果你的组织是小型企业，请改为阅读 [“创建呼叫队列 - 小型企业教程](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) ”。

呼叫队列提供：

- 问候语。

- 当人们在队列中等待等待时音乐。

- 调用路由 - *在第一个 In，First Out* (FIFO) 顺序 - 代理。

- 处理队列溢出和超时的选项。

请务必阅读[Teams自动助理和呼叫队列的计划](plan-auto-attendant-call-queue.md)，并遵循[入门步骤](plan-auto-attendant-call-queue.md#getting-started)，然后再按照本文中的过程操作。

**有关详细信息，请参阅下面的 [呼叫队列功能兼容性](#call-queue-feature-compatibility) 矩阵。**

## <a name="video-demonstration"></a>视频演示

此视频演示如何在Teams中创建呼叫队列的基本示例。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>创建呼叫队列

若要设置呼叫队列，请在Teams管理中心展开 **“语音**”，单击 **“呼叫队列**”，然后单击 **“添加**”。

键入呼叫队列的名称。

## <a name="resource-accounts"></a>资源帐户

![资源帐户设置的屏幕截图。](media/call-queue-name-language.png)

单击 **“添加帐户**”，搜索要用于此呼叫队列的资源帐户，单击 **“添加**”，然后单击 **“添加**”。  (代理在收到传入呼叫时将看到资源帐户名称。) 

有关详细信息，请参阅[管理Teams资源帐户](manage-resource-accounts.md)。

## <a name="dynamic-caller-id"></a>动态调用方 ID

![调用 ID 设置的屏幕截图。](media/call-queue-assign-calling-id.png)

**适用于Teams频道/协作呼叫桌面用户和Teams具有标准呼叫队列的移动客户端用户**

可以通过指定一个或多个具有电话号码的资源帐户为代理分配出站呼叫者 ID 号码。 代理可以选择要用于每个出站呼叫的出站调用者 ID 号。

单击 **“添加**”，搜索要允许代理在进行出站呼叫时用于调用方 ID 的资源帐户，单击 **“添加**”，然后单击 **“添加**”。

**标准呼叫队列**

对于Teams桌面用户和标准呼叫队列，请考虑将呼叫队列成员的呼叫者 ID 直接设置为呼叫队列的服务号或适当的自动助理。 有关详细信息，请参阅[Microsoft Teams中的“管理调用方 ID”策略](caller-id-policies.md)。

> [!NOTE]
> 用于调用 ID 目的的资源帐户必须具有Microsoft Teams 电话系统虚拟用户许可证，并分配了下列选项之一：
>
> - 呼叫计划许可证和分配的电话号码
> - 分配的运营商连接电话号码
> - 使用直接路由) 时，在线语音路由策略 (电话号码分配是可选的


## <a name="language"></a>语言

![语言设置的屏幕截图。](media/call-queue-language.png)

选择 [支持的语言](create-a-phone-system-call-queue-languages.md)。 如果) 启用系统生成的语音提示和语音邮件听录 (，则将使用此语言。

## <a name="greetings-and-music-on-hold-in-queue"></a>队列中保留的问候语和音乐

![队列设置中保留的问候语和音乐的屏幕截图。](media/call-queue-greetings-music.png)

指定在呼叫者到达队列时是否要向他们打招呼。 必须上传包含要播放的问候语的 MP3、WAV 或 WMA 文件。 上传的录制不得大于 5 MB。

Teams在呼叫者在队列中处于保留状态时为其提供默认音乐。 Teams呼叫队列中提供的默认音乐不含组织支付的任何版税。 如果要播放特定的音频文件，请选择 **“播放音频文件** ”并上传 MP3、WAV 或 WMA 文件。

> [!NOTE]
> 你负责独立清理和保护将任何音乐或音频文件与你的Microsoft Teams服务结合使用的所有必要权利和权限，这些权利和权限可能包括任何音乐、声音效果、音频、品牌、名称以及音频文件中所有相关权利持有者（可能包括艺术家、演员）中的其他权利， 表演者、音乐家、词曲作者、作曲家、唱片公司、音乐出版商、工会、公会、权利协会、集体管理组织以及拥有、控制或许可音乐版权、音效、音频和其他知识产权的任何其他各方。

## <a name="call-agents"></a>呼叫代理

查看 [将代理添加到呼叫队列的先决条件](plan-auto-attendant-call-queue.md#prerequisites)。

![呼叫队列的用户和组设置的屏幕截图。](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams通道

可以通过Teams通道添加多达 200 个代理。 必须是团队成员、创建者或频道所有者才能向队列添加通道。

如果要 [使用Teams通道管理队列](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)，请选择 **“选择团队**”选项，然后单击 **“添加频道**”。 搜索要使用的团队，选择该团队，然后单击 **“添加**”。 选择要使用的通道 (仅支持标准通道) 并单击“ **应用**”。 

对呼叫队列使用Teams通道时，支持以下客户端： 

  - Microsoft Teams Windows客户端
  - Microsoft Teams Mac 客户端

> [!NOTE]
> 如果使用此选项，调用队列可能需要长达 24 小时才能完全正常运行。

##### <a name="users-and-groups"></a>用户和组

可以通过组单独添加最多 20 个代理，最多可添加 200 个代理。

如果要将单个用户或组添加到队列，请选择 **“选择用户和组** ”选项。 

若要将用户添加到队列，请单击 **“添加用户**”，搜索用户，单击 **“添加**”，然后单击 **“添加**”。

若要将组添加到队列，请单击 **“添加组**”，搜索组，单击 **“添加**”，然后单击 **“添加**”。 可以使用通讯组列表、安全组和Microsoft 365组或Microsoft Teams团队。

> [!NOTE]
> 添加到组的新用户可能需要长达 8 小时才能到达其第一个呼叫。

## <a name="call-routing"></a>呼叫路由

![会议模式和路由方法设置的屏幕截图。](media/call-queue-conference-mode-routing-method.png)

在代理接受呼叫后，**会议模式** 可显著减少调用方连接到代理所需的时间。 若要使会议模式正常工作，呼叫队列中的代理必须使用以下客户端之一：

  - Microsoft Teams桌面客户端、Android应用或iOS应用的最新版本
  - Microsoft Teams 电话版本 1449/1.0.94.2020051601 或更高版本
  
代理的Teams帐户必须设置为仅限Teams模式。 不符合要求的代理不包括在呼叫路由列表中。 如果代理都使用兼容的客户端，建议为呼叫队列启用会议模式。

> [!NOTE]
> 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
>
> 如果Teams用户需要使用呼叫队列来咨询/转移呼叫，则需要会议模式。

> [!TIP]
> 建议设置“将 **会议模式** 设置为 **打开** ”。

**路由方法** 确定代理从队列接收呼叫的顺序。 从以下选项中进行选择：

- **助理路由** 同时将队列中的所有代理都响铃。 第一个接听呼叫的呼叫代理获取呼叫。

- **串行路由** 按照呼叫代理列表中指定的顺序逐个调 **用代理** 。 如果代理关闭或未接听呼叫，则调用将拨打下一个代理。 这会重复，直到接听呼叫或超时。

- **轮循机制** 平衡传入调用的路由，以便每个调用代理从队列中获取相同数量的调用。 在入站销售环境中，可能需要使用此路由方法来保证所有调用代理之间的机会均等。

- **最长的空闲** 路由每次调用已空闲时间最长的代理。 如果代理的状态可用，则代理被视为空闲状态。 在将状态更改为“可用”之前，其状态不可用的代理将无法接收呼叫。 

> [!TIP]
> 建议设置将 **路由方法** 设置为 **轮循机制** 或 **最长空闲** 状态。

> [!NOTE]
> 如果代理上启用了 [合规性录制](teams-recording-policy.md) ，则不支持 **会议模式** 和 **助理路由** 的组合。 如果需要使用 **会议模式**，请选择 **串行路由**、 **轮循机制** 或 **“最长空闲”** 作为 **路由方法**。 如果需要使用 **助理路由**，请将 **会议模式** 设置为 **“关闭**”。
> 
> 使用 **最长空闲** 状态时，当队列中的呼叫少于可用代理时，只有前两个最长的空闲代理会显示来自队列的调用。
> 
> 使用 **“最长空闲** 时间”时，有时代理在不可用后不久收到来自队列的呼叫，或者在出现可用后从队列接收呼叫的短暂延迟。
> 
> 对代理的呼叫队列调用演示可能与基于位置的路由限制冲突。 在这种情况下，代理将收到调用 toast，但无法接听呼叫。 此条件将继续，直到另一个代理可用于接听呼叫、调用方挂起或呼叫队列超时条件发生。  


![路由、选择退出和警报时间设置的屏幕截图。](media/call-queue-presence-agents-time.png)

**基于状态的路由** 使用调用代理的可用性状态来确定是否应将代理包含在所选路由方法的呼叫路由列表中。 可用性状态设置为 **“可用”** 的呼叫代理包含在呼叫路由列表中，可以接收呼叫。 其可用性状态设置为任何其他状态的代理将从呼叫路由列表中排除，并且在可用性状态更改回 **“可用**”之前不会接收呼叫。 

可以使用任何路由方法启用基于状态的调用路由。

如果代理选择不接听呼叫，则无论其可用性状态设置为何种，它们都不会包含在呼叫路由列表中。 

> [!NOTE]
> 选择 **“最长空闲时间** ”作为路由方法时，需要并自动启用基于状态的路由，即使基于状态的路由切换将 **关闭** 并灰显。
>
> 如果未启用基于状态的路由，并且队列中有多个调用，系统会同时向代理显示这些调用，而不考虑代理的状态。 这将导致多个给代理的呼叫通知，特别是当某些代理未响应向其发出的初始调用时。
>
> 使用 **基于状态的路由** 时，有时代理在不可用后不久收到来自队列的呼叫，或在可用后接收来自队列的呼叫的短暂延迟。
> 
> 启用基于状态的路由时，使用Skype for Business客户端的代理不会包含在呼叫路由列表中。 如果代理使用Skype for Business，请勿启用基于状态的呼叫路由。

> [!TIP]
> 建议将 **基于状态的路由** 设置为 **“打开** ”。

**代理警报时间** 指定在队列将呼叫重定向到下一个代理之前代理的电话将响多长时间。

> [!TIP]
> 建议将 **代理警报时间** 设置为 **20 秒** 。

> [!NOTE]
> [调用超时处理](#call-timeout-handling)设置优先于代理警报时间。 如果已达到为呼叫超时处理配置的最大队列时间，即使尚未达到代理警报时间限制，调用也将从代理 () 中拉回。

## <a name="call-overflow-handling"></a>呼叫溢出处理

![呼叫溢出设置的屏幕截图。](media/call-queue-overflow-handling.png)

**队列中的最大调用** 指定可在任何给定时间在队列中等待的最大调用数。 默认值为 50，但范围为 0 到 200。 达到此限制后，将按照 **达到最大呼叫数** 的设置指定处理调用。

可以选择断开呼叫连接或将其重定向到任何呼叫路由目标。 例如，你可能让调用方为队列中的代理保留语音邮件。 有关外部传输，请参阅 [先决条件](plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码传输 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 。

> [!NOTE]
> 如果最大呼叫数设置为 0，则问候消息将不会播放。
>
> 重定向到共享语音邮件时，请确保为Microsoft 365 管理中心中的团队/组启用 **此组织外部的人员电子邮件**。


## <a name="call-timeout-handling"></a>呼叫超时处理

![呼叫超时设置的屏幕截图。](media/call-queue-timeout-handling.png)

**呼叫超时：最大等待时间** 指定调用在重定向或断开连接之前在队列中可以保持的最大时间。 可以指定从 0 秒到 45 分钟的值。

可以选择断开呼叫连接或将其重定向到某个呼叫路由目标。 例如，你可能让调用方为队列中的代理保留语音邮件。 有关外部传输，请参阅 [先决条件](plan-auto-attendant-call-queue.md#prerequisites) 和 [外部电话号码传输 - 数字格式的技术详细信息](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 。

> [!NOTE]
> 重定向到共享语音邮件时，请确保为Microsoft 365 管理中心中的团队/组启用 **此组织外部的人员电子邮件**。

选择呼叫超时选项后，单击“ **保存**”。

## <a name="summary-of-recommended-call-queue-settings"></a>建议的呼叫队列设置摘要

建议使用以下设置：

- **会议模式** 为 **“打开”**
- **路由方法** 到 **轮循机制** 或 **最长空闲**
- **基于状态的路由** 到 **On**
- **代理警报时间：** 至 **20 秒**


## <a name="call-queue-feature-compatibility"></a>呼叫队列功能兼容性

|功能                          |Teams桌面<sup>1</sup> |Teams移动<sup>2</sup> |Lync |IP 电话 | 标准呼叫队列 |基于通道的呼叫队列 | 注释 |
|:--------------------------------|:------------------------:|:-----------------------:|:---:|:--------:|:--------------------:|:------------------------:|:-------------|
|**代理路由方法**        |                          |                         |     |          |                      |                          |              |
|`Attendant Routing`              |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*Default*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y                        |N    |Y         |Y                     |Y                         |*建议* |
|`Round Robin`                    |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*建议* |
|`Serial`                         |Y                         |Y                        |Y    |Y         |Y<sup>4</sup>         |Y<sup>4</sup>             |              |
|**代理路由选项**        |                          |                         |     |          |                      |                          |              |
|`Presence Based Routing`<sup>3</sup>|Y                        |Y                        |N    |Y         |Y                     |Y                         |*建议* |
|`Agents can Opt-out`               |Y                         |Y                        |Y<sup>7</sup>|Y<sup>7</sup>|Y          |Y                         |*Default*     |
|**传输模式**               |                          |                         |     |          |                      |                          |              |
|`Conference Mode`<sup>5</sup>    |Y                         |Y                        |N    |Y<sup>6</sup>|Y                  |Y                         |*建议* |
|`Transfer Mode`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*Default*              |
|**协作呼叫**        |                          |                         |     |          |                      |                          |              |
|`Channel Based Queues`             |Y                         |N                        |否    |否         |n/a                   |Y<sup>8</sup>             |              |
|**动态调用方 ID**            |                          |                         |     |          |                      |                          |              |
|`Standard call queue`            |N                         |Y                        |N    |否         |是                     |n/a                       |              |
|`Channel based call queue`       |Y                         |n/a                      |n/a  |n/a       |n/a                   |Y                         |              |
|**PSTN 连接方法**    |                          |                         |     |          |                      |                          |请参阅注释 10   |
|`Calling Plans`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |              |
|`Direct Routing`                 |Y                         |Y                        |N    |否         |Y                     |Y                         |              |
|`Operator Connect`               |Y                         |Y                        |     |          |Y                     |Y                         |              |
|**杂项**    |                          |                         |     |          |                      |                          |请参阅注释 10   |
|`Call toast shows Resource Account Name` |Y<sup>9</sup>       |Y                        |Y    |          |Y                     |Y                         |              |

注意：
1. Microsoft Teams Windows客户端，Microsoft Teams Mac 客户端，Microsoft Teams虚拟化桌面基础结构，Microsoft Teams Web 客户端。
2. Microsoft Teams iPhone应用，Microsoft Teams Android应用。
3. 为代理路由方法选择“最长空闲时间”将自动启用基于状态的路由。
4. 只能在将单个用户添加为标准呼叫队列的一部分时设置顺序。 使用分发列表或Teams通道时，顺序将按字母顺序排列。
5. 如果电话呼叫从启用了基于位置的路由的直接路由网关路由到队列，则不支持会议模式。
6. 仅Microsoft Teams手机。
7. 通过“用户设置门户”页面https://aka.ms/vmsettings
8. 仅支持公共频道。
9. 排除Teams Web 客户端。
10. 自动助理和呼叫队列无法在 PSTN 连接方法之间传输调用。


## <a name="supported-clients"></a>支持的客户端

呼叫队列中的呼叫代理支持以下客户端：

  - Skype for Business桌面客户端 2016 (32 位和 64 位版本) 
  - Lync 桌面客户端 2013 (32 位和 64 位版本) 
  - Microsoft Teams支持的所有 IP 手机型号。 请参阅[获取适用于 Skype for Business Online 的电话](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac Skype for Business 客户端（版本 16.8.196 及更高版本）
  - Android Skype for Business 客户端（版本 6.16.0.9 及更高版本）
  - iPhone Skype for Business 客户端（版本 6.16.0 及更高版本）
  - iPad Skype for Business 客户端（版本 6.16.0 及更高版本）
  - Microsoft Teams Windows客户端 (32 位和 64 位版本) 
  - Microsoft Teams Mac 客户端
  - 虚拟[化桌面基础](/microsoftteams/teams-for-vdi)结构 (Windows虚拟桌面、Citrix 和 VMware) 上的Microsoft Teams
  - Microsoft Teams iPhone 应用
  - Microsoft Teams Android 应用

    > [!NOTE]
    > 分配有直接路由号码的呼叫队列不支持Skype for Business客户端、Lync 客户端或Skype for Business IP Phone 作为代理。 仅Teams共[存模式支持Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings)客户端。

## <a name="call-queue-cmdlets"></a>呼叫队列 cmdlet

Windows PowerShell允许你通过命令行以批处理或编程方式创建和管理呼叫队列。

使用以下 cmdlet 可以管理呼叫队列：

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

还需要以下附加 cmdlet 来管理将用于呼叫队列的用户、资源帐户、Microsoft Teams 电话许可证、电话号码、音频文件和支持的语言：

用户/Teams

- 用户
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams： 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

资源帐户：

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

虚拟Teams 电话许可证：

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

电话数字分配：

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

音频文件

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

支持语言列表

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

有关使用 PowerShell 创建呼叫队列的分步指南，请参阅使用 [PowerShell cmdlet 创建呼叫队列](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>呼叫队列诊断工具

如果你是管理员，则可以使用以下诊断工具来验证呼叫队列是否能够接收呼叫：

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。 

   > [!div class="nextstepaction"]
   > [运行测试：Teams呼叫队列](https://aka.ms/TeamsCallQueueDiag)

2. 在“运行诊断”窗格中，在 **“用户名”或“电子邮件** ”字段中输入资源帐户，然后选择 **“运行测试**”。

3. 测试将返回处理任何租户、策略和资源帐户配置的最佳后续步骤，以验证呼叫队列是否能够接收呼叫。

## <a name="related-topics"></a>相关主题

[下面是Microsoft Teams 电话](here-s-what-you-get-with-phone-system.md)

[获取服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
