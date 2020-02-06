---
title: 测试设备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在全局范围（在整个环境中）或在单个站点中测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 "Skype for Business 服务器" 控制面板的 "测试设备" 页面上的列表中。
ms.openlocfilehash: ea6d0e74bf72a8887b3c6cd0f9c46e503af316fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822044"
---
# <a name="test-device"></a>测试设备

可将测试设备添加到“**测试设备**”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在全局范围（在整个环境中）或在单个站点中测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 "Skype for Business 服务器" 控制面板的 "**测试设备**" 页面上的列表中。

## <a name="tasks-you-can-perform"></a>可执行的任务

可以在 "**测试设备**" 页面上执行以下任务：

- 全局添加测试设备或为特定网站添加测试设备。

- 修改现有测试设备的选项。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新**你可以添加具有以下范围的新测试设备：

  - 全局

  - 站点

- **编辑**可以在列表中更改测试设备的选项。 使用此选项，您可以执行以下操作：

  - **显示详细信息**此选项将打开一个对话框，你可以在其中更改测试设备的选项。

  - **全选**此选项将选择列表中的所有测试设备。

  - **Delete**此选项将删除所有选定的测试设备。

- **刷新**你可以刷新测试设备列表，以验证所有测试设备的选项的状态。

有关测试设备的详细信息，请参阅操作文档中的[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)。
## <a name="see-also"></a>另请参阅

[测试设备：创建新的或编辑现有的](test-device-create-new-or-edit-existing.md)

[新-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[查看组织中的设备的软件更新](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
