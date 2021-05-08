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
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 了解如何管理组织中用于Teams的设备。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41213955c9e57829208ce0ec98448195dc266044
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50350600"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理设备

可以从管理中心管理Microsoft Teams组织中用于Microsoft Teams设备。 可以查看和管理组织的设备清单，以及执行更新、重启和监视设备的诊断等任务。 还可以创建配置文件并将其分配到设备或设备组。

若要管理设备，例如更改设备配置、重启设备、管理更新或查看设备和外围设备运行状况，需要分配以下Microsoft 365角色之一：

- Microsoft 365全局管理员
- Teams服务管理员
- Teams设备管理员

有关管理员角色在 Teams 中Teams，请参阅使用 Teams[管理员角色来管理Teams。](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？

可以管理通过认证并注册的任何设备，Teams。 用户首次登录设备时，会自动注册Teams设备。 有关可管理的已认证设备的列表，请参阅：

- [协作栏](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [会议电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [桌面电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams 会议室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams显示器](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams面板](teams-panels.md)

若要管理设备，请在管理中心左侧导航 [Microsoft Teams，转到](https://admin.teams.microsoft.com)"**设备**"，然后选择设备类型。 每种类型的设备都有自己的相应部分，可让你单独管理它们。

## <a name="manage-teams-rooms-devices"></a>管理Teams 会议室设备

可以使用 Teams 管理中心查看和远程管理Teams 会议室整个组织的设备。 使用 Teams 管理中心，可以轻松一目了然地查看哪些设备运行状况良好以及哪些需要关注，并让你专注于特定设备以查看有关设备运行状况、会议性能、呼叫质量和外围设备的详细信息。 

下面是一些可用于管理设备Teams 会议室操作。 Teams 会议室设备"下的"Microsoft Teams [管理中心](https://admin.teams.microsoft.com)**"中**  >  Teams 会议室。

若要详细了解如何管理 Teams 会议室 设备，请参阅[管理Microsoft Teams 会议室。](../rooms/rooms-manage.md)

| 为此...                          | 执行此操作                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改一台或多台设备上的设置 | 选择一个或多个设备 **>"设置"。** 如果选择多个设备，则更改的值将替换所有选定设备上的值。                                                                                                                                                                                                                       |
| 重启设备                        | 选择一个或多个设备>**重启"。** 重新启动设备时，可以选择是立即重启设备，还是选择"计划重启"以在特定的日期和时间重启设备。 选择的日期和时间是正在重启的设备的本地日期和时间。                                                                                            |
| 查看会议活动                  | 选择设备名称以打开"活动"> **详细信息**。 打开" **活动"** 选项卡时，可以看到设备已参与的所有会议。 此摘要视图显示会议开始时间、参与者数、持续时间和总体呼叫质量。                                                                                        |
| 查看会议详细信息                   | 选择设备名称以打开设备详细信息> **活动>** 选择会议。 打开会议的详细信息时，可以看到会议的所有参与者、他们在呼叫中的时间、Teams类型及其个人呼叫质量。 如果要查看有关参与者通话的技术信息，请选择参与者的通话开始时间。 |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>管理电话、协作栏Teams显示器和Teams面板 

在 Teams 管理中心中，可以查看和管理组织中Teams中注册Teams的电话、协作栏、Teams面板。 你将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。 可以自定义视图以显示符合需求的信息。

如果已注册Teams，Teams手机、协作栏、Teams面板会自动注册到 Microsoft Intune 中。 注册设备后，确认设备符合性，将条件访问策略应用到设备。

下面举例说明如何管理组织中电话、协作栏Teams和Teams面板。  

| 为此...                           | 执行此操作                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 更改设备信息               | 选择设备>**编辑"。** 可以编辑详细信息，例如设备名称、资产标记和添加注释。                                                                                                                                                                                                              |
| 管理软件更新                 | 选择设备>**更新"。** 可以查看适用于设备的软件和固件更新列表，并选择要安装的更新。 有关更新设备的信息，请参阅远程[Teams设备](remote-update.md)                                                          |
| 将Teams手机升级到Teams显示器  | 在 **"IP 电话**"页上，选择一个或多个Teams">**升级"。** 此选项仅适用于支持升级到显示器Teams手机。 若要了解有关详细信息，请参阅[将Teams升级到 Teams 显示器](upgrade-phones-to-displays.md)。                                                      |
| 分配或更改配置策略 | 在"分配配置"> **一个或多个设备**。                                                                                                                                                                                                                                                       |
| 添加或删除设备标记               | 选择一个或多个设备>**管理标记"。** 有关设备标记详细信息，请参阅[管理Teams标记](manage-device-tags.md)。                                                                                                                                                                 |
| 重启设备                         | 选择一个或多个设备>**重启"。**                                                                                                                                                                                                                                                                    |
| 使用设备标记筛选设备        | 选择筛选器图标，选择"**标记"** 字段，指定要筛选的设备标记，然后选择"应用 **"。** 有关使用设备标记筛选设备的信息，请参阅使用筛选器返回 [具有特定标记的设备](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 查看设备历史记录和诊断     | 在"**历史记录"** 列下，单击设备的"查看"链接以查看其更新历史记录和诊断详细信息。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>使用 Teams 中的配置文件

使用配置文件管理组织中不同 Teams 设备的设置和功能，包括协作栏、Teams、Teams和Teams面板。 可以创建或上传配置文件以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备集。 

#### <a name="create-a-configuration-profile"></a>创建配置文件

若要为设备类型创建Teams配置文件：

1. 在左侧导航栏中，转到"设备 **">选择** Teams"配置>**类型"。** 例如，选择 **"设备**  >  **"Teams"** 配置文件"，为面板创建新的  >  配置文件Teams配置文件。
2. 单击“**添加**”。
3. 输入配置文件的名称，并选择性地添加友好说明。
4. 指定配置文件的设置，然后单击"保存 **"。**
   新创建的配置文件显示在配置文件列表中。

#### <a name="assign-a-configuration-profile"></a>分配配置文件
为设备类型Teams配置文件后，将其分配给一个或多个设备。

1. 在左侧导航栏中，转到"**设备**>选择Teams类型。 例如，若要将配置文件分配给 Teams面板设备，请选择"Teams  >  **面板"。**
2. 选择一个或多个设备，并单击"**分配配置"。**  
3. 在 **"分配配置"** 窗格中，搜索要分配给所选设备的配置文件。
4. 单击“**应用**”。
   对于已应用配置策略的设备，"操作"列显示 **"配置** 更新"，"**配置文件**"列显示配置文件名称。 
