---
title: Teams 会议室中语音识别 (语音配置文件) 的租户管理控制
author: cazawideh
ms.author: czawideh
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解Teams会议室中语音识别 (语音配置文件) 的租户管理控制。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6afd8cbf6a62665dbdb4c472df9620d623011452
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817703"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>管理智能扬声器的语音识别技术控制

智能说话人使用语音配置文件信息来识别谁在实时听录中说出了什么。 当Windows会议室的Microsoft Teams 会议室配备智能说话人时，可以在会议期间使用实时听录。 本文介绍租户管理员如何控制用于语音识别的语音分析以生成实时听录。 可以控制组织使用语音识别的程度以及以下功能：

- 在脚本中编辑说话人的姓名。
- 更改脚本中单个话语的扬声器，或在脚本中的所有陈述中更改说话人 (但不更改将来的脚本) 。
- 更改会议中列出的人员的说话人标识。
- 删除在每个脚本上标识为该扬声器的一个或多个陈述的标识。

## <a name="review-intelligent-speaker-requirements"></a>查看智能说话人要求

智能扬声器包括一个特殊的七麦克风数组。 系统使用语音配置文件信息来识别会议室中最多 10 人的声音。

以下项是智能扬声器要求：

- 会议室最多应有 10 人亲自出席。
- 会议室的上传链接至少为 7 Mbps。

支持 Epos、Sennheiser 和 Yealink 智能扬声器。

> [!NOTE]
> 智能扬声器在除印度以外的所有国家和地区均可用，但尚不受支持。 有关当前支持生物识别注册和会议内听录的区域设置列表，请参阅 [支持的区域](#supported-locales) 设置。

## <a name="set-up-an-intelligent-speaker"></a>设置智能扬声器

智能扬声器使用 USB 直接连接到Teams 会议室控制台。

> [!NOTE]
> Yealink 智能扬声器 **必须** 与 Yealink 控制台一起使用。

> [!NOTE]
> 我们不支持连接到 Logitech Surface Pro Microsoft Teams 会议室 的智能扬声器。 有一个已知问题，Teams 会议室无法通过码头识别智能扬声器。

智能扬声器应放置至少 8 英寸 (20 厘米) 远离墙壁和大型物体，如笔记本电脑。 如果智能扬声器 USB 电缆的设置不够长，请使用电缆扩展器。

1. 以管理员身份登录到控制台。
2. 将Teams设备设置设置为与智能扬声器麦克风和扬声器匹配。
   也可以通过 TAC 门户而不是在会议室控制台执行此操作。

   该图显示了如果设备包含数据框，智能扬声器如何连接到设备。

   ![具有扬声器、电源和数据框的智能扬声器设置。一行转到控制台的 USB 端口，另一行进入电源。](../media/intelligent-speakers1.png)

   该图显示了如果设备不包括数据框，智能扬声器如何连接到设备。

   ![具有直接连接到控制台的扬声器的智能扬声器设置。](../media/intelligent-speakers2.png)

> [!Note]
> EPOS 和 Yealink 设备应具有“EPOS”或“Yealink”前缀，并在扬声器名称中包含“UAC2_RENDER”，麦克风名称中包含“UAC2_TEAMS”。 如果在下拉菜单中找不到这些麦克风和扬声器名称，请重启智能扬声器设备。

## <a name="enable-an-intelligent-speaker-user-recognition"></a>启用智能说话人用户识别

语音配置文件数据可在与智能说话人的任何会议中使用。 有关会议设置的信息，请参阅[Teams会议策略](../meetings-policies-recording-and-transcription.md#allow-transcription)和 [PowerShell 会议 cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy)。

当策略设置为区分或非会议受邀者在会议期间走进来时，将创建用户的语音配置文件数据。 语音配置文件数据在会议结束时被关闭。

以下是设置智能扬声器和用户识别所需的策略。

|策略|说明|值和行为|
|-|-|-|
|enrollUserOverride|用于在租户的Teams设置中设置语音配置文件捕获或注册。 |**禁用**<br><ul><li> 从未注册过的用户无法查看、注册或重新注册。<li>注册流的入口点将被隐藏。<li>如果用户选择指向注册页的链接，他们将看到一条消息，指出未为其组织启用此功能。  <li>已注册的用户可以在Teams设置中查看和删除其语音配置文件。 删除语音配置文件后，他们将无法查看、访问或完成注册流。</li></ul><br>**已启用**<br><ul><li> 用户可以查看、访问和完成注册流。<li>入口点将显示在“**识别**”选项卡下的Teams设置页上。</li></ul>|
|roomAttributeUserOverride|控制会议室中基于语音的用户标识。 Teams 会议室帐户需要此设置。| **禁用**<br><ul><li>Teams 会议室设备不会从会议室发送音频流保存带宽。 <li>会议室用户不会被归于或区分，他们的声音签名根本不会被检索或使用。<li>会议室用户未知。</li></ul> <br>**属性**<br><ul><li>会议室用户将根据其注册状态进行归类。<li>注册的用户会在听录中显示其姓名。  <li>未注册的用户将显示为说话人 \<n>。<li>Teams 会议室设备将从会议室发送七个音频流。</ul> <br>**区分**<br> <ul><li>会议室用户将以说话人 1、扬声器 2、....听录中的扬声器 \<n> 。</li><li>无论用户的注册状态如何，其名称都不会显示在听录中。</li><li>Teams 会议室设备将从会议室发送七个音频流。</li></ul>
|AllowTranscription|用户和Teams会议室帐户是必需的。|**True** 和 **False**|
||||

在Teams管理中心，设置 **听录策略**。 默认情况下，设置 **处于关闭状态**。

![突出显示会议策略并选择“允许听录”的管理中心。](../media/allow-transcription1.png)
  
> [!NOTE]
> 分配策略后，最长可能需要 48 小时才能生效。 若要使策略更快生效，必须注销帐户并重新登录。

## <a name="frequently-asked-questions-faq"></a>常见问题 (FAQ)

**语音配置文件数据存储在何处？**

语音配置文件数据存储在包含用户内容Office 365云中。

**什么是保留时间线和策略？**

[数据保留概述](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)中介绍了常规保留策略。 此外，如果用户在 1 年内未被邀请参加与智能说话人的任何会议，则用户的语音配置文件数据将在 1 年后删除。 数据不用于现有员工的任何会议。 如果员工已离开公司，则语音配置文件数据被视为用户内容，并按[数据保留概述](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)中所述的Office 365数据保留策略进行处理。

**是否跨Microsoft 服务使用语音配置文件数据？**

否，语音配置文件数据仅用于用户为其提供许可的目的。 除语音识别方案Teams外，Microsoft 不会使用语音配置文件数据。

例如，Microsoft 不会在以下情况下使用数据：

**我加入另一个组织中的会议时是否使用了语音配置文件数据？**

仅在组织中由用户组织的会议中进行。

**如何导出语音配置文件？**

IT 管理员可以随时导出音频数据。

## <a name="supported-locales"></a>支持的区域设置

所有国家和地区都支持以下注册和会议内听录区域设置。

### <a name="enrollment-locales"></a>注册区域设置

最终用户可以在以下区域设置中注册其语音以进行识别：

|**语言**|**国家/地区**|**区域性 ID**|
|:-----|:-----|:-----|
|英语  <br/> |澳大利亚 <br/> |en-AU  <br/> |
|英语  <br/> |加拿大  <br/> |en-CA <br/> |
|英语  <br/> |印度  <br/> |en-IN  <br/> |
|英语  <br/> |新西兰  <br/> |en-NZ  <br/> |
|英语  <br/> |英国  <br/> |en-GB  <br/> |
|英语  <br/> |美国  <br/> |en-US  <br/> |


### <a name="in-meeting-transcription-locales"></a>会议内听录区域设置

最终用户注册后，可以在会议期间识别其语音，并在将会议设置为以下区域设置之一时在听录中标识他们的声音：

|**语言**|**国家/地区**|**区域性 ID**|
|:-----|:-----|:-----|
|简体中文  <br/> |中国  <br/> |zh-CN  <br/> |
|英语  <br/> |澳大利亚 <br/> |en-AU  <br/> |
|英语  <br/> |加拿大  <br/> |en-CA <br/> |
|英语  <br/> |印度  <br/> |en-IN  <br/> |
|英语  <br/> |新西兰  <br/> |en-NZ  <br/> |
|英语  <br/> |英国  <br/> |en-GB  <br/> |
|英语  <br/> |美国  <br/> |en-US  <br/> |
|法语  <br/> |加拿大  <br/> |fr-CA  <br/> |
|法语  <br/> |法国  <br/> |fr-FR  <br/> |
|德语  <br/> |德国  <br/> |de-DE  <br/> |
|意大利语  <br/> |意大利  <br/> | it-IT <br/> |
|日语  <br/> |日本  <br/> |ja-JP  <br/> |
|韩语  <br/> |韩国  <br/> |ko-KR  <br/> |
|葡萄牙语  <br/> |巴西  <br/> |pt-BR  <br/> |
|西班牙语  <br/> |墨西哥  <br/> |es-MX  <br/> |
|西班牙语  <br/> |西班牙  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>相关主题

[支持文章：使用智能扬声器标识会议室内参与者 ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
