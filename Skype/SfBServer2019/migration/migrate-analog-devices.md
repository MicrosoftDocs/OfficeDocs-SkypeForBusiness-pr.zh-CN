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
description: Skype for Business Server为模拟设备提供支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 可以将合格的网关配置为支持在 Skype for Business Server 环境中使用模拟设备。 迁移到 2019 Skype for Business Server之后，还必须迁移与模拟设备关联的联系对象。 使用Skype for Business Server命令行管理程序首先检索与旧模拟设备关联的所有联系对象，然后将这些对象移动到 Skype for Business Server 2019 池。
ms.openlocfilehash: 464531fcffbe251d6a0868e86b1b9edccc898fdeeb0963ed0f10c2b653dfe93b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337262"
---
# <a name="migrate-analog-devices"></a>迁移模拟设备

Skype for Business Server为模拟设备提供支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 可以将合格的网关配置为支持在 Skype for Business Server 环境中使用模拟设备。 迁移到 2019 Skype for Business Server之后，还必须迁移与模拟设备关联的联系对象。 使用Skype for Business Server命令行管理程序首先检索与旧模拟设备关联的所有联系对象，然后将这些对象移动到 Skype for Business Server 2019 池。

### <a name="to-migrate-analog-devices"></a>迁移模拟设备

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 在命令行中键入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 确认所有联系对象已移动到 Skype for Business Server 2019 池。 在命令行中键入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 验证所有联系对象现在是否与 Skype for Business Server 2019 池相关联。


