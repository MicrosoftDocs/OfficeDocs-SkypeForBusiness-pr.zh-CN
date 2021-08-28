---
title: 管理Windows更新Microsoft Teams 会议室
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
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: 管理Windows更新Microsoft Teams 会议室
ms.openlocfilehash: 04572edd20c1c8e588b378ff3a225c103a58dff3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593606"
---
# <a name="manage-windows-updates"></a>管理Windows更新

Microsoft Teams 会议室 IoT Windows 10 企业版 VL Windows 10 企业版 (VL) ，并接收与Windows桌面相同的更新和操作系统版本。

Windows可以通过几种不同的方式管理更新：

## <a name="hands-off-approach"></a>动手方法 
- 可以直接从更新下载Windows更新，在非工作时间安装更新。 如果未对配置做出任何更改，则这是默认状态。
- 不可延迟的更新将自动安装第一天发布。 
- 质量更新和驱动程序将自动下载并安装第一天。 
- 功能更新。 请参阅下面的其他说明。 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows GPO (](/windows/deployment/update/waas-manage-updates-wufb) Intune)    
- 更新从 WU 或 WSUS 下载，但配置的延迟已过 KB 的原始发布日期。 
- 结合多个 OU 或筛选的策略，这允许创建部署"圈"，其中管理员可以指定哪些设备首先安装质量更新，哪些设备将在以后安装。 这样，可以在在整个部署中推出更新之前，在系统子集上实现可靠性和性能测试，而无需管理 Windows 更新等Microsoft Endpoint Configuration Manager开销。
- 如果您需要带宽管理和适用于Windows提供的控制，可以同时配置适用于[](/windows/deployment/update/waas-integrate-wufb)Business 的 WS Windows US 和 Windows 更新。
- 功能更新。 请参阅下面的其他说明。

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- 与适用于Windows更新非常类似，但具有用于在每个"圈"或整个部署中定位特定 KB 的其他选项。 可以立即单独部署和测试每个更新，而不是仅依赖延迟。 
- 功能更新。 请参阅下面的其他说明。


### <a name="feature-updates"></a>功能更新

与质量和不可延迟更新Windows 10， (主要操作系统版本) 仅在 Microsoft 使用 Microsoft Teams 会议室 测试并验证给定更新功能后，才安装"功能更新"。 即使你将系统设置为该通道以测试) 或者由你自己的尝试或配置手动推送 (即使将其释放到 Semi-Annual Channel (或 Targeted，它也不允许安装，直到我们端上的块被删除。

Microsoft Teams房间"开箱即用"，使用"开箱即用"方法Windows更新或因设备更新而自动Windows重启。 但是，系统可能会下载更新并等待下一次重启进行安装。 除非有人手动重新启动，否则安装应在自动夜间重启时执行。 Windows更新在聊天室中应该是透明的，UI 永远不应被更新Windows中断。

如果选择加入域，请使用 Microsoft Endpoint Configuration Manager 或 WSUS，请特别注意可能会导致设备在营业时间安装更新或强制重启的策略或操作。 如果你在使用期间在部署重启中或在 UI 上Windows更新警报，你将希望查看你的配置。