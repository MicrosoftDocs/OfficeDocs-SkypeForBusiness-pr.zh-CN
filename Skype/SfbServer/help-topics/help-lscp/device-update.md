---
title: 设备更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 定期为 Skype for business Phone Edition 发布一组新的设备固件更新，您可以将其导入到服务器并分发给用户。 通过转到 Microsoft 网站上的 "帮助和支持" 页面并搜索 forPhone 版本，你可以获取最新的设备更新规则集。下载最新的更新程序包，并将文件解压缩到要上载更新的计算机上的某个文件夹中。 解压缩文件后，可以使用 Import-CsDeviceUpdate cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅导入-CsDeviceUpdate。
ms.openlocfilehash: 066564a315fdda57e33ad62f8abfe8e5dbe931e1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700237"
---
# <a name="device-update"></a>设备更新

Microsoft 定期为 Skype for business Phone Edition 发布一组新的设备固件更新，您可以将其导入到服务器并分发给用户。 可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。 下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。 解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅[导入-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

导入设备更新规则后，您可以使用 "**设备更新**" 页面查看和管理组织设备的这些规则。

> [!TIP]
> 您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备更新**”页上执行以下任务：

- 批准列表中的设备更新。

- 取消或恢复挂起的设备更新。

- 从列表删除设备更新。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **编辑**可使用此选项执行下列操作：

  - **全选**此选项将选择列表中的所有设备更新。

  - **Delete**此选项将删除所有选定的设备更新。

- **操作**可以在列表中选择一个或多个更新，并执行以下操作：

  - **取消挂起的更新**此选项可防止将所选更新部署到你的组织的设备。

  - **批准**此选项允许将所选更新部署到你的组织的设备。

  - **还原**此选项允许将以前批准的更新部署到你的组织的设备

- **刷新**你可以刷新列表以验证所有设备更新的状态。

有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)。
## <a name="see-also"></a>另请参阅

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
