---
title: 管理 Microsoft 团队聊天室的 Windows 更新
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 团队聊天室的 Windows 更新
ms.openlocfilehash: 346747d3d5731f5b4504c45066a39a28f5289e70
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628678"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版（VL）上运行，并作为标准桌面接收相同的 Windows 更新和 OS 版本。

可通过几种不同的方式管理 Windows 更新：

## <a name="hands-off-approach"></a>免提做法 
- 更新可以直接从 Windows 更新下载并在下班期间安装。 如果未对配置进行任何更改，则这是默认状态。
- 不可推迟的更新将会自动安装1天内的版本。 
- 质量更新和驱动程序将自动下载并安装第一天。 
- 功能更新。 请参阅下面的其他说明。 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)（GPO 或 Intune）   
- 从 WU 或你的 WSUS 下载更新，但已配置的延迟超过 KB 的原始发布日期。 
- 与多个 OU 或筛选的策略相结合，这允许创建部署 "震铃"，管理员可在其中指定首先安装质量更新的设备，以及哪些设备将在以后安装。 这允许在跨整个部署中滚动更新之前对系统子集执行可靠性和性能测试，而无需在 Microsoft 终结点配置管理器中管理 Windows 更新的开销。
- 如果你希望带宽管理和适用于企业的 Windows 更新的控件提供，则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新 for business。
- 功能更新。 请参阅下面的其他说明。

## <a name="wsusconfiguration-managerhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/配置管理器](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 与面向企业的 Windows 更新非常相似，但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。 每个更新都可以单独部署和测试，而不只是依赖于延迟。 
- 功能更新。 请参阅下面的其他说明。


### <a name="feature-updates"></a>功能更新

与 Quality 和非 Deferable 更新不同，Windows 10 "功能更新" （主要 OS 版本）将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。 即使已将其发布到半年频道（或目标系统将系统设置为用于测试的系统），或者甚至手动按您自己的尝试或配置手动推送，它也不会允许安装，直到删除端点上的块。

Microsoft 团队聊天室 "开箱"，使用 "退出" 方法，将不会因 Windows 更新而自动安装 Windows 更新或重启设备。 但是，系统可能会下载更新并等待下一次重新启动进行安装。 除非有人手动重新启动，否则在每次自动重新启动时，安装应会发生。 在聊天室中，windows 更新应该是透明的，UI 永远不会被 Windows 更新中断。

如果你选择加入域，请使用 Microsoft 终结点配置管理器或 WSUS，请特别注意可能导致设备安装更新或在工作时间强制重启的策略或操作。 如果你的部署在使用期间重启系统或通过 UI 发出有关 Windows 更新的警报，你将希望查看你的配置。
