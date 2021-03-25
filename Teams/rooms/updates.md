---
title: 管理 Microsoft Teams 会议室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理员可以了解如何管理 Microsoft Teams 会议室的 Windows 更新和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117360"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行，接收与标准台式计算机相同的 Windows 更新和 OS 版本。

可以按照以下部分所述管理 Windows 更新：

## <a name="hands-off-approach"></a>动手方法 

- 默认情况下，更新直接从 Windows 更新下载，在非工作时间安装。
- 不可延迟的更新在发布的第一天自动安装。
- 质量更新和驱动程序会自动下载并安装第一天。
- 功能更新。 请参阅以下备注。

## <a name="windows-updates-for-business-gpo-or-intune"></a>适用于 Business 的 Windows (GPO 或 Intune)   

- [适用于 Business 的 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb) 下载
- 更新从 Windows 更新或 WSUS 下载，但配置的延迟会过原始发布日期。
- 可以使用多个 US 或筛选的策略创建部署"环"，管理员可以在部署"环"中指定哪些设备先安装质量更新，哪些设备稍后安装。 在整个部署中推出更新之前，可以在一部分系统上测试可靠性和性能，而无需在配置管理器中管理 Windows 更新。
- 如果你同时需要带宽管理和 Windows 商业更新[](/windows/deployment/update/waas-integrate-wufb)提供的控件，可以同时配置 WSUS 和 Windows 更新 for Business。
- 功能更新。 请参阅以下备注。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下载
- 与 Windows Update for Business 非常类似，但具有在每个"环"或整个部署中以特定 KB 为目标的额外选项。 可以单独部署并测试每个更新，而不是仅依赖于延迟。
- 功能更新。 请参阅以下备注。

### <a name="feature-updates"></a>功能更新

与质量和不可延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 通过 Microsoft Teams 会议室测试和验证给定更新功能后安装。 即使更新已发布到 Semi-Annual Channel (或 Targeted（如果系统已设置为用于测试) 或手动推送的通道，Microsoft Room Systems 设备也不允许安装未经测试的更新。

Microsoft Teams 会议室功能"开箱即用"，不会为 Windows 更新自动安装 Windows 更新或重新启动设备。 系统下载更新并等待下次重新启动以安装它。 除非有人手动重新启动它，否则安装仅在夜间自动重新启动时进行。 Windows 更新在聊天室中应该是透明的，正常操作不应被 Windows 更新中断。

如果选择将设备加入域，请使用 Microsoft 终结点配置管理器或 WSUS。 请特别注意在营业时间导致设备更新或强制重新启动的策略或操作。 部署中的系统不应在使用期间重新启动，也不应在使用时间通过 UI 提醒 Windows 更新，如果发生此行为，请查看配置。