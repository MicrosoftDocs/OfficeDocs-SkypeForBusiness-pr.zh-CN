---
title: 设备日志配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分，你可能想要在日志文件的数据缓存大小、日志文件大小或清除日志文件前的时间段内设置阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: d0f054f4c9209b552f1f084efab73f0750aefb18
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686845"
---
# <a name="device-log-configuration"></a>设备日志配置

设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分，你可能想要在日志文件的数据缓存大小、日志文件大小或清除日志文件前的时间段内设置阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。

> [!NOTE]
> 你还可以配置你希望设备更新 Web 服务自动删除早于你配置了服务以保留日志文件的天数（默认情况下是超过10天的日志文件）的日志文件的时间。 无法使用 Skype for Business Server 控制面板修改此设置。 而必须使用 Skype for Business Server 命令行管理程序。 若要指定每天删除已过期日志文件的时间，请将**CsDeviceUpdateConfiguration** cmdlet 与-LogCleanUpTimeOfDay 参数配合使用。 有关详细信息，请参阅[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备日志配置**”页上执行以下任务：

- 在全局范围或针对特定站点或池添加设备日志配置。

- 修改现有设备日志配置的选项。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新**你可以添加具有以下范围的新设备日志配置：

  - 全局

  - 站点

- **编辑**可以在列表中更改设备日志配置的选项。 使用此选项，您可以执行以下操作：

  - **显示详细信息**此选项将打开一个对话框，您可以在其中更改设备日志配置的选项。

  - **全选**此选项选择列表中的所有设备日志配置。

  - **Delete**此选项将删除所有选定的设备日志配置。

- **刷新**你可以刷新设备日志配置列表，以验证所有设备日志配置的选项状态。

## <a name="see-also"></a>另请参阅

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
