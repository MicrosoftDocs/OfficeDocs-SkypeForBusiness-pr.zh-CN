---
title: 在 Microsoft Teams 中管理设备
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 了解如何管理组织中与团队一起使用的设备。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587298"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理设备

作为管理员，你可以管理来自 Microsoft 团队管理中心的组织中的团队使用的设备。 你可以查看和管理你的组织的设备清单，并执行一些任务，如更新、重启和监视设备诊断。 你还可以创建配置文件并将其分配给设备或设备组。 

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？
你可以管理已认证且已注册团队的任何设备。 当用户第一次登录设备上的团队时，将自动注册设备。 有关可管理的认证设备的列表，请参阅：

- [会议电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [桌面电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- 协作栏

在左侧导航中的 "**设备**" 下的 " [Microsoft 团队管理中心](https://admin.teams.microsoft.com)" 中管理设备。

> [!NOTE]
> 如果你有 Microsoft Intune，则会在 Intune 中自动注册设备。 注册设备后，将确认设备合规性，并将条件访问策略应用到设备。

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>管理团队中的电话和协作栏

尽管在 Microsoft 团队管理中心中，手机和协作栏的管理方式相同，但它们在左侧导航中的 "**设备**" 下有各自的分区。 这使你可以单独管理每种类型的设备。

从这里，您可以查看和管理您的组织中的团队注册的电话和协作栏。 您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。 你可以自定义视图以显示符合你的需求的信息。

下面是有关如何管理组织中的团队设备的一些示例。  
    
|若要执行此操作 .。。  |执行此操作 |
|---------|---------|
|更改设备信息   | 选择 >**编辑**的设备。 你可以编辑设备名称、资产标记和添加笔记等详细信息。     |
|管理软件更新   |选择 >**更新**的设备。 你可以查看适用于该设备的软件和固件更新的列表，并选择要安装的更新。    |
|重启设备   |选择 >**重新启动**的设备。          |
|查看设备历史记录  | 选择一个设备 >**历史记录**。 你可以查看设备的更新历史记录。     |
|查看诊断  | 选择一个设备 >**诊断**。        |

## <a name="use-configuration-profiles-in-teams"></a>使用团队中的配置文件

使用配置文件管理组织中团队设备的设置和功能。 你可以创建或上载配置文件，以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备组。 

### <a name="create-a-configuration-profile"></a>创建配置文件

1. 在左侧导航中，转到 "**设备** > **配置文件**"。
2. 单击“添加”****。
3. 输入配置文件的名称，如果需要，请添加一个友好描述。
4. 为配置文件指定所需的设置，然后单击 "**保存**"。

### <a name="assign-a-configuration-profile"></a>分配配置文件

1. 在左侧导航中，转到 "**设备** > **配置文件**"。
2. 选择要分配的**配置文件**，然后单击 "**分配给设备**"。  
3. 在 "**将设备分配给配置文件**窗格" 中，搜索并选择要分配的设备。
4. 单击“**保存**”。
