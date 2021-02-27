---
title: 远程更新 Microsoft Teams 设备
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用 Teams 管理中心远程更新 Microsoft Teams 手机、Teams 面板和协作栏
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347883"
---
# <a name="update-microsoft-teams-devices-remotely"></a>远程更新 Microsoft Teams 设备

使用 Microsoft Teams 管理中心，可以远程更新 Teams 设备，例如 Teams 手机、Teams 面板和协作栏，还可以选择设备固件自动更新行为。 可以使用 Teams 管理中心在设备上更新以下内容：

- Teams 应用和 Teams 管理员代理
- 公司门户应用
- OEM 代理应用
- 设备固件

设备固件更新可以自动应用，也可以计划在将来的日期和时间。 其他可用的设备更新不会自动应用，但可以手动应用，也可以计划在将来的日期和时间。

> [!NOTE]
> 虽然可以计划设备固件更新，但如果计划的日期和时间在配置的最长 30 或 90 天延迟之后，则当达到最大延迟时应用固件更新。 将忽略计划的日期和时间。 此外，远程更新 Microsoft Teams 设备是美国政府云租户 (GCC-High) 。

若要管理设备，需要是全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色详细信息，请参阅["使用 Microsoft Teams 管理员角色管理 Teams"。](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>选择自动设备固件更新行为

将自动应用设备固件更新。 如果选择此选项，可以决定是否在发布更新后应用更新 (更新将在更新发布后的第一个周末应用) 或更新发布后的 30 或 90 天。 默认情况下，设备固件更新在发布后 30 天内应用。

> [!IMPORTANT]
> Teams 设备上未应用最新的固件更新版本。 相反，在设备上自动应用的更新会延迟一个版本。 例如，假设设备应用了版本"10"，并且发布了版本"11"。 版本"11"尚未应用。 而是仅在版本"12"发布后将设备更新到版本"11"。

> [!NOTE]
> 某些设备尚不支持自动固件更新。 在不支持自动更新的设备上应用自动固件更新设置不会影响这些设备。 有关设备是否支持自动固件更新的问题，请联系设备制造商。

若要选择设备的自动更新行为，请执行下列操作：

1. 访问 Microsoft Teams 管理中心 https://admin.teams.microsoft.com 。
2. 导航 **设备**  >  **IP 电话、****协作栏或** **Teams 面板**。
3. 选择一个或多个设备，然后选择"更新 **"。**
4. 在 **"固件自动更新"下**，选择以下选项之一：
    - **一旦可用** 最新设备固件更新在最新更新发布后的第一个周末应用。
    - **推迟 30 天** 第二个最新设备固件更新在最新更新发布后的 30 天内应用。
    - **推迟 90 天** 第二次最新的设备固件更新在最新更新发布后的 90 天内应用。
5. 选择 **"更新"。**

如果出于任何原因需要还原设备固件更新，则需要将设备重置为出厂设置。 按照制造商的说明重置设备。  

## <a name="manually-update-remote-devices"></a>手动更新远程设备

使用管理中心更新一个或多个设备时，可以决定是立即更新设备，还是计划将来日期和时间的更新。

若要手动更新远程设备，请执行下列操作：

1. 访问 Microsoft Teams 管理中心 https://admin.teams.microsoft.com 。
2. 导航 **设备**  >  **IP 电话、****协作栏或** **Teams 面板**。
3. 选择一个或多个设备，然后选择"更新 **"。**
4. 如果要 **将更新****计划为** 将来的日期和时间，请在"手动更新"下选择"计划"。 更新在时区中选定的时区的 **日期和时间应用**。

将看到的信息取决于是否选择了一个或多个设备。 下面的左侧图像显示已选择多个设备，而右侧图像显示选中的单个设备。

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的一个和多个设备视图":::

选择多个设备时，可以选择要应用到每个所选设备的更新类型。 选择要应用的更新类型，然后选择"更新 **"。**

选择单个设备时，会显示适用于设备的更新。 如果设备有多个更新类型可用，请选择要应用的每个更新类型。 可以查看设备上 **应用的** 当前版本以及 **要** 应用的新版本。 选择要应用 () ，然后选择"更新 **"。**

选择" **更新**"后，如果计划更新，更新将在所选日期和时间应用到设备。 如果未选择将来的日期和时间，更新数分钟内将应用到设备。
