---
title: 设备日志配置
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分，您可能需要设置日志数据缓存大小、日志文件 大小或 日志文件 在清除之前保留的时间长度的阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: cd9227d16e06d221a0c997787d906001d57c2f33
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757388"
---
# <a name="device-log-configuration"></a>设备日志配置

设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为组织的数据管理策略的一部分，您可能需要设置日志数据缓存大小、日志文件 大小或 日志文件 在清除之前保留的时间长度的阈值。 您可以根据组织的要求更改这些设置。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。

> [!NOTE]
> 您还可以配置一天中您希望设备更新 Web 服务自动删除超过您配置该服务保留日志文件 (的天数的日志文件（即超过) 年 10 天的日志文件）的时间。 无法使用"控制面板"Skype for Business Server修改此设置。 相反，必须使用命令行管理Skype for Business Server命令行管理程序。 若要指定删除过期日志文件的时间，请使用 **New-CsDeviceUpdateConfiguration** cmdlet 和 -LogCleanUpTimeOfDay 参数。 有关详细信息，请参阅 [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“设备日志配置”页上执行以下任务：

- 在全局范围或针对特定站点或池添加设备日志配置。

- 修改现有设备日志配置的选项。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新建** 你可以添加具有以下作用域的新设备日志配置：

  - 全球

  - Site

- **编辑** 你可以更改列表中的设备日志配置选项。 使用此选项，可以执行以下操作：

  - **显示详细信息** 此选项将打开一个对话框，可在其中更改设备日志配置的选项。

  - **全选** 此选项选择列表中的所有设备日志配置。

  - **删除** 此选项将删除所有选定的设备日志配置。

- **刷新** 你可以刷新设备日志配置列表以验证所有设备日志配置的选项状态。

## <a name="see-also"></a>另请参阅

[修改设备更新活动的日志文件的设置](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)