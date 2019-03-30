---
title: 为 Microsoft 团队房间管理 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 为 Microsoft 团队房间管理 Windows 更新
ms.openlocfilehash: 723ecf20fb835a3d942270e9de6d59416a9cd14a
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013100"
---
# <a name="manage-windows-updates"></a>管理 Windows 更新

Microsoft 团队聊天室 Windows 10 企业 IoT 或 Windows 10 企业 (VL) 上运行并接收作为标准桌面相同的 Windows 更新和操作系统版本。

Windows 更新可以管理几个不同的方式：

## <a name="hands-off-approach"></a>干预方法 
- 可以自动下载直接从 Windows 更新和非工作时间安装更新。 如果不做任何更改到配置这是默认状态。
- 非可延迟更新将自动安装版本的-一天。 
- 质量更新和驱动程序将自动下载和安装第一天。 
- 功能更新。 请参阅以下其他注意事项。 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)（GPO 或 Intune）   
- 从 WU 或您 WSUS 但以前 KB 的原始发行版的日期配置延迟下载更新。 
- 结合多个 OU 或筛选策略，这将允许创建的部署"拨打"，其中管理员可以指定哪些设备先安装高质量的更新和其与将安装更高版本。 这样，以实现可靠性和性能测试跨整个部署无需开销的管理 SCCM 中的 Windows 更新，例如推出更新之前系统的子集。
- WSUS 和 for Business Windows 更新，可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)根据需要带宽管理和控制业务的 Windows Update 提供。
- 功能更新。 请参阅以下其他注意事项。

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 就像 Windows Update for Business，但是有面向特定 KB 的每个"拨打"或整个部署中的其他选项。 每个更新可以分别部署和测试在将，而不是信赖上仅延迟。 
- 功能更新。 请参阅以下其他注意事项。


### <a name="feature-updates"></a>功能更新

质量和非 Deferable 与更新不同，Windows 10 Microsoft 测试并验证给定的更新功能与 Microsoft 团队聊天室后，将仅安装"功能更新"（主要操作系统版本）。 即使它是释放到半年通道 （或目标如果必须设置为测试该频道的系统），或者甚至手动推送尝试或配置，它将不允许安装，直到删除的阻止，我们结束。

使用手中的关闭方法中，Microsoft 团队会议室"out box"不将安装 Windows Update 或由于 Windows Update 的自动重新启动设备。 但是，系统可能下载更新，等待下一步的重新启动以安装它。 除非某人重新启动它手动安装何时发生在夜间自动重新启动。 Windows 更新在聊天室中应为透明，UI 应永远不会在 Windows 更新被打断。

如果您选择加入域，使用 SCCM 或 WSUS，并请特别注意策略或可能会导致设备安装更新或强制重新启动工作时间内的操作。 如果您有系统使用过程中重新启动或通过 UI 警报 Windows 更新有关在部署中，要查看您的配置。