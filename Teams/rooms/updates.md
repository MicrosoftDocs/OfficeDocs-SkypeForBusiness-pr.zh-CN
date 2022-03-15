---
title: 管理Windows更新Microsoft Teams 会议室
ms.author: czawideh
author: cazawideh
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
ms.assetid: ''
description: 管理员可以了解如何管理Windows更新Windows更新Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503749"
---
# <a name="manage-windows-updates"></a>管理Windows更新

Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行Windows接收与标准台式计算机相同的更新和 OS 版本。

Windows如以下部分所述管理更新：

## <a name="hands-off-approach"></a>动手方法 

- 默认情况下，更新直接从 Windows更新下载，在非工作时间安装。
- 不可延迟的更新会在发布的第一天自动安装。
- 质量更新和驱动程序第一天自动下载并安装。
- 功能更新。 请参阅以下备注。

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows GPO (Intune)   

- [Windows更新 for Business](/windows/deployment/update/waas-manage-updates-wufb) 下载
- 更新从 Windows 更新或 Windows Server Update Services (WSUS) ，但配置的延迟会过原始发布日期。
- 可以使用多个 US 或筛选的策略创建部署"环"，管理员可以在"环"中指定哪些设备Teams 会议室安装质量更新，以及哪些设备稍后安装。 在整个部署中推出更新之前，可以在一部分设备上测试可靠性和性能，而无需在配置管理器中Windows更新。
- 如果同时Windows适用于 Business 的更新提供的带宽管理和控制，可以同时[](/windows/deployment/update/waas-integrate-wufb)配置 WSUS Windows Business 更新。
- 功能更新。 请参阅以下备注。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下载
- 与 Windows 更新 for Business 非常类似，但附加的选项是在每个"环"或整个部署中定位特定知识库。 可以单独部署并测试每个更新，而不是仅依赖于延迟。
- 功能更新。 请参阅以下备注。

### <a name="feature-updates"></a>功能更新

与质量和不可延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 使用 Microsoft Teams 会议室 测试并验证给定更新功能后才能安装。 即使更新已发布到 Semi-Annual 通道 (或定向（如果系统已设置为用于测试) 或手动推送的通道，Microsoft Teams 会议室 也不允许安装未经测试的更新。

Microsoft Teams 会议室一种动手方法，实现"开箱即用"功能。 Teams 会议室下载更新并等待下次重新启动以安装它。 除非有人手动重新启动它，否则安装仅在夜间自动重新启动时进行。 Windows更新在聊天室中应该是透明的，并且正常操作不应被更新Windows中断。

如果选择对加入设备进行域设置，可以使用 Microsoft Endpoint Configuration Manager WSUS。 请特别注意在营业时间导致设备更新或强制重新启动的策略或操作。 Teams 会议室使用期间不应重启，也不应在使用Windows UI 上提醒用户更新。 如果发生此行为，请查看配置。
