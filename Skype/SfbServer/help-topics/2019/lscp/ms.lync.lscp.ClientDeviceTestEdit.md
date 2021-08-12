---
title: 测试设备创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: 测试设备功能与设备更新功能结合使用。 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在控制面板的"测试设备"Skype for Business Server列表中。
ms.openlocfilehash: 73f56f0ef008fe603b44055d1ad2b48086c9d0b49d3200877bc0545f945dc315
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279300"
---
# <a name="test-device-create-new-or-edit-existing"></a>测试设备：创建新的或编辑现有的

测试设备功能与设备更新功能结合使用。 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在控制面板的"测试设备 **"Skype for Business Server列表中**。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“新建测试设备”或“编辑测试设备”页上执行以下任务：

- 添加新的测试设备。

- 修改现有测试设备的属性。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **范围** 标识测试 (全局) 站点范围。

- **名称** 你可以添加或修改测试设备的名称。

- **设备名称** 你可以添加或修改测试设备的名称。

- **标识符类型** 通过选择下列选项之一，可以选择用于标识设备的方法：

  - **MAC 地址**

  - **序列号**

- **唯一标识符** 可以键入设备的 MAC 地址或序列号。

有关测试设备的详细信息，请参阅操作文档中的[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)。
## <a name="see-also"></a>另请参阅

[测试设备](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[查看组织中设备的软件更新](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)