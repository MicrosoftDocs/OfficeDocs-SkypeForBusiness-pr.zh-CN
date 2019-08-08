---
title: 在 Microsoft Teams 中管理设备
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: 了解如何管理组织中与团队一起使用的设备。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b259b893f443a068b8156f2298613b0feb6d028
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237499"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理设备

::: zone target="docs"
作为管理员, 你可以通过 Microsoft 团队 & Skype for business 管理中心管理组织中的团队使用的所有设备。 你可以查看和管理你的组织的设备清单, 并执行一些任务, 如更新、重启和监视设备诊断。 你还可以创建配置文件并将其分配给设备或设备组。 

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？
设备必须经过认证, 才能供团队和注册团队。 当用户第一次登录设备上的团队时, 将自动注册设备。 有关可管理的认证设备的列表, 请参阅[电话会议](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)和[桌面电话](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)。

> [!NOTE]
> 如果你有 Microsoft Intune, 则会在 Intune 中自动注册设备。 注册设备后, 将确认设备合规性, 并将条件访问策略应用到设备。 

## <a name="manage-devices-in-teams"></a>管理团队中的设备

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 转到 "**设备** > **管理设备**"。
2. 选择 "**所有设备**"。  

::: zone-end

 从这里, 您可以查看和管理您的组织中的团队注册的所有设备。 您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。 你可以自定义视图以显示符合你的需求的信息。

 下面是有关如何管理组织中的团队设备的一些示例。  
    
|若要执行此操作 .。。  |执行此操作 |
|---------|---------|
|更改设备信息   | 选择 >**编辑**的设备。 你可以编辑设备名称、用户信息、资产标记和添加笔记等详细信息。     |
|管理软件更新   |选择 >**更新**的设备。 你可以查看适用于该设备的软件和固件更新的列表, 并选择要安装的更新。    |
|重启设备   |选择 >**重新启动**的设备。          |
|查看设备历史记录  | 选择一个设备 >**历史记录**。 你可以查看设备的更新历史记录。     |
|查看诊断  | 选择一个设备 >**诊断**。        |

## <a name="use-configuration-profiles-in-teams"></a>使用团队中的配置文件

使用配置文件管理组织中团队设备的设置和功能。 你可以创建或上载配置文件, 以包含要启用或禁用的设置和功能, 然后将配置文件分配给设备或设备组。 

### <a name="create-a-configuration-profile"></a>创建配置文件

::: zone target="docs"

![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) 使用 Microsoft 团队 & Skype for Business 管理中心

1. 在左侧导航中, 转到 "**设备** > **管理设备**"。

::: zone-end

2. 选择 "**配置文件**", 然后选择 "**新建配置文件**"。
3. 输入配置文件的名称, 如果需要, 请添加一个友好描述。
4. 为配置文件指定所需的设置, 然后单击 "**保存**"。

### <a name="assign-a-configuration-profile"></a>分配配置文件

::: zone target="docs"

![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) 使用 Microsoft 团队 & Skype for Business 管理中心

1. 在左侧导航中, 转到 "**设备** > **管理设备**"。

::: zone-end

2. 选择**配置文件**, 然后在要分配的配置文件中的 "**分配给**" 下, 单击该链接。  
3. 在 "**将设备分配给配置文件**窗格" 中, 搜索并选择要分配的设备。
4. 单击“**保存**”。
