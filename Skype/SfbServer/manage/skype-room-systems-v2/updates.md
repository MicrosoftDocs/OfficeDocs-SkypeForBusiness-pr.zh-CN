---
title: 管理 Microsoft Teams 会议室的 Windows 更新
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft Teams 会议室的 Windows 更新
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832872"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行，并接收与标准桌面相同的 Windows 更新和操作系统版本。

可通过几种不同方式管理 Windows 更新：

## <a name="hands-off-approach"></a>动手方法 
- 可以直接从 Windows 更新下载更新，并可在非工作时间安装更新。 如果未对配置做出任何更改，则这是默认状态。
- 不可延迟的更新将自动安装第一天发布。 
- 质量更新和驱动程序将自动下载并安装第一天。 
- 功能更新。 请参阅下面的其他说明。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[适用于企业 (](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) GPO 或 Intune)    
- 更新从 WU 或 WSUS 下载，但配置的延迟已过 KB 的原始发布日期。 
- 结合多个 OU 或筛选的策略，这允许创建部署"圈"，其中管理员可以指定哪些设备先安装质量更新，哪些设备稍后安装。 这样，可以在整个部署中推出更新之前，在系统子集上进行可靠性和性能测试，而无需管理 Microsoft Endpoint Configuration Manager 中的 Windows 更新（例如）。
- 如果你同时需要带宽管理和适用于企业 Windows[](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)更新提供的控制，可以同时配置适用于 Business 的 WSUS 和 Windows 更新。
- 功能更新。 请参阅下面的其他说明。

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 与适用于 Business 的 Windows 更新非常类似，但具有在每个"圈"或整个部署中定位特定 KB 的其他选项。 可以单独部署和测试每个更新，而不是仅依赖延迟。 
- 功能更新。 请参阅下面的其他说明。


### <a name="feature-updates"></a>功能更新

与质量和非延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 测试和验证 Microsoft Teams 会议室的给定更新功能后安装。 即使将其发布至 Semi-Annual Channel (或 Targeted（如果你将系统设置为该通道以测试) ，甚至手动推送到你自己的尝试或配置中，它将不会允许安装，直到我们端上的阻止被删除。

Microsoft Teams 会议室"开箱即用"使用"开箱即用"方法，将不会由于 Windows 更新而安装 Windows 更新或自动重新启动设备。 但是，系统可能会下载更新并等待下一次重启以安装它。 除非有人手动重新启动它，否则应在自动夜间重启时进行安装。 Windows 更新在聊天室中应该是透明的，并且 UI 永远不应被 Windows 更新中断。

如果选择加入域，请使用 Microsoft Endpoint Configuration Manager 或 WSUS，请特别注意可能导致设备在营业时间安装更新或强制重启的策略或操作。 如果你在使用期间或在 UI 上提醒 Windows 更新时部署重启系统，你将希望查看你的配置。
