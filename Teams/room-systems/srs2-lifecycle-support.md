---
title: 版本支持
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: 本文介绍 Microsoft 团队聊天室的生命周期支持。
ms.openlocfilehash: dc4f8c0997ee64f4011aed6056be506738012639
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427683"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft 团队聊天室应用版本支持
 
Microsoft 计划每年对 Microsoft 团队会议室进行一次版本的更新, 每个更新支持 12 (12) 个月的每次更新 (GA) 发布日期。 为全 12 (12) 个月提供技术支持。 但是, 支持结构现在是动态的, 它发展成两个截然不同的服务阶段, 它们依赖于最新版本的可用性。

**服务和关键更新服务阶段**\-当运行最新版本的 Microsoft 团队聊天室时, 将收到定期更新, 其中包含安全和服务更新。

**安全更新 (仅限) 服务阶段**\-发布新版本后, 对较旧的分支的支持仅减少到 12 (12) 个月的剩余服务更新支持生命周期的安全更新。

> [!NOTE]
> 最新版本始终位于 "服务" 和 "关键更新服务" 阶段。 这意味着, 如果遇到可保证关键更新的代码缺陷, 则必须安装最新版本才能接收修补程序。 所有其他支持的版本仅有资格接收安全更新。

所有支持将在某版本的 12 (12) 个月生命周期到期后, 或者自那时起发布超过两个更新时结束。 然后, 客户必须更新到受支持的版本。

所有版本均在[Microsoft 团队聊天室发行说明](srs2-release-note.md)中列出。

# <a name="os-version-support"></a>操作系统版本支持
对于运行 Microsoft 团队聊天室的设备, windows 10 的功能更新不会在 Windows 发布更新时的6个月内提供。 通过在 Windows 更新 for Business 频道 (即半年频道) 和应用设置中为 Microsoft 团队聊天室设备放置特殊的块来完成此操作。 在此阻止期间, Microsoft 将在内部和设备 OEM 合作伙伴之间执行各种测试, 以确保新的 Windows 10 功能版本与连接到 Microsoft 团队聊天室应用和外围设备的协调配合工作。 这对确保设备安全性、一致的用户体验以及确保通过 Microsoft 团队聊天室应用提供的体验质量非常重要。 

从时间块提升 (即, 将 Windows 10 功能更新提供给在这些设备上下载), Microsoft 团队聊天室支持特定的 Windows 10 功能版本, 其中包含应用支持策略的12个月内的版本。 由于 Windows 10 功能更新是每六个月提供的, 因此这还意味着 Microsoft 团队有两个更多的版本可在当前版本的时间支持结束时进行测试。 这还意味着, 每隔六个月的 Windows 10 版本都将取消对所有 Microsoft 团队聊天室客户的阻止。 该应用在上次取消阻止的 Windows 版本中不断更改和开发。 为确保你在 Microsoft 团队聊天室设备上遇到的问题的应用修复, 我们建议所有客户将这些设备升级到所提供的最新 Windows 10 功能更新, 以保持受支持的 windows 版本指南。

因此, Microsoft 团队聊天室设备需要 Windows 10 版本1709作为支持的最低版本 (从5月2019开始)。 Windows 10 版本1703或更低版本上的系统不提供新的应用版本。

> [!NOTE]
> 当 Microsoft 团队聊天室设备与下一版本的 Windows 10 操作系统兼容时, 设备会通过 Windows 更新自动更新到下一个版本。 Microsoft 团队聊天室设备不应手动升级到下一版本的 Windows 10, 或者通过启用 Windows 更新 (WUFB) 组策略, 使用 "选择要接收的更新的 Windows 准备情况级别" 和 "当通过 GPO 接收 "预览内部版本" 和 "功能更新" 选项。 已知启用这些组策略会导致 Windows 10 操作系统更新和 Microsoft 团队聊天室应用之间出现问题。 
 
<a name="See"> </a> 
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 团队聊天室发行说明](srs2-release-note.md)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
