---
title: 迁移模拟设备
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务服务器为模拟设备提供支持。 具体而言，受支持的模拟设备将模拟音频电话和模拟传真机。 您可以配置合格网关以支持在您 Skype 业务服务器环境中使用模拟设备。 您迁移到 Skype 业务服务器 2019年后，您还必须迁移相关联的模拟设备联系对象。 使用 Skype 的业务 Server Management Shell，以先检索所有联系对象相关联的旧的模拟设备，然后将这些对象移动到业务服务器 2019年池 Skype。
ms.openlocfilehash: ea100f4e26cc38d5eb30f881de61bf415110ca36
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374848"
---
# <a name="migrate-analog-devices"></a>迁移模拟设备

Skype 业务服务器为模拟设备提供支持。 具体而言，受支持的模拟设备将模拟音频电话和模拟传真机。 您可以配置合格网关以支持在您 Skype 业务服务器环境中使用模拟设备。 您迁移到 Skype 业务服务器 2019年后，您还必须迁移相关联的模拟设备联系对象。 使用 Skype 的业务 Server Management Shell，以先检索所有联系对象相关联的旧的模拟设备，然后将这些对象移动到业务服务器 2019年池 Skype。

### <a name="to-migrate-analog-devices"></a>迁移模拟设备

1. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。

2. 在命令行中键入：

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 验证的所有联系对象已移至 Skype 业务服务器 2019年池。 在命令行中键入：

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 验证所有联系对象现在是否与业务服务器 2019年池 Skype 关联。


