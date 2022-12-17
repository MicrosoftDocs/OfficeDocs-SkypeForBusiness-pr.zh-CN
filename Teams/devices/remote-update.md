---
title: 远程更新Microsoft Teams 设备
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用 Teams 管理中心远程更新 android 设备上的Microsoft Teams 电话、Teams 面板和Teams 会议室。
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438260"
---
# <a name="update-microsoft-teams-devices-remotely"></a>远程更新Microsoft Teams 设备

使用 Microsoft Teams 管理中心，可以远程更新 Teams 设备，例如 Android 上的 Teams 电话、Teams 面板和Teams 会议室。 可以从 Teams 管理中心更新设备上的以下软件组件：

- Teams 应用
- 设备固件

默认情况下，设备固件更新会自动发生。 但是，可以手动更新固件和其他软件组件。 手动应用更新时，可以立即应用更新，也可以针对将来的日期和时间进行计划。

只有通过 Microsoft 测试的固件版本才能通过 Teams 管理中心进行自动更新或手动更新。 Microsoft测试的固件版本标记为 **“已验证”Microsoft**。 尚未由Microsoft测试的固件版本标记为 **“未知版本**”。 无法自动更新运行未知固件版本的设备;这些设备只能手动更新。

若要管理设备，需要是全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的详细信息，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](../using-admin-roles.md)。

## <a name="assign-devices-to-an-automatic-update-phase"></a>将设备分配到自动更新阶段

将设备分配到自动更新阶段是 Android 设备上Teams 会议室的一项Teams 会议室专业版功能。 具有 Teams 会议室 基本许可证的设备将分配到“常规”阶段。 将维护任何预配置的阶段，不允许进一步更改。 有关详细信息，请参阅[Microsoft Teams 会议室许可证](../rooms/rooms-licensing.md)。  

使用 Teams 管理中心的 Teams 设备自动更新在 GCC High 中不可用。 但是，GCC High 中的组织可以使用 Teams 管理中心 [手动更新 Teams 设备](#manually-update-remote-devices) 。

> [!IMPORTANT]
> 自动更新功能目前处于早期版本。 汇报的部署速度可能比所选阶段慢。 在接下来的几个月里，自动部署更新的速度将提高，直到它们达到你选择的阶段。

> [!NOTE]
> 某些设备尚不支持自动固件更新。 在不支持自动更新的设备上应用自动固件更新设置不会对这些设备产生任何影响。 有关设备是否支持自动固件更新的问题，请联系设备制造商。
>
> 汇报在周末和典型营业时间外应用，以避免中断。 阶段中的设备将在几周内逐步更新，而不是一次性更新。

若要为设备选择自动更新阶段，请执行以下操作：

1. 通过访问 https://admin.teams.microsoft.com登录到 Microsoft Teams 管理中心。
2. 导航到 **Teams 设备**，然后选择 **Android 上的****电话**、**显示器**、**面板** 或Teams 会议室。  
3. 选择一个或多个设备，然后选择“ **更新**”。
4. 在 **“固件自动更新**”下，选择以下选项之一：
    - **测试** 此选项最适合用于实验室或测试设备，可以在这些设备上执行需要执行的任何验证。 汇报发布最新固件版本后立即开始部署。 以前称为 **“尽快**”。
    - **一般** 这是默认选项，最适合大多数常规用途设备。 汇报新固件版本发布 30 天后才开始部署。 以前称为 **延迟 30 天**。
    - **最后** 此选项最适合 VIP 使用的设备，在完成大规模验证后在大型设置中使用。 汇报从新固件版本发布 90 天后开始部署。 以前称为 **延迟 90 天**。
5. 选择“ **更新**”。

若要查看设备处于哪个阶段，请参阅 Teams 管理中心的 **固件自动更新** 列。 若要查看哪些设备属于特定阶段，请使用 **“筛选器”** 选项和 **自动更新阶段** 参数。

若要还原设备固件更新，需要将设备重置为其出厂设置。 按照制造商的说明重置设备。  

## <a name="manually-update-remote-devices"></a>手动更新远程设备

如果要使用 Teams 管理中心手动更新设备，可以决定是立即更新设备，还是为将来的日期和时间计划更新。

若要手动更新远程设备，请执行以下操作：

1. 通过访问 https://admin.teams.microsoft.com登录到 Microsoft Teams 管理中心。
2. 导航 **Teams 设备**，然后选择 **Android 上的****电话**、**显示器**、**面板** 或Teams 会议室。
3. 选择一个或多个设备，然后选择“ **更新**”。
4. 如果要为将来的日期和时间计划更新，请选择“ **手动更新**”下的“ **计划** ”。 更新将在时区中选择的 **时区中的日期和时间** 应用。

你将看到的内容取决于你是否选择了一个或多台设备。 下面的左图显示了选择的多个设备，而右侧的图像显示所选的单个设备。

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图。":::

选择多个设备时，可以选择要应用于每个所选设备的更新类型。 选择要应用的更新类型，然后选择“ **更新**”。

选择单个设备时，将显示可用于该设备的更新。 如果设备有多个更新类型可用，请选择要应用的每种更新类型。 可以查看设备上应用的 **当前版本** 和将要应用的 **新版本** 。 选择要应用的更新 () ，然后选择“ **更新**”。

选择“ **更新**”后，更新将在你计划更新时选择的日期和时间应用于设备。 如果未选择将来的日期和时间，则会在几分钟内将更新应用到设备。
