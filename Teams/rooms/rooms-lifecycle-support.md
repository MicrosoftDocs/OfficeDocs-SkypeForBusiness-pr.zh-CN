---
title: Microsoft Teams 会议室应用版本支持
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
ms.localizationpriority: medium
description: 了解动态支持Microsoft Teams 会议室生命周期支持，包括动态支持结构及其阶段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e7a82d7643a925d5c997c9d6fe5661a421d47ab
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356420"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 会议室应用版本支持
 
应用Microsoft Teams 会议室通过应用商店每季度Windows更新。 可以在两者之间进行带外更新，以修复紧急问题。 Microsoft Teams会议室应用使用常绿产品生命周期，并且在任何给定时间仅支持应用的当前版本和最后一个版本。 Microsoft Teams会议室应用捆绑了经过修改供Teams桌面应用的特定版本。 桌面Teams每两周更新一次。 详细了解更新[Teams过程](../teams-client-update.md)。 这意味着Teams 会议室当前 1 版应用最多支持六个 Teams 桌面应用更新，因此建议始终将 Teams Room 应用程序更新到最新版本的 Teams 会议室 应用。 

该版本Teams 会议室结构是动态的，具体取决于最新版本的可用性。 当应用程序版本不是最新版本时遇到代码缺陷时，必须安装最新版本，以接收修补程序。

所有版本都列在Microsoft Teams 会议室说明[中](rooms-release-note.md)。

> [!IMPORTANT]
> 安装旧版 Teams 会议室应用程序的新设备时，建议在设置帐户后手动更新应用程序，然后再下载Windows更新。 [](manual-update.md) 这可确保设备上已安装 correbt OS 版本和更新。  

## <a name="windows-10-release-support"></a>Windows 10版本支持

Microsoft Teams 会议室频道服务Windows 10 IoT 企业版下Windows 10 企业版或Semi-Annual SKUS。 不支持Windows 10其他版本：

- Windows 10 企业版LTSC (/长期服务) /LTSC (长期服务) 分支
- Windows 10IoT (物联网) Enterprise LTSB/LTSC 版本
- 任何其他版本的Windows，例如Windows 10 专业版家庭版

Windows 10设备上不会立即提供新功能Microsoft Teams 会议室更新。 在发布信息页上发布的公开发布日期后，有一个最多六个月或更Windows 10[延迟](/windows/release-information/)。 这一次用于验证 Windows 10 应用、设备硬件Microsoft Teams 会议室认证音频视频外围设备的发布兼容性。 验证在活动开发每个主要版本期间开始并继续Windows 10。 需要额外时间来验证所有设备制造商是否都为设备生成了更新的映像，Microsoft Teams和测试这些映像。 在验证期间，Microsoft Teams Room 应用使用 Windows [Update for Business](/windows/deployment/update/waas-manage-updates-wufb)组策略来延迟Windows 10更新。 找到并解决任何兼容性问题后，会通过应用商店中的新应用版本更新组策略Windows块。 在夜间维护Microsoft Teams 会议室运行应用的设备Windows 10更新到相应的版本。 MSI 版本可供想要手动管理更新的客户使用。  

> [!IMPORTANT]
> 在验证期间，Microsoft Teams 会议室设备不应通过任何方式更新到下一Windows 10版本。 这包括覆盖就地的组策略，或者System Center或其他第三方设备管理服务。 其中任何一个都可能会导致应用程序Microsoft Teams问题，或者使设备不可用。  

下表显示了经过验证以支持Windows 10支持的推荐版本Microsoft Teams 会议室。 所有日期均以 ISO 8601 格式列出：YYYY-MM-DD。

|版本  |可用性日期   |Microsoft Teams 会议室支持状态   |Microsoft Teams 会议室最低应用程序版本 | 建议的 OS 版本  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |支持， <br/>推荐|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |已跳过， <br/> 不建议&#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |支持 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |否  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |不支持， <br/>已知兼容性问题&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |否                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支持                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |否                         |&#x2014; |&#x2014; |

&#x2780; Windows 10应用程序兼容性问题，不建议使用版本 2004 Microsoft Teams 会议室版本。 此特定问题Microsoft Teams 会议室重启后，应用程序无法启动。 

&#x2781; Windows 10版本 1809，因为发现应用程序与应用程序Microsoft Teams 会议室问题。 此特定问题Microsoft Teams 会议室重启后，应用程序无法启动。 此问题在版本 1903 Windows 10已解决。  

使用受支持的版本时，Windows 10应用始终会获得最新的应用程序Microsoft Teams 会议室更新。  


## <a name="related-topics"></a>相关主题

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 会议室发行说明](rooms-release-note.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
