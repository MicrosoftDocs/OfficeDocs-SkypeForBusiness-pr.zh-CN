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
description: 了解如何管理组织中与团队一起使用的设备。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49032986"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理设备

你可以从 Microsoft 团队管理中心管理你的组织中的 Microsoft 团队使用的设备。 你可以查看和管理你的组织的设备清单，并执行一些任务，如更新、重启和监视设备诊断。 你还可以创建配置文件并将其分配给设备或设备组。

若要管理设备（如更改设备配置、重启设备、管理更新或查看设备和外围设备运行状况），您需要分配以下 Microsoft 365 管理员角色之一：

- Microsoft 365 全局管理员
- 团队服务管理员
- 团队设备管理员

有关团队中的管理员角色的详细信息，请参阅 [使用团队管理员角色管理团队](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>可以管理哪些设备？

你可以管理已认证且已注册团队的任何设备。 当用户第一次登录设备上的团队时，将自动注册设备。 有关可管理的认证设备的列表，请参阅：

- [Microsoft Teams 会议室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [会议电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [桌面电话](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [团队显示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [协作栏](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

若要管理设备，请在 [Microsoft 团队管理中心](https://admin.teams.microsoft.com)的左侧导航中，转到 " **设备** "，然后选择设备类型。 每种类型的设备都有其各自的分区，可供您单独管理。

## <a name="manage-teams-rooms-devices"></a>管理团队聊天室设备

你可以使用团队管理中心在你的组织内查看和远程管理团队聊天室设备。 团队管理中心使你可以轻松查看哪些设备运行正常，哪些设备需要引起注意，让你专注于特定设备以查看有关设备运行状况、会议性能、呼叫质量和外围设备的详细信息。 

下面是可用于管理团队聊天室设备的一些操作。 团队聊天室设备可在 " **设备** 团队" 会议室下的 " [Microsoft 团队管理中心](https://admin.teams.microsoft.com)" 中找到  >  **Teams Rooms** 。

有关如何管理团队聊天室设备的详细信息，请参阅 [管理 Microsoft 团队聊天室](../rooms/rooms-manage.md)。

| 若要执行此操作 .。。 | 要执行的操作|
|---------------|--------|
| 在一个或多个设备上更改设置 | 选择一个或多个设备 > " **编辑设置** "。 如果你选择多个设备，你更改的值将替换所有选定设备上的值。 |
| 重启设备 | 选择一个或多个设备 > **重启** 。 重新启动设备时，可以选择是立即重新启动设备，还是选择 " **计划重启** " 以在特定日期和时间重启设备。 您选择的日期和时间对重新启动的设备而言是本地的。|
| 查看会议活动 | 选择设备名称以打开 "设备详细信息" > " **活动** "。 打开 " **活动** " 选项卡时，你可以看到设备参与的所有会议。 此摘要视图显示会议开始时间、参与者数、持续时间和整体通话质量。|
| 查看会议详细信息 |  选择设备名称以打开 "设备详细信息" > " **活动** " > 选择会议。 当您打开会议的详细信息时，您可以查看会议中的所有参与者、通话时间、团队授课类型以及个人通话质量。 如果您想要查看有关参与者的通话的技术信息，请选择参与者的通话开始时间。|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>管理手机、协作栏和团队显示 

在 "团队管理中心" 中，您可以查看和管理手机、协作栏和团队显示组织中已注册的团队。 您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。 你可以自定义视图以显示符合你的需求的信息。

如果已注册手机、协作栏和团队显示，则会在 Microsoft Intune 中自动注册。 注册设备后，将确认设备合规性，并将条件访问策略应用到设备。

下面是如何管理你的组织中显示的电话、协作栏和团队的一些示例。  

|若要执行此操作 .。。  |要执行的操作 |
|---------|---------|
| 更改设备信息               | 选择 > **编辑** 的设备。 你可以编辑设备名称、资产标记和添加笔记等详细信息。     |
| 管理软件更新                 | 选择 > **更新** 的设备。 你可以查看适用于该设备的软件和固件更新的列表，并选择要安装的更新。 有关更新设备的详细信息，请参阅 [远程更新团队设备](remote-update.md)   |
| 将团队的电话升级到团队显示                | 在 " **IP 电话** " 页面上，选择一个或多个团队的电话 > **升级** 。 此选项仅适用于支持升级到团队的电话。 若要了解详细信息，请参阅 [将团队手机升级到团队显示](upgrade-phones-to-displays.md)。   |
| 分配或更改配置策略 | 选择一个或多个设备 > " **分配配置** "。                                                                                                                                                                                                                   |
| 添加或删除设备标记               | 选择一个或多个设备 > **管理标记** 。 有关设备标记的详细信息，请参阅 [管理团队设备标记](manage-device-tags.md)。                                                                                                      |
| 重启设备                         | 选择一个或多个设备 > **重启** 。                                                                                                                                                                                                                                |
| 使用设备标签筛选设备        | 选择 "筛选器" 图标，选择 " **标记** " 字段，指定要筛选的设备标记，然后选择 " **应用** "。 有关使用设备标记对设备进行筛选的详细信息，请参阅 [使用筛选器返回具有特定标记的设备](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。|
| 查看设备历史记录                     | 选择一个设备 > **历史记录** 。 你可以查看设备的更新历史记录。                                                                                                                                                                                |
| 查看诊断                        | 选择一个设备 > **诊断** 。                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>使用团队中的配置文件

使用配置文件管理组织中的团队电话和协作栏的设置和功能。 你可以创建或上载配置文件，以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备组。 

#### <a name="create-a-configuration-profile"></a>创建配置文件

1. 在左侧导航中，转到 " **设备**  >  **配置文件** "。
2. 单击“添加”。
3. 输入配置文件的名称，如果需要，请添加一个友好描述。
4. 为配置文件指定所需的设置，然后单击 " **保存** "。

#### <a name="assign-a-configuration-profile"></a>分配配置文件

1. 在左侧导航中，转到 " **设备**  >  **配置文件** "。
2. 选择要分配的 **配置文件** ，然后单击 " **分配给设备** "。  
3. 在 " **将设备分配给配置文件** 窗格" 中，搜索并选择要分配的设备。
4. 单击“ **保存** ”。

