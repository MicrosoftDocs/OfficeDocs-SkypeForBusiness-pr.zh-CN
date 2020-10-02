---
title: 版本支持
ms.author: v-lanac
author: lanachin
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
description: 了解 Microsoft 团队聊天室的生命周期支持，包括动态支持结构及其阶段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd4640df6b4512b5f5b4707a1423c78ae6deea49
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336980"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft 团队聊天室应用版本支持
 
Microsoft 团队聊天室应用每年更新几次。 每个更新均支持 12 (12) 个月，其常规可用性 (GA) 发布日期。 为整个 12 (12) 个月提供技术支持。 但是，支持结构是动态的，具有两个不同的阶段，它们依赖于最新版本的可用性：

- **服务和关键更新阶段** \- 当你运行最新版本的 Microsoft 团队聊天室应用时，你将收到包含 *安全和服务* 更新的定期更新。

- **仅安全更新阶段** \- 当新版本的 Microsoft 团队聊天室应用发布时，较早版本的应用的支持级别将仅适用于 12 (12) 月生命周期的其余部分的 *安全更新* 。

> [!NOTE]
> 最新版本始终位于 "服务" 和 "关键更新" 阶段。 如果遇到可保证关键更新的代码缺陷，还必须安装最新版本才能接收修补程序。 所有其他支持的版本仅有资格接收安全更新。

所有支持将在某版本的 12 (12) 个月生命周期后终止，或者自那时起发布了两个以上的更新。 然后，客户必须更新到受支持的版本。

所有版本均在 [Microsoft 团队聊天室发行说明](rooms-release-note.md)中列出。

## <a name="windows-10-release-support"></a>Windows 10 版本支持

Microsoft 团队聊天室需要 Windows 10 IoT Enterprise 或 Windows 10 企业版 Sku 在半年度频道服务选项下。 不支持以下其他 Windows 10 版本：

- Windows 10 企业长期服务分支 (LTSB) /长期服务通道 (LTSC) 版本
- Windows 10 Internet (IoT) Enterprise LTSB/LTSC 版本
- 任何其他 Windows 版本（如 Windows 10 专业版或家庭版）

Microsoft 团队聊天室设备上不会立即提供或更新 Windows 10 功能更新。 在 [Windows 10 发布信息](https://docs.microsoft.com/windows/release-information/) 页面上发布的常规可用日期后的六个月内的有意延迟。 延迟时间用于验证 Microsoft 团队聊天室应用程序、设备硬件和经过认证的音频视频外设的 Windows 10 发布兼容性。 在 Windows 10 的每个主要版本的活动开发期间，验证开始和继续。 需要额外的时间来验证所有设备制造商是否已为其设备生成了更新的图像，以及 Microsoft 团队验证并测试这些图像。 在验证周期内，Microsoft 团队聊天室应用使用  [Windows 更新 For Business 组策略](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 延迟 windows 10 功能更新。 找到并解决任何兼容性问题后，将通过 Windows 应用商店中的新应用版本更新组策略来提升该块。 运行 Microsoft 团队聊天室应用的设备会在夜间维护重启期间自动更新到相应的 Windows 10 版本。 MSI 版本可供希望手动管理更新的客户使用。  

> [!IMPORTANT]
> 在验证周期内，Microsoft 团队会议室设备 **不** 应通过任何方式更新到下一版本的 Windows 10。 这包括替代组策略，或使用 System Center 或其他第三方设备管理服务。 任何这些都可能导致 Microsoft 团队聊天室应用程序出现问题，或者可能导致设备无法使用。  

下表显示了受支持的 Windows 10 版本和支持的 Windows 10 版本，这些版本经过验证以支持 Microsoft 团队聊天室。 所有日期均以 ISO 8601 格式列出： YYYY MM。

|版本  |可用性日期   |Microsoft 团队会议室支持状态   |Microsoft 团队会议室最小应用程序版本 | 推荐的操作系统内部版本  |
|:---  |:---       |:---                                  |:---     |:---     |
| 2004 |2020-05-27 |在 "验证" 下， <br/>不推荐|&#x2014; |19041.264 |
| 1909 |2019-11-12 |能 <br/>推荐 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |支持  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |不支持， <br/>已知兼容性问题 &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |否                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支持                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |否                         |&#x2014; |&#x2014; |

由于在 Microsoft 团队聊天室应用程序中发现兼容性问题，因此建议不要 &#x2780; Windows 10 版本1809。 此特定问题导致在夜间重启后 Microsoft 团队聊天室应用程序无法启动。 此问题已在 Windows 10 版本1903中解决。  

由于在 Microsoft 团队聊天室应用程序中发现兼容性问题，因此建议不要 &#x2781; Windows 10 版本2004。 此特定问题导致在夜间重启后 Microsoft 团队聊天室应用程序无法启动。 

使用受支持的 Windows 10 版本时，你将始终获取适用于 Microsoft 团队聊天室应用的最新应用程序更新。  

## <a name="related-topics"></a>相关主题

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 团队聊天室发行说明](rooms-release-note.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
