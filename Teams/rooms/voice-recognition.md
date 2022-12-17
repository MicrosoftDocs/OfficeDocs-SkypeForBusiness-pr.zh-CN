---
title: Teams 会议室中语音识别 (语音配置文件) 的租户管理控制
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解 Teams 会议室中语音识别 (语音配置文件) 的租户管理控制。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: 478e739be2787eb2758a2070a441f68c7da727ba
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438300"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>管理智能扬声器的语音识别技术控件

智能扬声器使用语音配置文件信息来识别谁在实时听录中说了什么。 当 Windows 会议室上的Microsoft Teams 会议室配备智能扬声器时，可以在会议期间使用实时听录。 本文介绍租户管理员如何控制用于语音识别生成实时听录的语音分析。 可以控制组织在多大程度上使用语音识别和以下功能：

- 在脚本中编辑说话人的姓名。
- 更改脚本中单个话语的说话人，或者更改脚本 (但不更改未来脚本) 的所有话语中的说话人。
- 更改会议中列出的人员的说话人标识。
- 删除每个脚本上标识为该说话人的一个或多个话语的标识。

## <a name="review-intelligent-speaker-requirements"></a>查看智能扬声器要求

智能扬声器包括一个特殊的七麦克风阵列。 系统使用语音配置文件信息来识别会议室中最多 10 人的声音。

以下项是智能扬声器要求：

- 会议室最多应有 10 人亲自出席。
- 会议室的上传链接至少为 7 Mbps。

支持 Epos、Sennheiser 和 Yealink 智能扬声器。

> [!NOTE]
> 智能扬声器在所有国家/地区都可用。 有关生物识别注册和会议内听录当前支持的区域设置列表，请参阅 [支持](#supported-locales) 的区域设置。

## <a name="set-up-an-intelligent-speaker"></a>设置智能扬声器

智能扬声器使用 USB 直接连接到Teams 会议室控制台。

> [!NOTE]
> Yealink 智能扬声器 **必须与** Yealink 控制台一起使用。

> [!NOTE]
> 我们不支持连接到 Logitech Surface Pro Microsoft Teams 会议室的智能扬声器。 存在一个已知问题，即Teams 会议室无法通过扩展坞识别智能扬声器。

智能扬声器应放置至少 8 英寸 (20 厘米，) 远离墙壁和大型物体，如笔记本电脑。 如果智能扬声器 USB 电缆不够长，适合你的设置，请使用电缆扩展器。

1. 以管理员身份登录到控制台。
2. 设置 Teams 设备设置以匹配智能扬声器麦克风和扬声器。
   还可以通过 TAC 门户（而不是会议室控制台）执行此操作。

   此图显示如果设备包含数据框，智能扬声器如何连接到设备。

   ![带有扬声器、电源和数据盒的智能扬声器设置。一条线路连接到主机的 USB 端口，另一条线路通电。](../media/intelligent-speakers1.png)

   此图显示了如果设备不包含数据框，智能扬声器如何连接到设备。

   ![智能扬声器设置，扬声器直接连接到控制台。](../media/intelligent-speakers2.png)

> [!NOTE]
> EPOS 和 Yealink 设备应具有“EPOS”或“Yealink”前缀，并在扬声器名称中包含“UAC2_RENDER”，麦克风名称中包含“UAC2_TEAMS”。 如果在下拉菜单中找不到这些麦克风和扬声器名称，请重启智能扬声器设备。

## <a name="enable-an-intelligent-speaker-user-recognition"></a>启用智能说话人用户识别

语音配置文件数据可用于任何与智能扬声器的会议。 有关 [会议](../meetings-policies-recording-and-transcription.md#transcription) 设置的信息，请参阅 Teams 会议策略和 [PowerShell 会议 cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy) 。

当策略设置为区分或非会议被邀请者在会议期间走进时，将创建用户的语音配置文件数据。 会议结束时将消除语音配置文件数据。

以下是设置智能扬声器和用户识别所需的策略。

|策略|说明|值和行为|
|-|-|-|
|enrollUserOverride|用于在租户的 Teams 设置中设置语音配置文件捕获或注册。 |**禁用**<br><ul><li> 从未注册过的用户无法查看、注册或重新注册。<li>注册流的入口点将被隐藏。<li>如果用户选择注册页面的链接，他们将看到一条消息，指出其组织未启用此功能。  <li>已注册的用户可在 Teams 设置中查看和删除其语音配置文件。 删除语音配置文件后，将无法查看、访问或完成注册流。</li></ul><br>**已启用**<br><ul><li> 用户可以查看、访问和完成注册流。<li>入口点将显示在 Teams 设置页上的“ **识别** ”选项卡下。</li></ul>|
|roomAttributeUserOverride|控制会议室中基于语音的用户标识。 Teams 会议室帐户需要此设置。| **禁用**<br><ul><li>Teams 会议室设备不会从会议室发送音频流节省带宽。 <li>不会对会议室用户进行属性化或区分，并且根本不会检索或使用其语音签名。<li>会议室用户未知。</li></ul> <br>**属性**<br><ul><li>将根据用户注册状态对会议室用户进行属性化。<li>已注册的用户将在听录中显示其姓名。  <li>未注册的用户显示为说话人 \<n>。<li>Teams 会议室设备将从会议室发送七个音频流。</ul> <br>**区分**<br> <ul><li>会议室用户将被区分为说话人 1、扬声器 2、...。听录中的扬声器 \<n> 。</li><li>无论用户的注册状态如何，其名称都不会显示在听录中。</li><li>Teams 会议室设备将从会议室发送七个音频流。</li></ul>
|AllowTranscription|用户和 Teams 会议室帐户是必需的。|**True** 和 **False**|
||||

在 Teams 管理中心中，设置 **听录** 策略。 默认情况下，设置为 **“关闭** ”。

![管理中心，其中突出显示了会议策略，并选择了“允许听录”。](../media/allow-transcription1.png)
  
> [!NOTE]
> 分配策略后，最长可能需要 48 小时才能生效。 若要使策略早日生效，帐户必须注销并重新登录。

## <a name="frequently-asked-questions-faq"></a>常见问题 (FAQ)

**语音配置文件数据存储在哪里？**

语音配置文件数据存储在包含用户内容的Office 365云中。

**什么是保留时间线和策略？**

[数据保留概述](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)中介绍了常规保留策略。 此外，如果用户在该 1 年内未受邀参加任何具有智能扬声器的会议，则用户语音个人资料数据将在 1 年后删除。 数据不会在现有员工的任何会议中使用。 如果员工已离开公司，则语音配置文件数据被视为用户内容，并且根据数据[保留概述中所述Office 365数据保留](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)策略被视为用户内容。

**是否跨Microsoft服务使用语音配置文件数据？**

否，语音配置文件数据仅用于用户已提供同意的目的。 Microsoft不会使用语音配置文件数据，除非在 Teams 语音识别方案中。

例如，Microsoft在以下情况下不会使用数据：

**当我加入其他组织中的会议时，是否使用我的语音个人资料数据？**

不能仅在由组织中的用户组织的会议中。

**如何导出语音配置文件？**

IT 管理员可以随时导出音频数据。

## <a name="supported-locales"></a>支持的区域设置

所有国家和地区都支持以下注册和会议中听录区域设置。

### <a name="enrollment-locales"></a>注册区域设置

最终用户可以在以下区域设置中注册其语音进行识别：

|**语言**|**国家/地区**|**区域性 ID**|
|:-----|:-----|:-----|
|阿拉伯语  <br/> |沙特阿拉伯 <br/> |ar-SA  <br/> |
|中文  <br/> |中国 <br/> |zh-CN  <br/> |
|中文  <br/> |台湾 <br/> |zh-TW  <br/> |
|丹麦语  <br/> |丹麦 <br/> |da-DK  <br/> |
|荷兰语  <br/> |荷兰 <br/> |nl-NL  <br/> |
|英语  <br/> |澳大利亚 <br/> |en-AU  <br/> |
|英语  <br/> |加拿大  <br/> |en-CA <br/> |
|英语  <br/> |印度  <br/> |en-IN  <br/> |
|英语  <br/> |新西兰  <br/> |en-NZ  <br/> |
|英语  <br/> |英国  <br/> |en-GB  <br/> |
|英语  <br/> |美国  <br/> |en-US  <br/> |
|芬兰语  <br/> |芬兰  <br/> |fi-FI  <br/> |
|法语  <br/> |加拿大 <br/> |fr-CA  <br/> |
|法语  <br/> |法国 <br/> |fr-FR  <br/> |
|意大利语  <br/> |意大利 <br/> |it-IT  <br/> |
|日语  <br/> |日本 <br/> |ja-JP  <br/> |
|挪威语  <br/> |挪威 <br/> |nb-NO  <br/> |
|波兰语  <br/> |波兰 <br/> |pl-PL  <br/> |
|葡萄牙语      <br/> |巴西 <br/> |pt-BR  <br/> |
|俄语  <br/> |俄罗斯 <br/> |ru-RU  <br/> |
|瑞典语  <br/> |瑞典 <br/> |sv-SE  <br/> |
|西班牙语  <br/> |墨西哥  <br/> |es-MX  <br/> |
|西班牙语  <br/> |西班牙  <br/> |es-ES  <br/> |

### <a name="in-meeting-transcription-locales"></a>会议内听录区域设置

最终用户注册后，可以在会议期间识别他们的语音，并在会议设置为以下区域设置之一时在听录中标识他们的声音：

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

[支持文章：使用智能扬声器识别会议室内参与者](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
