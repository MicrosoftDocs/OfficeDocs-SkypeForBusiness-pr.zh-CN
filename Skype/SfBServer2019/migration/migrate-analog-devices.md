---
title: 迁移模拟设备
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 为模拟设备提供支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 您可以配置合格的网关，以支持在 Skype for Business Server 环境中使用模拟设备。 迁移到 Skype for business Server 2019 后，还必须迁移与模拟设备关联的 contact 对象。 使用 Skype for Business Server 命令行管理程序先检索与旧模拟设备关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752824"
---
# <a name="migrate-analog-devices"></a>迁移模拟设备

Skype for Business Server 为模拟设备提供支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 您可以配置合格的网关，以支持在 Skype for Business Server 环境中使用模拟设备。 迁移到 Skype for business Server 2019 后，还必须迁移与模拟设备关联的 contact 对象。 使用 Skype for Business Server 命令行管理程序先检索与旧模拟设备关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。

### <a name="to-migrate-analog-devices"></a>迁移模拟设备

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。

2. 在命令行中键入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 验证是否已将所有 contact 对象移动到 Skype for Business Server 2019 池。 在命令行中键入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 验证所有联系人对象现在是否与 Skype for Business Server 2019 池相关联。


