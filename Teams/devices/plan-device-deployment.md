---
title: 规划 Teams 手机设备和显示器的部署
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
description: 本文提供并概述部署 Teams 电话和在组织中显示的任务和步骤。
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 5172d230823088141c58e3d2b58e1c3b579268b3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272387"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>规划 Teams 手机设备和显示器的部署

Teams 手机设备和 Teams 显示器的成功部署从规划开始。 本文将指导你完成在组织中部署这些设备的任务和步骤。 它还提供有关设备使用情况、许可、与环境集成、触摸点和管理的指导。

> [!TIP]
> [Microsoft 365 采用中心](https://adoption.microsoft.com/) 是开始使用 Microsoft Teams 的采用旅程的好地方。

## <a name="task-1-what-are-your-deployment-objectives"></a>任务 1：部署目标是什么？

从部署目标开始，规划 Teams 手机和显示在组织中的推出。 Teams 设备支持会议室、办公室和其他功能空间中的混合工作。 你需要确定将使用这些设备的位置以及由谁使用。

### <a name="objective-identify-your-device-personas"></a>目标：识别设备角色

Teams 手机和显示器将适合以下两个角色之一： 

- 个人设备
- 共享空间设备

个人设备和共享设备具有不同的角色和用法。 

**个人设备：** 

- 通常分配给一个用户，使用该用户的帐户登录，并使用 Teams 功能许可证启用以访问服务。
- 将个人设备视为具有一对一关系，每个用户有一个设备。
- 可以与 Teams 桌面客户端配对，并使用“更好在一起”等功能
- 可以连接到耳机、有线或无线
- 个人设备上的其他功能包括热桌面和主屏幕。 

**共享空间设备：**

- 执行特定的函数，如公共区域电话或会议室设备，并且需要专用帐户和功能许可证才能访问该服务。
- 将共享设备视为具有一对多关系：一个设备由许多用户共享。
- 部署在会议室、接待区或制造车间等共享空间中。 
- 其用户界面 (UI) 特定于其函数，例如公共区域电话 UI 或会议室 UI 取决于共享设备的功能和位置。
- 需要配置和可选强化，以确保设置不会更改，或阻止帐户注销。 
- 共享空间设备上的其他功能包括搜索公共区域电话和空闲超时时的热桌面

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目标：需要多少台个人和共享空间设备？

现在，你已确定设备角色，需要确定要使用的认证设备以及需要的设备数量。 若要帮助你做出此决定，请考虑以下问题： 

- 需要多少台个人设备，谁将拥有个人设备？
- 需要共享设备的房间或空间数？ 每个空间是否都具有相同类型的设备？ 
- 设备需要满足特定要求吗？
    - 示例包括屏幕大小、外形因子以及制造商或模型？ 有关认证电话和显示器的列表，请参阅 [Microsoft Teams 认证的设备](teams-ip-phones.md)。
-  是否需要 Teams 电话或 Teams 显示？ 有关 Teams 手机支持的功能列表，请参阅 [Microsoft Teams 手机](phones-for-teams.md#features-supported-by-teams-phones)和 Teams 显示支持的功能列表，请参阅 [Microsoft Teams 显示。](teams-displays.md#features-supported-by-teams-displays)
- 你是否有足够的设备供新用户使用，还是新订单和交付流程？
- 你是否可以使用备用设备进行维护或发生硬件问题？ 能够快速交换设备可防止用户体验中断。

## <a name="task-2-what-are-your-licensing-requirements"></a>任务 2：许可要求是什么？ 

现在你知道需要多少台设备，下一步是确定需要多少个许可证。 Teams 手机和显示器需要许可证才能访问 Microsoft Teams 和 Microsoft 365。

共享设备和个人设备将需要不同的许可。 对于个人设备，可以使用分配给用户帐户的许可证。 共享设备需要特定于其函数的许可证。 对于手机和显示器，适用的许可证是 [Microsoft Teams 的通用区域电话许可证](../set-up-common-area-phones.md#step-1---buy-the-licenses)和[Microsoft Teams 会议室标准版许可证](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)。

有关详细信息和比较许可选项，请参阅 [Microsoft 365 许可计划](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 

## <a name="task-3-what-are-your-dependencies"></a>任务 3：依赖项是什么？ 

### <a name="objective-plan-your-device-identities"></a>目标：规划设备标识

标识使设备能够访问 Microsoft 365 服务，并且它们应该使设备更易于发现、管理和连接到组织内。 若要实现此目的，请在规划设备标识时考虑以下事项：

- 用户主体名称及其格式和域
- 显示名称
- 通讯簿可发现性
- 个人与共享空间设备类型
- 组与用户分配的许可

### <a name="objective-review-conditional-access-policies"></a>目标：查看条件访问策略

Azure Active Directory 条件访问策略是必须满足的其他要求，才能登录设备。

规划部署时

- 查看可能影响 Teams 手机和显示的现有条件访问策略。 可以使用 [What If 工具](/azure/active-directory/conditional-access/what-if-tool)和[登录日志](/azure/active-directory/reports-monitoring/concept-sign-ins)在 Azure AD 管理员中心执行此操作

- 根据需要规划新规则

- 使用设备筛选器等条件访问功能将规则应用于 Teams 手机和显示器。

>[!NOTE]
>有一些 Android 设备不支持的条件访问策略。 有关指南和最佳做法，请参阅 Android 设备，请参阅 [Teams Android 设备的身份验证最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="task-4-prepare-your-environment"></a>任务 4：准备环境

### <a name="objective-plan-network-basics"></a>目标：规划网络基础知识

Teams 电话设备和显示器需要访问 Internet 才能连接到 Teams 并按预期运行。 若要使网络准备好进行部署，请考虑以下事项：

- 网络基础结构是否有足够的容量？ 考虑交换端口、无线接入点和其他覆盖范围。
- 如果使用 VLAN 和 DHCP，范围是否相应调整？
- 评估和测试从何处将设备部署到 Microsoft 365 的网络路径。 
- 根据指南打开 Microsoft 365 所需的防火墙端口和 URL。
- 查看并测试 E911 要求和配置，了解位置准确性和符合性。 
- 避免使用代理服务器并优化媒体路径以实现可靠性和质量。

### <a name="objective-physical-considerations"></a>目标：物理注意事项

请考虑 Teams 手机和显示器将使用的物理空间。

关键方面包括

- **权力：** 是否有足够的电源插座？ 如果设备需要外部电源，可将它定位到出口有多近？
- **设备放置：** 设备的实际位置是什么？ 查看桌面展台、壁板和其他来自原始设备制造商的配件 (OEM) 。
- **安全：** 设备是否需要锁定在特定空格中？
- **辅助功能：** 设备是否满足其主要用户的辅助功能要求？ 考虑放置位置、电线长度、手机或耳机可用性。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>任务 5：如何管理已部署的设备？

Teams 手机和显示器从两个到三个 Microsoft 365 门户及其各自的 PowerShell 模块进行管理： 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 管理员中心

使用 Azure AD 管理员中心进行管理

- Teams 手机和显示的所有标识相关任务
- 条件访问策略 
- 密码重置

#### <a name="teams-admin-center"></a>Teams 管理员中心

使用 Teams 管理员中心进行管理

- [Teams 的设备设置](../business-voice/manage-devices.md)
- [配置文件](device-management.md#use-configuration-profiles-in-teams)
- [设备标记](manage-device-tags.md)
- [远程登录和注销](remote-sign-in-and-sign-out.md)
- 呼叫分析  
- 固件
- 排查和下载日志问题

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>如果将Intune用于设备管理) ，请Endpoint Manager 管理员中心 (

使用Endpoint Manager 管理员中心进行管理： 

- 设备符合性策略
- 注册限制
- 企业设备标识符
- 设备筛选器
