---
title: 测试设备
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 Skype for Business Server 控制面板的"测试设备"页上的列表中。
ms.openlocfilehash: a8f8183974556caf11873597425ebc156701ddbc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120261"
---
# <a name="test-device"></a>测试设备

可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 Skype for Business  Server 控制面板的"测试设备"页上的列表中。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“测试设备”页上执行以下任务：

- 在全局范围或为特定站点添加测试设备。

- 修改现有测试设备的选项。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新建** 你可以添加具有以下作用域的新测试设备：

  - 全局

  - Site

- **编辑** 你可以更改列表中的测试设备选项。 使用此选项，可以执行以下操作：

  - **显示详细信息** 此选项将打开一个对话框，可在其中更改测试设备的选项。

  - **全选** 此选项选择列表中的所有测试设备。

  - **删除** 此选项将删除所有选定的测试设备。

- **刷新** 你可以刷新测试设备列表以验证所有测试设备的选项状态。

有关测试设备的详细信息，请参阅操作文档中的[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)。
## <a name="see-also"></a>另请参阅

[测试设备：创建新的或编辑现有的](ms.lync.lscp.ClientDeviceTestEdit.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[查看组织中设备的软件更新](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)