---
title: 设备更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 会定期发布 Skype for Business Phone Edition 的新设备固件更新集，你可以将其导入服务器并分发给用户。 可以通过访问 Microsoft 网站的"帮助和支持"页并搜索Phone Edition 来获取一组最新的设备更新规则。下载最新的更新程序包，将文件解压缩到要上载更新的计算机上的文件夹。 解压缩文件后，可以使用 Import-CsDeviceUpdate cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅 Import-CsDeviceUpdate。
ms.openlocfilehash: e98d414c66c6d4400d1bf2de88158859e57b93a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115270"
---
# <a name="device-update"></a>设备更新

Microsoft 会定期发布 Skype for Business Phone Edition 的新设备固件更新集，你可以将其导入服务器并分发给用户。 可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。 下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。 解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅 [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

导入设备更新规则后，可以使用"设备更新"页查看和管理组织的设备的这些规则。

> [!TIP]
> 您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“设备更新”页上执行以下任务：

- 批准列表中的设备更新。

- 取消或恢复挂起的设备更新。

- 从列表删除设备更新。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **编辑** 可以使用此选项执行以下操作：

  - **全选** 此选项选择列表中的所有设备更新。

  - **删除** 此选项将删除所有选定的设备更新。

- **操作** 可以选择列表中的一个或多个更新，并执行以下操作：

  - **取消挂起的更新** 此选项可阻止将所选更新部署到组织的设备。

  - **批准** 此选项允许将所选更新部署到组织的设备。

  - **还原** 此选项允许将以前批准的更新部署到组织的设备

- **刷新** 你可以刷新列表以验证所有设备更新的状态。

有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)。
## <a name="see-also"></a>另请参阅

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)