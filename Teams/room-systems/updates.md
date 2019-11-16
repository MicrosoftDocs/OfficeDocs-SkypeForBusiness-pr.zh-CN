---
title: 管理 Microsoft 团队聊天室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理 Microsoft 团队聊天室的 Windows 更新
ms.openlocfilehash: 5f0942efc1b503589412a1de6852d83e42a3b03e
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675416"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版（VL）上运行，并接收与标准桌面计算机相同的 Windows 更新和操作系统版本。

可按以下部分中的讨论对 Windows 更新进行管理：

## <a name="hands-off-approach"></a>免提做法 

- 默认情况下，自动从 Windows 更新下载并在小时内安装更新。
- 非延迟更新安装第1天-自动发布其中一个版本。
- 质量更新和驱动程序自动下载和安装第一天。
- 功能更新。 请参阅下面的备注。

## <a name="windows-updates-for-business-gpo-or-intune"></a>适用于企业的 Windows 更新（GPO 或 Intune）  

- [Windows 更新企业](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)版下载
- 从 Windows 更新或 WSUS 下载更新，但已配置的延迟已超过原始发布日期。
- 你可以使用多个 Ou 或筛选的策略创建部署 "铃声"，管理员可以在其中指定首先安装质量更新的设备，以及哪些设备将在以后安装。 可以在系统子集上测试可靠性和性能，而无需在 SCCM 中管理 Windows 更新的开销。
- 如果你希望带宽管理和适用于企业的 Windows 更新的控件提供，则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 Windows 更新 for business。
- 功能更新。 请参阅下面的备注。

## <a name="wsussccm"></a>WSUS/SCCM

- [WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下载
- 与面向企业的 Windows 更新非常相似，但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。 每个更新都可以单独部署和测试，而不只是依赖于延迟。
- 功能更新。 请参阅下面的备注。

### <a name="feature-updates"></a>功能更新

与质量和非可推迟更新不同，Windows 10 "功能更新" （主要操作系统版本）将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。 即使将更新发布到半年频道（或者如果系统设置为用于测试的系统）或手动推送的更新，Microsoft 会议室系统设备也不允许安装未经测试的更新。

Microsoft 团队聊天室使用有干预方法的 "开箱" 功能，不会为 Windows 更新自动安装 Windows 更新或重启设备。 系统下载更新，并等待下一次重新启动进行安装。 除非有人手动重启，否则，仅在夜间自动重启时才会进行安装。 Windows 更新在聊天室中应该是透明的，正常操作不应被 Windows 更新中断。

如果选择 "加入域" 设备，请使用 SCCM 或 WSUS。 特别注意在营业时间内导致设备更新或强制重启的策略或操作。 在使用期间，你的部署中的系统不应重启或在使用期间发出有关 Windows 更新的警报。如果发生此行为，请查看你的配置。