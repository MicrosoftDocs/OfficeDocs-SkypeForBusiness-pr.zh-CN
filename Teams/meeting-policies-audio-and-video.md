---
title: 管理音频和视频的会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理音频和视频的会议策略设置。
ms.openlocfilehash: 3f7a557555d6846c4ada792ceb05da43ce91ed0f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598715"
---
# <a name="meeting-policy-settings-for-audio--video"></a>音频和视频的会议&设置

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

本文介绍特定于音频和视频的会议策略设置。 其中包括以下内容：

- [允许听录](#allow-transcription)
- [允许云录制](#allow-cloud-recording)
- [IP 音频模式](#mode-for-ip-audio) 
- [IP 视频模式](#mode-for-ip-video) 
- [允许 IP 视频](#allow-ip-video)
- [媒体比特率 (Kbs) ](#media-bit-rate-kbs)
- [视频剪辑器模式](#video-filters-mode)

### <a name="allow-transcription"></a>允许听录

这是按组织者和按用户策略的组合。 此设置控制在播放会议录制期间字幕和听录功能是否可用。 如果将其关闭 **，则播放** 会议录制期间，"搜索"和"抄送"选项将不可用。 开始录制的人需要启用此设置，以便录制还包括听录。

请注意，录制的会议的听录功能目前仅支持在 Teams 中将语言设置为英语和在会议中说出英语的用户。

### <a name="allow-cloud-recording"></a>允许云录制

这是按组织者和按用户策略的组合。 此设置控制是否可以录制此用户的会议。 如果为参与者打开策略设置，并且他们是同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以启动录制。

组织外部的用户（例如联合用户和匿名用户）无法开始录制。 来宾用户无法启动或停止录制。

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

让我们看看以下示例。

|用户 |会议策略  |允许云录制 |
|---------|---------|---------|
|Daniela | 全局   | 关 |
|Amanda | Location1MeetingPolicy | 开|
|John (外部)  | 不适用 | 不适用|

无法录制由 Daniela 组织的会议，已启用策略设置的 Amanda 无法录制 Daniela 组织的会议。 可以录制由 Amanda 组织的会议，但禁用了策略设置的 Daniela 和外部用户的 John 无法录制 Amanda 组织的会议。

若要详细了解云会议录制，请参阅 [Teams 云会议录制](cloud-recording.md)。

### <a name="mode-for-ip-audio"></a>IP 音频模式

这是按用户的策略。 此设置控制是否可以在会议和群组通话中打开音频。 下面是此设置的值。

|设置值 |行为  |
|---------|---------|
|**已启用传出和传入音频**    |会议允许传出和传入音频。 这是默认设置。 |
|**已禁用**     |传出和传入音频在会议中已关闭。     |

如果用户设置为 **"已** 禁用"，该用户仍可以安排和组织会议，但他们不能使用音频。 若要加入会议，他们必须通过 PSTN 公用电话交换网 (电话) 或通过电话拨入会议呼叫并加入。 未分配任何策略的会议参与者，例如， (参与者默认已启用) "传出和 **传入音频** "。 在 Teams 移动客户端上，如果禁用此设置，用户必须通过 PSTN 拨入会议。

此设置不适用于 1：1 调用。 若要限制 1 对 1 通话，请配置 [Teams](teams-calling-policy.md) 通话策略并关闭" **进行私人通话"** 设置。 此设置也不适用于会议室设备，例如 Surface Hub 和 Microsoft Teams 会议室设备。

此设置尚不可用于 Microsoft 365 政府社区云 (GCC) 、GCC High 或国防部 (DoD) 环境。

有关详细信息，请参阅 [管理会议参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。

### <a name="mode-for-ip-video"></a>IP 视频模式

这是按用户的策略。 此设置控制是否可以在会议和群组通话中打开视频。 下面是此设置的值。

|设置值 |行为  |
|---------|---------|
|**已启用传出和传入视频**    | 会议允许传出和传入视频。 这是默认设置。 |
|**已禁用**     | 传出和传入视频在会议中已关闭。 在 Teams 移动客户端上，用户无法共享会议中的视频或照片。 <br><br>请注意，如果 **禁用"IP** 音频模式"，则 **"IP** 视频模式"也将保持禁用状态。  |

如果用户设置为 **"** 已禁用"，该用户无法打开视频或查看其他会议参与者共享的视频。 未为会议参与者分配任何策略，例如， (参与者默认已启用) "传出和 **传入视频** "。

此设置不适用于会议室设备，例如 Surface Hub 和 Microsoft Teams 会议室设备。 

此设置尚不可用于 Microsoft 365 政府社区云 (GCC) 、GCC High 或国防部 (DoD) 环境。

> [!NOTE]
> 请记住，此设置控制传出和传入视频，而" **允许 IP** 视频"设置控制传出视频。 有关详细信息，请参阅哪个 [IP 视频策略设置优先？](#which-ip-video-policy-setting-takes-precedence) 和管理会议 [参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。

有关详细信息，请参阅 [管理会议参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。

### <a name="allow-ip-video"></a>允许 IP 视频

这是按组织者和按用户策略的组合。 视频是会议的一个重要组成部分。 在某些组织中，管理员可能希望对哪些用户的会议具有视频进行更多控制。 此设置控制是否可以在由用户主持的会议以及由用户启动的 1：1 和群组通话中打开视频。 在 Teams 移动客户端上，此设置控制用户是否可以在会议中共享照片和视频。 

由启用了此策略设置的用户组织的会议，如果参与者还启用了策略设置，则允许会议参与者在会议中共享视频。 未分配任何策略的会议参与者， (匿名和联合参与者) 会议组织者的策略。

> [!NOTE]
> 请记住，此设置控制传出视频，而 IP **视频** 模式设置控制传出和传入视频。 有关详细信息，请参阅哪个 [IP 视频策略设置优先？](#which-ip-video-policy-setting-takes-precedence) 和管理会议 [参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。

| Teams 桌面和 Web 客户端 |Teams 移动客户端  |
|:-------:|:-------:|
|![显示桌面音频/视频设置的会议加入的屏幕截图](media/meeting-policies-audio-video-settings.png)    |![显示移动设备上音频/视频设置的会议加入屏幕截图](media/meeting-policies-mobile-join.png)          |

让我们看看以下示例。

|用户 |会议策略  |允许 IP 视频 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda    | Location1MeetingPolicy        | 关      |

Daniela 主持的会议允许打开视频。 Daniela 可以加入会议并打开视频。 Amanda 无法打开 Daniela 会议中的视频，因为 Amanda 的策略设置为不允许视频。 Amanda 可以在会议中查看其他参与者共享的视频。

在 Amanda 主持的会议中，无论分配给他们的视频策略如何，均无法打开视频。 这意味着 Daniela 无法打开 Amanda 会议中的视频。  

如果 Daniela 通过视频呼叫 Amanda，Amanda 只能使用音频应答呼叫。  当呼叫已连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。 如果 Amanda 呼叫 Daniela，Daniela 可以使用视频和音频应答呼叫。 当呼叫接通后，Daniela 可根据需要打开或关闭其视频。

有关详细信息，请参阅 [管理会议参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪个 IP 视频策略设置优先？

对于用户，视频的最严格策略设置优先。 下面是一些示例。

|允许 IP 视频|IP 视频模式|会议体验|
|---------|---------|---------|
|组织者： **打开**<br><br>参与者： **打开** |参与者： **已禁用**        |IP **视频设置的模式** 优先。 分配了此策略的参与者无法打开或查看其他人共享的视频。|
|组织者： **打开**<br><br>参与者： **打开** |参与者： **已启用传出和传入视频**          |分配了此策略的参与者可以打开或查看其他人共享的视频。         |
|组织者： **打开**<br><br>参与者： **关闭** |参与者： **已启用传出和传入视频**         |" **允许 IP 视频** "设置优先。 参与者只能看到传入的视频，并且无法发送传出视频。         |
|组织者： **打开**<br><br>参与者： **关闭** |参与者： **已禁用**         |IP **视频设置的模式** 优先。 参与者无法看到传入或传出视频。|
|组织者： **关闭**    |       |" **允许 IP** 视频"设置优先，因为组织者已关闭此设置。 在分配有此策略的用户组织的会议中，没有人可以打开视频。         |

### <a name="manage-audiovideo-for-meeting-participants"></a>管理会议参与者的音频/视频

|如果你希望...  |设置以下策略设置  |
|---------|---------|
|为会议参与者禁用音频和视频  |IP 音频模式： **已禁用**<br> IP 视频模式： **已禁用**<br>允许 IP 视频：N/A       |
|仅为会议中的参与者启用传入视频和音频  |IP 音频模式： **已启用传出和传入音频**<br> IP 视频模式： **已启用传出和传入视频**<br>允许 IP 视频： **关闭**       |
|禁用会议中参与者的视频， (参与者只有音频) |  IP 音频模式： **启用传出和传入音频**<br> IP 视频模式： **已禁用**<br>允许 IP 视频：N/A        
|为会议参与者启用音频和视频    |IP 音频模式： **已启用传出和传入音频 (** 默认) <br> IP 视频模式： **已启用传出和传入视频 (** 默认) <br>允许 IP 视频： **在 (** 上)     |

会议组织者的策略与用户策略之间的限制性最强的策略适用。 例如，如果组织者的策略限制视频，而用户的策略不限制视频，则会议参与者将继承会议组织者的策略，并且无法访问会议中的视频。 这意味着他们只能使用音频加入会议。

> [!NOTE]
> 当用户开始群组通话以通过电话加入时，不显示"将 **电话用于** 音频"屏幕。 这是一个已知问题，我们正在努力解决此问题。 若要解决此问题，请在"其他加入选项 **"下选择**"**电话音频"。**  

#### <a name="teams-mobile-clients"></a>Teams 移动客户端

对于 Teams 移动客户端上的用户，会议期间共享照片和视频的能力也取决于"允许 **IP** 视频"或 **"IP 视频模式"设置** 。 共享视频和照片的能力将不可用，具体取决于哪个策略设置优先。 这不会影响屏幕共享，这是使用单独的屏幕共享模式 [设置配置的](meeting-policies-content-sharing.md#screen-sharing-mode) 。 此外，可以设置 [Teams 移动](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 策略，防止移动用户通过手机网络连接使用 IP 视频，这意味着他们必须使用 WiFi 连接。

### <a name="media-bit-rate-kbs"></a>媒体比特率 (Kbs) 

这是按用户的策略。 此设置确定用户通话和会议中基于音频、视频和视频的应用共享传输的媒体比特率。 它同时应用于呼叫或会议中的用户的上行和下行媒体遍历。 使用此设置可以精细控制组织中带宽的管理。 根据用户所需的会议方案，我们建议有足够的带宽，以便获得优质体验。 最小值为 30 Kbps，最大值取决于会议方案。 若要详细了解在 Teams 中为优质会议、通话和实时事件建议的最小带宽，请参阅 [带宽要求](prepare-network.md#bandwidth-requirements)。

如果会议带宽不足，参与者将看到一条消息，指示网络质量不佳。

对于需要最高质量的视频体验的会议，例如 CEO 董事会会议和 Teams 实时活动，建议将带宽设置为 10 Mbps。 即使设置了最大体验，当检测到某些网络条件时，Teams 媒体堆栈也适应低带宽条件，具体取决于方案。

## <a name="video-filters-mode"></a>视频筛选器模式

<a name="bkvideofilters"> </a>

这是按用户的策略。 此设置控制用户是否可以在会议中自定义其视频背景。

目前，只能使用 PowerShell 设置此策略。 可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略，然后将该策略分配给用户。

若要指定用户是否可以在会议中自定义其视频背景，请设置 **VideoFiltersMode** 参数，如下所示：

|在 PowerShell 中设置值 |行为  |
|---------|---------|
|**NoFilters**     |用户无法自定义其视频背景。|
|**BlurOnly**     |用户可以选择模糊其视频背景。 |
|**BlurandDefaultBackgrounds**     |用户可以选择模糊其视频背景，或者从默认图像集选择用作背景。 |
|**AllFilters**     |使用 可以选择模糊其视频背景、从默认图像集选择或上传自定义图像以用作背景。 |

> [!NOTE]
> Teams 不会筛选用户上传的图像。 使用 **AllFilters** 设置时，应制定内部组织策略，防止用户上传冒犯性或不适宜的图像，或组织没有权限用于 Teams 会议背景的图像。






## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)

