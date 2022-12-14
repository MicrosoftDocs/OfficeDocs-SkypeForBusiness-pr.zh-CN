---
title: 规划 Teams 电话设备和显示器的部署
ms.author: dstrome
author: dstrome
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
description: 本文概述了在组织中部署 Teams 电话和显示器的任务和步骤。
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 4ba5c1a9ab59765a5a0af2ac145baf69fc4a8a9a
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392512"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>规划 Teams 电话设备和显示器的部署

成功部署 Teams 电话设备和 Teams 显示器从规划开始。 本文将指导你完成在组织中部署这些设备的任务和步骤。 它还提供有关设备使用情况、许可、与环境集成、接触点和管理的指导。

> [!TIP]
> [Microsoft 365 采用中心](https://adoption.microsoft.com/)是使用 Microsoft Teams 开始采用旅程的好地方。

## <a name="task-1-what-are-your-deployment-objectives"></a>任务 1：部署目标是什么？

在组织中规划 Teams 电话和显示器的推出从部署目标开始。 Teams 设备支持会议室、办公室和其他功能空间中的混合工作。 你需要确定这些设备的使用位置以及由谁使用。

### <a name="objective-identify-your-device-personas"></a>目标：识别设备角色

Teams 电话和显示器将适合以下两种角色之一： 

- 个人设备
- 共享空间设备

个人设备和共享设备具有不同的角色和用途。 

**个人设备：** 

- 通常分配给一个用户，使用该用户的帐户登录，并使用 Teams 功能许可证启用以访问服务。
- 将个人设备视为具有一对一关系，每个用户有一个设备。
- 可与 Teams 桌面客户端配对，并使用“共同改进”等功能
- 可以连接到耳机（有线或无线）
- 个人设备上的其他功能包括热桌面和主屏幕。 

**共享空间设备：**

- 执行特定功能，例如公用区域电话或会议室设备，并需要专用帐户和功能许可证才能访问服务。
- 将共享设备视为具有一对多关系：一个设备由多个用户共享。
- 部署在会议室、接待区或生产车间等共享空间中。 
- 其用户界面 (UI) 特定于其功能，例如公用区域电话 UI 或会议室 UI 取决于共享设备的功能和位置。
- 需要配置和可选强化，以确保设置不会更改，或阻止帐户注销。 
- 共享空间设备上的其他功能包括搜索公用区域电话和具有空闲超时的热桌面

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目标：需要多少个人和共享空间设备？

确定设备角色后，需要确定要使用的认证设备以及需要多少台设备。 为了帮助你做出此决定，请考虑以下问题： 

- 需要多少个个人设备，谁将拥有一个？
- 有多少会议室或空间需要共享设备？ 每个空间都会有相同类型的设备吗？ 
- 你的设备是否需要满足特定要求？
    - 示例包括屏幕大小、外形规格以及制造商或型号？ 有关经过认证的手机和显示器的列表，请参阅[Microsoft Teams 认证设备](teams-ip-phones.md)。
-  是否需要 Teams 手机或 Teams 显示器？ 有关 Teams 手机支持的功能列表，请参阅[适用于 Microsoft Teams 的电话](phones-for-teams.md#features-supported-by-teams-phones)。 有关 Teams 显示器支持的功能列表，请参阅 [Teams 显示Microsoft](teams-displays.md#features-supported-by-teams-displays)。
- 你是否有足够的设备供新用户使用，或者新订单和交付流程？
- 是否有备用设备可用于维护，或者如果设备遇到硬件问题？ 能够快速交换设备可防止用户体验中断。

## <a name="task-2-what-are-your-licensing-requirements"></a>任务 2：你的许可要求是什么？ 

现在，你已知道需要多少台设备，下一步是确定需要多少个许可证。 Teams 电话和显示器需要许可证才能访问 Microsoft Teams 和 Microsoft 365。

共享和个人设备需要不同的许可。 对于个人设备，可以使用分配给用户帐户的许可证。 共享设备需要特定于其功能的许可证。 对于手机和显示器，适用的许可证是[Microsoft Teams 共享设备许可证](/microsoftteams/teams-add-on-licensing/teams-shared-device-license)和[Microsoft Teams 会议室许可证](../rooms/rooms-licensing.md)。

有关详细信息并比较许可选项，请参阅 [Microsoft 365 许可计划](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。

## <a name="task-3-what-are-your-dependencies"></a>任务 3：你的依赖项是什么？ 

### <a name="objective-plan-your-device-identities"></a>目标：规划设备标识

标识使设备能够访问 Microsoft 365 服务，并且它们应使设备更易于在组织中发现、管理和连接。 若要实现此目的，请在规划设备标识时考虑以下事项：

- 用户主体名称及其格式和域
- 显示名称
- 通讯簿可发现性
- 个人与共享空间设备类型
- 组与用户分配的许可

### <a name="objective-review-conditional-access-policies"></a>目标：查看条件访问策略

Azure Active Directory 条件访问策略是设备登录之前必须满足的其他要求。

规划部署时

- 查看可能影响 Teams 手机和显示器的现有条件访问策略。 可以使用 [What If 工具和](/azure/active-directory/conditional-access/what-if-tool)[登录日志](/azure/active-directory/reports-monitoring/concept-sign-ins)在 Azure AD 管理员中心执行此操作

- 根据需要规划新规则

- 使用条件访问功能（如设备筛选器）将规则应用于 Teams 手机和显示器。

>[!NOTE]
>Android 设备不支持一些条件访问策略。 有关指南和最佳做法，请参阅 Android 设备，请参阅 [Teams Android 设备的身份验证最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="task-4-prepare-your-environment"></a>任务 4：准备环境

### <a name="objective-plan-network-basics"></a>目标：规划网络基础知识

Teams 电话设备和显示器需要访问 Internet 才能连接到 Teams 并按预期运行。 若要使网络做好部署准备，请考虑以下事项：

- 网络基础结构是否有足够的容量？ 考虑交换机端口、无线接入点和其他覆盖范围。
- 如果使用 VLAN 和 DHCP，范围的大小是否相应调整？
- 评估和测试从设备部署到 Microsoft 365 的网络路径。 
- 根据指导打开 Microsoft 365 所需的防火墙端口和 URL。
- 查看并测试位置准确性和合规性的 E911 要求和配置。 
- 避免使用代理服务器，并优化媒体路径，以确保可靠性和质量。

### <a name="objective-physical-considerations"></a>目标：物理注意事项

请考虑使用 Teams 手机和显示器的物理空间。

关键方面包括

- **权力：** 是否有足够的电源插座？ 如果设备需要外部电源，可以将其定位到插座的距离有多近？
- **设备放置：** 你的设备在物理上会在哪里？ 查看原设备制造商 (OEM) 的桌面支架、壁架和其他配件。
- **安全：** 你的设备是否需要锁定在某些空间中？
- **辅助功能：** 设备是否满足其主要用户的辅助功能要求？ 考虑放置位置、电线长度以及听筒或头戴显示设备的可用性。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>任务 5：如何管理已部署的设备？

Teams 电话和显示器从两个到三个Microsoft 365 门户及其各自的 PowerShell 模块进行管理： 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 管理员 Center

使用 Azure AD 管理员中心进行管理

- Teams 手机和显示器的所有标识相关任务
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
- 故障排除和下载日志

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>如果将Intune用于设备管理) ，管理员中心 (终结点管理器

使用 Endpoint Manager 管理员 Center 管理： 

- 设备符合性策略
- 注册限制
- 公司设备标识符
- 设备筛选器
