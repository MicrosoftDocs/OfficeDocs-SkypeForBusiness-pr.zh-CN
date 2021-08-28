---
title: 管理Windows更新Microsoft Teams 会议室
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
ms.assetid: ''
description: 管理员可以了解如何管理Windows更新Windows更新Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28f5d9def3a5217d1d34343e27cbaddb6a3433b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602117"
---
# <a name="manage-windows-updates"></a>管理Windows更新

Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行Windows接收与标准台式计算机相同的更新和 OS 版本。

Windows可以按照以下部分所述管理更新：

## <a name="hands-off-approach"></a>动手方法 

- 默认情况下，更新直接从 Windows更新下载，在非工作时间安装。
- 不可延迟的更新在发布的第一天自动安装。
- 质量更新和驱动程序会自动下载并安装第一天。
- 功能更新。 请参阅以下备注。

## <a name="windows-updates-for-business-gpo-or-intune"></a>WindowsBusiness (GPO 或 Intune)   

- [Windows更新 for Business](/windows/deployment/update/waas-manage-updates-wufb)下载
- 更新从 Windows 或 WSUS 下载，但配置的延迟比原始发布日期要快。
- 可以使用多个 US 或筛选的策略创建部署"环"，管理员可以在部署"环"中指定哪些设备先安装质量更新，哪些设备稍后安装。 在整个部署中推出更新之前，可以在一部分系统上测试可靠性和性能，而无需在配置管理器中Windows更新。
- 如果需要带宽管理和 Windows Business 更新提供的控制，可以[](/windows/deployment/update/waas-integrate-wufb)同时配置 WSUS Windows Business 更新。
- 功能更新。 请参阅以下备注。

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下载
- 与 Windows Update for Business 非常类似，但附加的选项是在每个"环"或整个部署中定位特定知识库。 可以单独部署并测试每个更新，而不是仅依赖于延迟。
- 功能更新。 请参阅以下备注。

### <a name="feature-updates"></a>功能更新

与质量和不可延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 使用 Microsoft Teams 会议室 测试和验证给定更新功能后安装。 即使更新已发布到 Semi-Annual Channel (或 Targeted（如果系统已设置为用于测试) 或手动推送的通道，Microsoft Room Systems 设备也不允许安装未经测试的更新。

Microsoft Teams 会议室"开箱即用"功能，并且不会为 Windows 更新自动安装 Windows 更新或重新启动设备。 系统下载更新并等待下次重新启动以安装它。 除非有人手动重新启动它，否则安装仅在夜间自动重新启动时进行。 Windows更新在聊天室中应该是透明的，正常操作不应被更新Windows中断。

如果选择将设备加入域，请使用 Microsoft Endpoint Configuration Manager WSUS。 请特别注意在营业时间导致设备更新或强制重新启动的策略或操作。 部署中的系统不应在使用期间重新启动，也不应在使用Windows UI 上提醒用户更新，如果发生此行为，请查看配置。