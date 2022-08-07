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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 了解Microsoft Teams 会议室的生命周期支持，包括动态支持结构及其阶段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8814ee9190ff6036345b4aa4607191d3486a369e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268207"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 会议室应用版本支持
 
Microsoft Teams 会议室应用通过 Windows 应用商店获取更新。 Microsoft Teams 会议室应用使用常绿产品生命周期，并且在任何给定时间仅支持应用的当前版本和下一个最新版本。 Microsoft Teams 会议室应用捆绑特定版本的 Teams 桌面应用，该应用经过修改以供会议室使用。 Teams 桌面应用每两周更新一次。 详细了解 [Teams 更新过程](../teams-client-update.md)。 这意味着Teams 会议室应用 current-1 版本最多可以是 6 个 Teams 桌面应用更新，因此建议始终将 Teams 会议室应用程序更新到最新版本的 Teams 会议室 应用。 

Teams 会议室的支持结构是动态的，取决于最新版本的可用性。 当在不是最新版本的应用程序中遇到代码缺陷时，必须安装最新版本才能接收修补程序。

所有版本都列在[Microsoft Teams 会议室发行说明](rooms-release-note.md)中。

> [!IMPORTANT]
> 安装带有旧版 Teams 会议室应用程序的新设备时，建议在设置帐户后 [手动更新](manual-update.md) 应用程序，然后再下载任何 Windows 更新。 这可确保在设备上安装正确的 OS 版本和 Windows 更新。  

## <a name="windows-10-release-support"></a>Windows 10发布支持

Microsoft Teams 会议室需要Semi-Annual通道服务选项下的Windows 10 IoT 企业版或Windows 10 企业版 SKU。 不支持其他Windows 10版本：

- Windows 10 企业版长期服务分支 (LTSB) /长期服务通道 (LTSC) 版本
- Windows 10物联网 (IoT) 企业 LTSB/ LTSC 版本
- 任何其他版本的 Windows，如 Windows 10 专业版 版或主页版

Microsoft Teams 会议室设备上不会立即提供新的Windows 10功能更新。 在Windows 10[发布信息](/windows/release-information/)页上发布的正式发布日期之后，将故意延迟 6 个月或更长的时间。 这一次用于验证Microsoft Teams 会议室应用、设备硬件和经过认证的音频视频外围设备的Windows 10发布兼容性。 在积极开发每个主要版本的Windows 10期间，验证将开始并继续进行。 需要额外的时间来验证所有设备制造商是否为其设备生成了更新的映像，以及 Microsoft 认证和测试这些映像。 在验证期间，Microsoft Teams 会议室应用使用 [Windows 更新 for Business 组策略](/windows/deployment/update/waas-manage-updates-wufb)来延迟Windows 10功能更新。 找到并解决任何兼容性问题后，将通过通过 Windows 应用商店中的新应用版本更新组策略来解除该块。 运行Microsoft Teams 会议室应用的设备会在夜间维护重启期间自动更新到适当的Windows 10版本。 MSI 版本可供需要手动管理更新的客户使用。  

> [!IMPORTANT]
> 在验证期间，**不应** 通过任何方式将Microsoft Teams 会议室设备更新到下一版本的Windows 10。 这包括替代就地的组策略，或使用 System Center 或其他第三方设备管理服务。 其中任何一项都可能导致 Microsoft Teams 会议室应用出现问题，或使设备无法使用。  

下表显示了经过验证以支持Microsoft Teams 会议室的建议和支持的Windows 10版本。 所有日期都以 ISO 8601 格式列出：YYYY-MM-DD。

| 版本 | 可用性日期 | Microsoft Teams 会议室支持状态                    | Microsoft Teams 会议室最低应用程序版本 | 建议的 OS 生成 |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | 支持<br>推荐                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | 否                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | 支持                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | 跳 <br/> 不建议&#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | 支持                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | 否                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | 不支持， <br/>已知兼容性问题&#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | 否                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | 不支持                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | 否                                           | &#x2014;                                          | &#x2014;             |

由于与Microsoft Teams 会议室应用程序的兼容性问题，不建议&#x2780; Windows 10版本 2004。 此特定问题导致Microsoft Teams 会议室应用程序在夜间重新启动后无法启动。 

由于与Microsoft Teams 会议室应用程序的兼容性问题，不建议&#x2781; Windows 10版本 1809。 此特定问题导致Microsoft Teams 会议室应用程序在夜间重新启动后无法启动。 Windows 10版本 1903 中解决了此问题。  

使用受支持的Windows 10版本时，始终会获取Microsoft Teams 会议室应用的最新应用程序更新。  


## <a name="related-topics"></a>相关主题

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 会议室发行说明](rooms-release-note.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
