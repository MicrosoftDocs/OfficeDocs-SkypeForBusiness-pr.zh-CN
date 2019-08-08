---
title: 管理 Microsoft 团队聊天室的 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 团队聊天室的 Windows 更新
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243274"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行, 并作为标准桌面接收相同的 Windows 更新和 OS 版本。

可通过几种不同的方式管理 Windows 更新:

## <a name="hands-off-approach"></a>免提做法 

- 更新可以直接从 Windows 更新下载并在下班期间安装。 这是默认配置。
- 非延迟更新安装第1天-自动发布其中一个版本。
- 质量更新和驱动程序自动下载和安装第一天。
- 功能更新。 请参阅下面的备注。

## <a name="windows-updates-for-business-gpo-or-intune"></a>适用于企业的 Windows 更新 (GPO 或 Intune)  

- [Windows 更新企业](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)版下载
- 从 WU 或你的 WSUS 下载更新, 但已配置的延迟超过 KB 的原始发布日期。
- 与多个 OU 或筛选的策略一起使用, 您可以创建部署 "震铃", 管理员可在其中指定首先安装质量更新的设备, 以及哪些设备将在以后安装。 这样, 在通过整个部署 (例如在 SCCM 中管理 Windows 更新的开销) 在整个部署中滚动更新之前, 可以对系统的子集进行可靠性和性能测试。
- 如果你希望带宽管理和适用于企业的 Windows 更新的控件提供, 则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 Windows 更新 for business。
- 功能更新。 请参阅下面的备注。

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下载
- 与面向企业的 Windows 更新非常相似, 但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。 每个更新都可以单独部署和测试, 而不只是依赖于延迟。
- 功能更新。 请参阅下面的备注。

### <a name="feature-updates"></a>功能更新

与质量和非可推迟更新不同, Windows 10 "功能更新" (主要操作系统版本) 将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。 即使将更新发布到半年频道 (或者如果系统设置为用于测试的系统) 或手动推送的更新, Microsoft 会议室系统设备也不允许安装未经测试的更新。

Microsoft 团队会议室 "开箱", 使用 "退出" 方法, 不会为 Windows 更新自动安装 Windows 更新或重启设备。 系统可能会下载更新并等待下一次重新启动进行安装。 除非有人手动重新启动, 否则在每次自动重新启动时, 安装应会发生。 在聊天室中, windows 更新应该是透明的, UI 永远不会被 Windows 更新中断。

如果你选择加入域的设备, 请使用 SCCM 或 WSUS。 特别注意可能会导致设备在工作时间安装更新或强制重启的策略或操作。 在使用期间, 你的部署中的系统不应重启或在使用期间发出有关 Windows 更新的警报。如果发生此行为, 请查看你的配置。