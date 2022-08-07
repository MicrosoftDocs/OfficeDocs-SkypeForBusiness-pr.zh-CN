---
title: 管理适用于Microsoft Teams 会议室的 Windows 汇报
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: 管理员可以了解如何管理适用于Microsoft Teams 会议室的 Windows 汇报和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272177"
---
# <a name="manage-windows-updates"></a>管理 Windows 汇报

Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行，并接收与标准桌面计算机相同的 Windows 汇报和 OS 生成。

可以按以下部分中所述管理 Windows 汇报：

## <a name="hands-off-approach"></a>举手方法 

- 默认情况下，更新将直接从 Windows 汇报自动下载并在非工作时间安装。
- 不可延迟汇报自动安装发布第一天。
- 质量汇报和驱动程序会自动下载并安装第一天。
- 功能汇报。 请参阅下面的说明。

## <a name="windows-updates-for-business-gpo-or-intune"></a>适用于企业的 Windows 汇报 (GPO 或 Intune)   

- [适用于企业的 Windows 汇报](/windows/deployment/update/waas-manage-updates-wufb)下载
- 汇报从Windows 更新或Windows Server Update Services (WSUS) 下载，但已配置延迟超过原始发布日期。
- 可以使用多个 OU 或筛选策略创建部署“圈”，管理员可以指定哪些Teams 会议室设备先安装质量汇报，然后安装哪些设备。 在在整个部署中推出更新之前，可以在一部分设备上测试可靠性和性能，而无需在Configuration Manager中管理 Windows 汇报的开销。
- 如果同时需要带宽管理和适用于企业的 Windows 汇报提供的控件，可以[同时配置](/windows/deployment/update/waas-integrate-wufb) WSUS 和适用于企业的 Windows 汇报。
- 功能更新。 请参阅下面的说明。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下载
- 很像适用于企业的Windows 更新，但具有针对每个“环”或整个部署中特定 KB 的附加选项。 每个更新都可以单独部署和测试，而不是仅依赖于延迟。
- 功能更新。 请参阅下面的说明。

### <a name="feature-updates"></a>功能更新

与质量和不可延迟更新不同，Windows 10“功能汇报” (主要 OS 版本) 仅在 Microsoft 测试后安装，并使用Microsoft Teams 会议室验证给定更新功能。 即使更新发布到Semi-Annual频道 (或目标，如果你已将系统设置为该通道进行测试) 或手动推送，Microsoft Teams 会议室也不会允许安装未经测试的更新。

Microsoft Teams 会议室使用即用方法“开箱即用”的函数。 Teams 会议室下载更新并等待下一次重启安装。 除非有人手动重新启动，否则安装仅在自动夜间重新启动时进行。 Windows 汇报在会议室中应是透明的，并且 Windows 汇报不应中断正常操作。

如果选择加入域设备，可以使用 Microsoft Endpoint Configuration Manager或 WSUS。 特别注意在工作时间内导致设备更新或强制重启的策略或操作。 Teams 会议室不应在使用期间重新启动，也不应在使用时段内通过 UI 对 Windows 汇报发出警报。 如果发生此行为，请查看配置。
