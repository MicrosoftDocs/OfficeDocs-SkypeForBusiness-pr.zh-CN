---
title: 版本支持
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解动态支持Microsoft Teams 会议室生命周期支持，包括动态支持结构及其阶段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e22bf9759920a5b4233fab9a6f6169f3a1153f0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117440"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 会议室应用版本支持
 
应用Microsoft Teams 会议室应用每年获取几次更新。 自 GA 发行日期 (起) 12 个月 (支持) 更新。 为 12 个月这 12 个月 (12) 技术支持。 但是，支持结构是动态的，有两个不同的阶段依赖于最新版本的可用性：

- **"服务"和"关键更新"阶段** \-运行最新版本的 Microsoft Teams 会议室 应用时，会收到包含安全和服务更新 *的常规* 更新。

- **仅安全更新阶段** \-当新版 Microsoft Teams 会议室 应用发布时，较旧版本的应用的支持级别会减少，仅针对 12个月生命周期中剩余的 12 (12) 安全更新。

> [!NOTE]
> 最新版本始终位于"服务"和"关键更新"阶段。 遇到需要关键更新的代码缺陷时，还必须安装最新版本，以接收修补程序。 所有其他支持的版本仅有资格接收安全更新。

版本生命周期的 12 (12) 或此后发布的更新超过两个，所有支持将结束。 然后，客户必须更新到支持的版本。

所有版本都列在Microsoft Teams 会议室说明[中](rooms-release-note.md)。

## <a name="windows-10-release-support"></a>Windows 10版本支持

Microsoft Teams 会议室频道服务Windows 10 IoT 企业版下Windows 10 企业版或Semi-Annual SKUS。 不支持Windows 10其他版本：

- Windows 10 企业版LTSC (LTSB) /长期服务渠道 (LTSC) 分支
- Windows 10IoT (物联网) Enterprise LTSB/LTSC 版本
- 其他版本的Windows，例如Windows 10 专业版家庭版

Windows 10设备上不会立即提供或更新Microsoft Teams 会议室更新。 在发布信息页面上发布的公开发布日期之后，有意延迟[Windows 10六](/windows/release-information/)个月。 延迟时间用于验证 Windows 10 应用程序、设备硬件Microsoft Teams 会议室认证音频视频外围设备的发布兼容性。 在主动开发每个主要版本期间，验证开始并继续Windows 10。 需要额外时间来验证所有设备制造商是否都为设备生成了更新的映像，Microsoft Teams和测试这些映像。 在验证期间，Microsoft Teams会议室应用使用 Windows 更新[for Business](/windows/deployment/update/waas-manage-updates-wufb)组策略来延迟Windows 10更新。 找到并解决任何兼容性问题后，通过应用商店中的新应用版本更新组策略，Windows块。 在夜间维护Microsoft Teams 会议室运行应用的设备Windows 10更新到相应的版本。 MSI 版本可供想要手动管理更新的客户使用。  

> [!IMPORTANT]
> 在验证期间，Microsoft Teams 会议室设备不应通过任何方式Windows 10更新到下一版本。 这包括覆盖就地的组策略，或者使用System Center或其他第三方设备管理服务。 其中任何一种都可能导致 Microsoft Teams 应用程序的问题，或者使设备不可用。  

下表显示了经验证支持Windows 10支持的推荐版本Microsoft Teams 会议室。 所有日期均以 ISO 8601 格式列出：YYYY-MM-DD。

|版本  |可用性日期   |Microsoft Teams 会议室支持状态   |Microsoft Teams 会议室最低应用程序版本 | 建议的 OS 版本  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |在验证下， <br/>尚不支持|&#x2014; |19042.572 |
| 2004 |2020-05-27 |已跳过， <br/> 不建议|&#x2014; |19041.264 |
| 1909 |2019-11-12 |支持， <br/>推荐 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |支持  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |不支持， <br/>已知兼容性问题&#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |否                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支持                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |否                         |&#x2014; |&#x2014; |

&#x2780; Windows 10版本 1809，因为发现与 Microsoft Teams 会议室 应用程序兼容。 此特定问题Microsoft Teams 会议室重启后，应用程序无法启动。 此问题在版本 1903 Windows 10已解决。  

&#x2781; Windows 10应用程序兼容性问题，不建议使用版本 2004 Microsoft Teams 会议室版本。 此特定问题Microsoft Teams 会议室重启后，应用程序无法启动。 

使用受支持的版本时，Windows 10应用始终会获得最新的应用程序Microsoft Teams 会议室更新。  

## <a name="related-topics"></a>相关主题

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 会议室发行说明](rooms-release-note.md)

[Microsoft Teams 会议室规划](rooms-plan.md)