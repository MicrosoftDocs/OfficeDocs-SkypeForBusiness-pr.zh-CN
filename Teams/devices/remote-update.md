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
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用 Teams 管理中心远程更新 Microsoft Teams 手机、Teams 面板和协作栏
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269457"
---
# <a name="update-microsoft-teams-devices-remotely"></a>远程更新 Microsoft Teams 设备

使用 Microsoft Teams 管理中心，可以远程更新 Teams 设备（如 Teams 电话、Teams 面板和协作栏），并可以选择设备固件自动更新行为。 可以使用 Teams 管理中心在设备上更新以下内容：

- Teams 应用和团队管理员代理
- 公司门户应用
- OEM 代理应用
- 设备固件

设备固件更新可以自动应用，也可以计划将来的日期和时间。 其他可用的设备更新不会自动应用，但可以手动应用或计划将来的日期和时间。

> [!NOTE]
> 虽然可以计划设备固件更新，但如果计划日期和时间在配置的最大延迟 30 或 90 天后下降，则在达到最大延迟时应用固件更新。 将忽略计划的日期和时间。 此外，远程更新 Microsoft Teams 设备是美国政府云租户 (GCC-High) 尚不可用的功能。

若要管理设备，需要全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的详细信息，请参阅 [使用 Microsoft Teams 管理员角色来管理 Teams](../using-admin-roles.md)。

## <a name="choose-automatic-device-firmware-update-behavior"></a>选择自动设备固件更新行为

自动应用设备固件更新。 如果选择此选项，则可以在发布更新后的第一个周末或发布更新 30 或 90 天后，决定是否在 () 发布更新后立即应用更新。 默认情况下，设备固件更新在发布后 30 天内应用。

> [!IMPORTANT]
> 最新的固件更新版本未应用于 Teams 设备。 相反，在设备上自动应用的更新会被一个版本延迟。 例如，假设设备应用了版本“10”，并且版本“11”已发布。 版本“11”尚未应用。 相反，只有在版本“12”发布后，设备才会更新为版本“11”。

> [!NOTE]
> 某些设备尚不支持自动固件更新。 在不支持自动更新的设备上应用自动固件更新设置不会对这些设备产生任何影响。 有关设备是否支持自动固件更新的问题，请与设备制造商联系。

若要为设备选择自动更新行为，请执行以下操作：

1. 通过访问 https://admin.teams.microsoft.com登录到 Microsoft Teams 管理中心。
2. 导航 **Teams 设备** > **IP 电话** 、 **协作栏** 或 **Teams 面板**。
3. 选择一个或多个设备，然后选择 **“更新**”。
4. 在 **固件自动更新** 下，选择下列选项之一：
    - **一旦可用** 最新更新发布后的第一个周末将应用第二最新的设备固件更新。
    - **推迟 30 天** 最新更新发布 30 天后将应用第二新设备固件更新。
    - **推迟 90 天** 最新更新发布 90 天后，将应用第二新设备固件更新。
5. 选择 **“更新**”。

如果出于任何原因需要还原设备固件更新，则需要将设备重置为其出厂设置。 使用制造商的说明重置设备。  

## <a name="manually-update-remote-devices"></a>手动更新远程设备

使用管理中心更新一个或多个设备时，可以决定是立即更新设备，还是为将来的日期和时间安排更新。

若要手动更新远程设备，请执行以下操作：

1. 通过访问 https://admin.teams.microsoft.com登录到 Microsoft Teams 管理中心。
2. 导航  **Teams 设备** > **IP 电话** 、 **协作栏** 或 **Teams 面板**。
3. 选择一个或多个设备，然后选择 **“更新**”。
4. 在 **“手动更新**”下，如果要为将来的日期和时间计划更新，请选择“ **计划** ”。 更新在时区中选择的时 **区** 中的日期和时间应用。

你将看到的内容取决于是否选择了一个或多个设备。 下图显示了选择的多个设备，而右侧的图像显示所选的单个设备。

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图。":::

选择多个设备时，可以选择要应用于每个所选设备的更新类型。 选择要应用的更新类型，然后选择 **“更新**”。

选择单个设备时，会显示可用于设备的更新。 如果设备有多种更新类型，请选择要应用的每个更新类型。 可以查看在设备上应用的 **当前版本** 和将要应用 **的新版本** 。 选择要应用的更新 () 并选择 **“更新**”。

选择 **“更新**”后，如果计划了更新，更新会在所选日期和时间应用到设备。 如果未选择将来的日期和时间，则会在几分钟内将更新应用到设备。
