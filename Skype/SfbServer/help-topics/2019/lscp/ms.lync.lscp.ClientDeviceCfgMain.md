---
title: 设备日志配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织数据管理策略的一部分，您可能想要设置阈值日志数据缓存大小、 日志文件大小或的日志文件在被清除之前保留的时间长度。 您可以更改这些设置根据贵组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: 8fe17b65e4070c312876a6b8f03679b24288e304
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891864"
---
# <a name="device-log-configuration"></a>设备日志配置

设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织数据管理策略的一部分，您可能想要设置阈值日志数据缓存大小、 日志文件大小或的日志文件在被清除之前保留的时间长度。 您可以更改这些设置根据贵组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。

> [!NOTE]
> 您还可以配置一次您希望自动删除早于天数的日志文件的设备更新 Web 服务的一天中的配置要保留日志文件 （默认情况下，即超过 10 天的日志文件） 的服务。 不能用于业务 Server Control Panel Skype 修改此设置。 相反，您必须为业务 Server 命令行管理程序中使用 Skype。 若要指定一天中删除过期的日志文件的时间，请使用-LogCleanUpTimeOfDay 参数**New-csdeviceupdateconfiguration** cmdlet。 有关详细信息，请参阅[New-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备日志配置**”页上执行以下任务：

- 在全局范围或针对特定站点或池添加设备日志配置。

- 修改现有设备日志配置的选项。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新**您可以添加新的设备日志配置具有以下作用域：

  - 全局

  - 站点

- **编辑**您可以更改设备日志配置列表中的选项。 使用此选项，可以执行以下操作：

  - **显示详细信息**此选项可打开一个对话框，您可以在其中更改设备日志配置的选项。

  - **选择全部**此选项可选择列表中所有设备日志配置。

  - **删除**此选项可删除所有选定的设备日志配置。

- **刷新**您可以刷新设备日志配置列表以验证所有设备日志配置的选项状态。

## <a name="see-also"></a>另请参阅

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
