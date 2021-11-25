---
title: 管理音频和视频的会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: 了解如何在音频和视频Teams管理会议策略设置。
ms.openlocfilehash: 9cd2a82c87106e8060d168766915e4249b9193a5
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177993"
---
# <a name="meeting-policy-settings-for-audio--video"></a>音频和视频的会议&设置

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

本文介绍特定于音频和视频的会议策略设置。 其中包括以下内容：

- [IP 音频模式](#mode-for-ip-audio)
- [IP 视频模式](#mode-for-ip-video)
- [IP 视频](#ip-video)
- [媒体位率 (Kbs)](#media-bit-rate-kbs)
- [视频筛选器模式](#video-filters-mode)
- [允许自定义背景设置](#allow-custom-background-settings)

### <a name="mode-for-ip-audio"></a>IP 音频模式

这是按用户策略。 此设置控制是否可以在会议和群组通话中打开音频。 下面是此设置的值。

|设置值 |行为  |
|---------|---------|
|**已启用传出和传入音频**    |会议允许传出和传入音频。这是默认设置。 |
|**禁用**     |传出和传入音频在会议中已关闭。     |

如果用户设置为 **"已** 禁用"，该用户仍可以安排和组织会议，但他们不能使用音频。 若要加入会议，他们必须通过 PSTN 公用电话交换网 (电话) 或通过电话拨入会议呼叫并加入会议。 没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入音频**。 在 Teams 移动客户端上，如果禁用此设置，用户必须通过 PSTN 拨入会议。

此设置不适用于 1:1 呼叫。 若要限制 1:1 通话，请配置 Teams [通话策略](teams-calling-policy.md) 并关闭 **“进行私人通话”** 设置。 此设置也不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。

此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。

有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。

### <a name="mode-for-ip-video"></a>IP 视频模式

这是按用户策略。 此设置控制是否可以在会议和群组通话中打开视频。 下面是此设置的值。

|设置值 |行为  |
|---------|---------|
|**已启用传出和传入视频**    | 会议允许传出和传入视频。 这是默认设置。 |
|**禁用**     | 传出和传入视频在会议中已关闭。 在 Teams 移动客户端上，用户无法在会议中分享视频或照片。 <br><br>请注意，如果 **禁用"IP** 音频模式"，则 **"IP** 视频模式"也将保持禁用状态。  |

如果为用户设置为 **禁用**，则该用户无法打开视频或查看其他会议参与者共享的视频。 没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入视频**。

此设置不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。

此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。

> [!NOTE]
> 请记住，此设置控制传出和传入视频， **而 IP 视频设置控制** 传出视频。 若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。

有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。

### <a name="ip-video"></a>IP 视频

这是按组织者和按用户策略的组合。 视频是会议的重要组成部分。 在一些组织中，管理员可能希望对有视频的用户会议进行更多的控制。 此设置控制是否可以在用户主持的会议和用户启动的 1:1 和群组通话中打开视频。 在Teams客户端上，此设置控制用户是否可以在会议中共享照片和视频。

由启用了此策略设置的用户组织的会议，如果与会者也启用了此策略设置，则允许与会者在会议中进行视频共享。 没有指定任何策略的会议参与者 (例如，匿名和联合参与者) 继承会议组织者的策略。

> [!NOTE]
> 请记住，此设置控制传出视频，而 **IP 视频的模式** 设置则控制传出和传入视频。 若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。

| Teams 桌面和 Web 客户端 |Teams 移动客户端  |
|:-------:|:-------:|
|![显示在桌面上通过音频/视频设置加入会议的屏幕截图。](media/meeting-policies-audio-video-settings.png)    |![屏幕截图显示在移动设备上通过音频/视频设置加入会议的画面](media/meeting-policies-mobile-join.png)          |

查看以下示例。

|用户 |会议策略  |IP 视频 |
|---------|---------|---------|
|Daniela   | 全局   | 开       |
|Amanda    | Location1MeetingPolicy        | 关闭      |

由 Daniela 主持的会议允许开启视频。 Daniela 可以加入会议并打开视频。 Amanda 无法打开 Daniela 会议中的视频，因为 Amanda 的策略设置为不允许视频。 Amanda 可以看到其他与会者在会议上分享的视频。

在 Amanda 主持的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。 这意味着 Daniela 不能在 Amanda 的会议上开视频。  

如果 Daniela 给 Amanda 打电话时开着视频，Amanda 可以只用音频接听电话。  电话接通后，Amanda 可以看到 Daniela 的视频，但无法打开视频。 如果 Amanda 给 Daniela 打电话，Daniela 可以用视频和音频接听电话。 通话接通后，Daniela 可以根据需要打开或关闭其视频。

有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪个 IP 视频策略设置优先？

对于用户，视频的最多限制策略设置优先。此处为一些示例。

|IP 视频|IP 视频模式|会议体验|
|---------|---------|---------|
|组织者: **打开**<br><br>参与者: **打开** |参与者: **禁用**        |**IP 视频模式** 设置优先。 分配到此策略的参与者不能开启或查看他人分享的视频。|
|组织者: **打开**<br><br>参与者: **打开** |参与者: **启用传出和传入视频**          |分配到该策略的参与者可以打开或查看他人分享的视频。         |
|组织者: **打开**<br><br>参与者: **关闭** |参与者: **启用传出和传入视频**         |**IP 视频** 设置优先。 参与者只能看到传入视频，无法发送传出视频。         |
|组织者: **打开**<br><br>参与者: **关闭** |参与者: **禁用**         |**IP 视频模式** 设置优先。 参与者无法看到传入或传出的视频。|
|组织者: **关闭**    |       |**IP 视频** 设置优先，因为组织者已关闭此设置。 任何人都不能在分配此策略的用户组织会议中打开视频。         |

### <a name="manage-audiovideo-for-meeting-participants"></a>管理与会者的音频/视频

|如果你想要...  |设置以下策略设置  |
|---------|---------|
|禁用会议参与者的音频和视频  |IP 音频模式: **禁用**<br> IP 视频模式: **禁用**<br>IP 视频：N/A       |
|只为会议参与者启用传入的视频和音频  |IP 音频模式: **启用传出和传入音频**<br> IP 视频模式: **启用传出和传入视频**<br>IP 视频： **关闭**       |
|禁用会议参与者的视频 (参与者仅有音频)|  IP 音频模式: **启用传出和传入音频**<br> IP 视频模式: **禁用**<br>IP 视频：N/A
|为会议参与者启用音频和视频    |IP 音频模式: **启用的传出和传入** (默认)<br> IP 视频模式: **启用传出和传入视频** (默认)<br>IP 视频： **在 (** 上)     |

适用会议组织者政策和用户政策之间最严格的政策。 例如，如果组织者有限制视频的策略，而用户的策略不限制视频，那么会议参与者就会继承会议组织者的策略，在会议中无法访问视频。 这意味着他们只能使用音频加入会议。

> [!NOTE]
> 当用户通过电话启动群组呼叫加入时，不会出现 **使用电话进行音频** 的画面。 这是一个已知的问题，我们正在努力解决。 若要解决这个问题，选择 **其他加入选项** 下的 **电话音频**。  

#### <a name="teams-mobile-clients"></a>Teams 移动设备客户端

对于Teams客户端上的用户，会议期间共享照片和视频的能力也取决于 **IP 视频** 或 **IP 视频模式** 设置。 根据策略设置优先，将无法使用分享视频和照片的功能。 这不会影响屏幕共享，可以使用单独的 [屏幕共享模式](meeting-policies-content-sharing.md#screen-sharing-mode) 设置进行配置。 此外，还可以设置 [Teams 移动性策略](/powershell/module/skype/new-csteamsmobilitypolicy)，防止移动用户通过蜂窝连接使用 IP 视频，这意味着他们必须使用 WiFi 连接。

### <a name="media-bit-rate-kbs"></a>媒体位率 (Kbs)

这是按用户策略。 此设置确定用户通话和会议中基于音频、视频和视频的应用共享传输的媒体比特率。 它适用于通话或会议中用户的上行和下行媒体遍历。 此设置可让你对组织中的带宽管理进行精细控制。 根据用户所需的会议场景，我们建议准备足够的带宽，以保证优质的体验。 最小值为 30Kbps，最大值取决于会议场景。 若要了解有关在 Teams 中举行高质量会议、通话和实时活动的最低推荐带宽的更多信息，请参阅 [“带宽要求”](prepare-network.md#bandwidth-requirements)。

如果没有足够的带宽供会议使用，与会者会看到一条表明网络质量差的消息。

对于需要最高质量视频体验的会议，如 CEO 董事会会议和 Teams 直播活动，我们建议将带宽设置为 10 Mbps。 即使设置了最大体验，当检测到某些网络状况时，Teams 媒体栈也会根据不同的场景，适应低带宽的条件。

## <a name="video-filters-mode"></a>视频筛选器模式

<a name="bkvideofilters"> </a>

这是每用户策略。此设置控制用户是否可以自定义他们在会议中的视频背景。

可以使用管理中心Teams PowerShell 设置此策略。 可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，然后将该策略分配给用户。

若要指定用户是否可以在会议中自定义其视频背景，请在管理中心中设置 **VideoFiltersMode** 参数 (选择视频筛选器Teams设置) 如下所示：

|在 PowerShell 中设置值|在管理中心Teams值 |行为  |
|---------|---------|---------|
|**NoFilters** |**无筛选器**    |用户无法自定义其视频背景。|
|**BlurOnly**     |**仅背景模糊**|用户可以选择模糊其视频背景。 |
|**BlurandDefaultBackgrounds**|**背景模糊和默认图像**     |用户可以选择模糊显示视频背景或选择从默认的图像集作为他们的背景。 |
|**AllFilters**|**所有筛选器**     |用户可以选择模糊显示视频背景、从默认的图像集选择、或上传自定义图像作为他们的背景。 |

> [!NOTE]
> 用户上传的图片不会经过 Teams 的筛选。 当使用 **AllFilters** 设置时，应该制定内部组织政策，以防止用户上传攻击性或不适当的图像，或组织无权用于 Teams 会议背景的图像。

### <a name="allow-custom-background-settings"></a>允许自定义背景设置

可以添加要用于每个租户的自定义背景图像。 此功能允许公司将企业品牌应用到Teams会议。

1. 登录到 Teams 管理中心。

2. 选择 **"会议**  >  **会议策略**  >  **""自定义会议图像"。**

   ![会议策略选择，突出显示"自定义会议图像"按钮。](media/custom-background-image-button.png)

3. 从 **"组织范围****的背景图像"中选择"打开"。**

4. 选择 **"+ 添加图像"。**

5. 在"管理背景"面板中，选择"**添加图像"。**

6. 确保映像满足以下要求：
  
   - 最小大小 360 px
   - 最大大小 2048 px
   - PNG、JPG 或 BMP 的文件类型
   - 最多可以上传 50 个图像

7. 预览已选择的图像，然后选择"关闭 **"。**

8. 查看图像并根据需要添加更多图像。

9. 选择“**保存**”。

与会者将看到他们参加会议时可以使用的一系列背景图像。

> [!NOTE]
> 更改最多可能需要 24 小时才能生效。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](policy-assignment-overview.md)
