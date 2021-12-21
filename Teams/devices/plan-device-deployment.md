---
title: 规划手机设备和Teams的部署
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: 本文提供并概述在组织中部署Teams和显示的任务和步骤。
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577790"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>规划手机设备和Teams的部署

成功部署手机设备和Teams显示器Teams开始规划。 本文将介绍在组织中部署这些设备的任务和步骤。 它还提供有关设备使用情况、许可、与环境、触摸点和管理集成的指导。

> [!TIP]
> [采用Microsoft 365中心](https://adoption.microsoft.com/)是开始使用采用过程和采用Microsoft Teams。

## <a name="task-1-what-are-your-deployment-objectives"></a>任务 1：部署目标是什么？

在组织中规划Teams手机和显示器的部署首先需要制定部署目标。 Teams设备支持会议室、办公室和其他功能空间的混合工作。 你需要确定这些设备将在何处使用以及由谁使用。

### <a name="objective-identify-your-device-personas"></a>目标：标识设备角色

Teams手机和显示器将适合两个角色之一： 

- 个人设备
- 共享空间设备

个人设备和共享设备具有不同的角色和用法。 

**个人设备：** 

- 通常分配给一个用户，使用该用户的帐户登录，并启用Teams功能许可证来访问服务。
- 将个人设备视为具有一对一关系，每个用户一个设备。
- 可以与桌面客户端Teams，并使用 Better Together 等功能
- 可以连接到耳机、有线或无线设备
- 个人设备上的其他功能包括热桌面和主屏幕。 

**共享空间设备：**

- 执行特定功能，例如公用区域电话或会议室设备，并需要专用帐户和功能许可证才能访问该服务。
- 将共享设备视为具有一对多关系：一个设备由多个用户共享。
- 部署在会议室、接待区域或制造楼层等共享空间中。 
- 其用户界面 (UI) 特定于其功能，例如公共区域 电话 UI 或会议室 UI 取决于共享设备的功能和位置。
- 要求配置和可选强化，以确保不会更改设置，或防止帐户退出。 
- 共享空间设备的其他功能包括搜索公用区域电话和空闲超时的桌面

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目标：需要多少个个人和共享空间设备？

确定设备角色后，需要确定要使用哪些认证设备以及所需的设备数。 为了帮助你做出此决定，请考虑以下问题： 

- 需要多少个个人设备，谁将拥有一个？
- 多少房间或空间需要共享设备？ 每个空间是否具有相同的设备类型？ 
- 你的设备是否需要满足特定要求？
    - 示例包括屏幕大小、外形规格以及制造商或型号？ 有关认证电话和显示器的列表，请参阅[Microsoft Teams设备](teams-ip-phones.md)。
-  你是否需要Teams手机或Teams显示器？ 有关手机支持的功能Teams，请参阅手机[for Microsoft Teams，](phones-for-teams.md#features-supported-by-teams-phones)有关手机显示器支持的功能Teams，请参阅 Microsoft Teams[显示](teams-displays.md#features-supported-by-teams-displays)。
- 是否有足够的设备供新用户使用，或者新订单和交付的流程是否足够？
- 是否提供备用设备进行维护或发生硬件问题？ 能够快速交换设备可防止用户体验中断。

## <a name="task-2-what-are-your-licensing-requirements"></a>任务 2：你的许可要求是什么？ 

现在，你已知道需要多少台设备，下一步是确定需要多少个许可证。 Teams手机和显示器需要许可证来访问Microsoft Teams Microsoft 365。

共享设备和个人设备将需要不同的许可。 对于个人设备，可以使用分配给用户帐户的许可证。 共享设备需要特定于其功能的许可证。 对于手机和显示器，适用的[许可证是适用于](../set-up-common-area-phones.md#step-1---buy-the-licenses)电话 的公用Microsoft Teams许可证Microsoft Teams 会议室标准版[许可证](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)。

有关详细信息并比较许可选项，请参阅Microsoft 365[计划](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 

## <a name="task-3-what-are-your-dependencies"></a>任务 3：你的依赖项是什么？ 

### <a name="objective-plan-your-device-identities"></a>目标：规划设备标识

标识使设备能够访问Microsoft 365服务，并且它们应使设备更易于发现、管理和连接到组织内部。 为此，在规划设备标识时，请考虑以下事项：

- 用户主体名称及其格式和域
- 显示名称
- 通讯簿可发现性
- 个人与共享空间设备类型
- 组与用户分配的许可

### <a name="objective-review-conditional-access-policies"></a>目标：查看条件访问策略

Azure Active Directory条件访问策略是必须在设备登录之前满足的其他要求。

规划部署时

- 查看可能影响手机和显示器Teams条件访问策略。 可以使用 What If 工具和登录日志Azure AD[管理](/azure/active-directory/conditional-access/what-if-tool)中心[中执行此操作](/azure/active-directory/reports-monitoring/concept-sign-ins)

- 根据需要规划新规则

- 使用条件访问功能（如设备筛选器）将规则Teams手机和显示器。

>[!NOTE]
>某些条件访问策略是 Android 设备不支持的。 有关指南和最佳做法，请参阅 Android 设备，请参阅 Android Teams[的身份验证最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="task-4-prepare-your-environment"></a>任务 4：准备环境

### <a name="objective-plan-network-basics"></a>目标：规划网络基础知识

Teams 电话设备和显示器需要访问 Internet，Teams正常工作。 若要使网络准备好进行部署，请考虑以下事项：

- 网络基础结构是否有足够的容量？ 请考虑切换端口、无线接入点和其他覆盖区域。
- 如果使用 VLAN 和 DHCP，范围是否相应地调整？
- 评估并测试设备从何处部署到 Microsoft 365。 
- 根据指南打开所需的防火墙端口Microsoft 365 URL。
- 查看和测试 E911 要求和配置，确保位置准确性和符合性。 
- 避免使用代理服务器，并优化媒体路径，确保可靠性和质量。

### <a name="objective-physical-considerations"></a>目标：物理注意事项

请考虑你的手机和Teams将用于的物理空间。

主要方面包括

- **电源：** 是否有足够的电源插座？ 如果设备需要外部电源，可以将它定位到插座有多近？
- **设备放置：** 你的设备将实际在哪里？ 来自原始设备制造商和 OEM (审查台、墙壁支架和其他) 。
- **安全性：** 你的设备是否需要锁定在某些空间中？
- **辅助功能：** 设备是否满足其主要用户的辅助功能要求？ 请考虑放置位置、线路长度以及话筒或耳机的可用性。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>任务 5：如何管理已部署的设备？

Teams手机和显示器托管在两到三个Microsoft 365门户及其各自的 PowerShell 模块中： 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory管理中心

使用 Azure AD 管理中心进行管理

- 手机和显示器的所有标识Teams任务
- 条件访问策略 
- 密码重置

#### <a name="teams-admin-center"></a>Teams管理中心

使用 Teams 管理中心进行管理

- [设备的设备设置Teams](../business-voice/manage-devices.md)
- [配置文件](device-management.md#use-configuration-profiles-in-teams)
- [设备标记](manage-device-tags.md)
- [远程登录和注销](remote-sign-in-and-sign-out.md)
- 调用分析  
- 固件
- 排查和下载日志问题

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Intune 进行设备管理 (管理中心) 

使用Endpoint Manager管理中心管理： 

- 设备符合性策略
- 注册限制
- 企业设备标识符
- 设备筛选器
