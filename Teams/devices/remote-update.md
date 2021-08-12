---
title: 远程Microsoft Teams更新设备
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
description: 使用 Microsoft Teams 管理Teams远程更新手机、Teams面板和 Teams协作栏
ms.openlocfilehash: 8ff925756e91c72c42d1557a1c735e5323691272a82405d5e4047ab4ff9828b5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322684"
---
# <a name="update-microsoft-teams-devices-remotely"></a>远程Microsoft Teams更新设备

使用 Microsoft Teams 管理中心，可以远程更新 Teams 设备，例如 Teams 手机、Teams 面板和协作栏，还可以选择设备固件自动更新行为。 可以使用管理中心在设备上Teams以下内容：

- Teams应用和 Teams 管理员代理
- 公司门户应用
- OEM 代理应用
- 设备固件

可以自动应用设备固件更新，也可以计划在将来的日期和时间进行更新。 其他可用的设备更新不会自动应用，但可以手动应用或计划在将来的日期和时间。

> [!NOTE]
> 虽然可以计划设备固件更新，但如果计划的日期和时间低于配置的最长 30 天或 90 天延迟，则当达到最大延迟时，将应用固件更新。 将忽略计划的日期和时间。 此外，Microsoft Teams远程更新设备是美国政府云租户 (GCC-High) 。

若要管理设备，需要是全局管理员、Teams管理员或Teams管理员。有关管理员角色详细信息，请参阅使用 Microsoft Teams[管理员角色管理Teams。](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>选择自动设备固件更新行为

将自动应用设备固件更新。 可以决定是否在发布更新后应用更新 (如果选择此选项，更新将在更新发布) 后的第一个周末或更新发布后的 30 或 90 天内应用。 默认情况下，设备固件更新在发布后 30 天内应用。

> [!IMPORTANT]
> 最新的固件更新版本不会应用到Teams设备上。 相反，在设备上自动应用的更新会延迟一个版本。 例如，假设设备应用了版本"10"，并且发布了版本"11"。 版本"11"尚未应用。 而是仅在发布版本"12"后将设备更新到版本"11"。

> [!NOTE]
> 某些设备尚不支持自动固件更新。 在不支持自动更新的设备上应用自动固件更新设置不会影响这些设备。 有关设备是否支持自动固件更新的问题，请与设备制造商联系。

若要选择设备的自动更新行为，请执行下列操作：

1. 通过访问 Microsoft Teams登录到管理中心 https://admin.teams.microsoft.com 。
2. 导航 **设备**  >  **IP 电话** 或 **协作栏或****Teams面板**。
3. 选择一个或多个设备，然后选择"更新 **"。**
4. 在 **"固件自动更新"** 下，选择下列选项之一：
    - **一旦可用** 最新设备固件更新在最新更新发布后的第一个周末应用。
    - **推迟 30 天** 最新设备固件更新在最新更新发布后的 30 天内应用。
    - **推迟 90 天** 最新设备固件更新在最新更新发布后的 90 天内应用。
5. 选择"**更新"。**

如果出于任何原因需要还原设备固件更新，则需要将设备重置为出厂设置。 按照制造商的说明重置设备。  

## <a name="manually-update-remote-devices"></a>手动更新远程设备

使用管理中心更新一个或多个设备时，可以决定是立即更新设备，还是计划将来日期和时间的更新。

若要手动更新远程设备，请执行下列操作：

1. 通过访问 Microsoft Teams登录到管理中心 https://admin.teams.microsoft.com 。
2. 导航 **设备**  >  **IP 电话** 或 **协作栏或****Teams面板**。
3. 选择一个或多个设备，然后选择"更新 **"。**
4. 在 **"手动更新**" **下** ，如果要将更新计划为将来的日期和时间，请选择"计划"。 更新在时区 中选定的时区中的 **日期和时间应用**。

将看到的信息取决于是否选择了一个或多个设备。 下面的左侧图像显示了选中的多个设备，而右侧图像显示选中的单个设备。

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图":::

选择多个设备时，可以选择要应用到每个所选设备的更新类型。 选择要应用的更新类型，然后选择"更新 **"。**

选择单个设备时，会显示适用于设备的更新。 如果设备有多个更新类型可用，请选择要应用的每个更新类型。 可以查看设备上 **应用的** 当前版本和 **要应用的** 新版本。 选择要 (更新) ，然后选择"更新 **"。**

选择" **更新**"后，如果计划了更新，则更新将在你选择的日期和时间应用到你的设备。 如果未选择将来的日期和时间，则更新将几分钟内应用到设备。
