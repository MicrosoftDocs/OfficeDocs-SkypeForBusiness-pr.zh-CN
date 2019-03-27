---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 呼叫寄存应用程序包括设置为与保留文件中旧安装已上载的任何自定义保持音乐的业务服务器 2019年池 Skype 迁移，还原的服务级别设置和重定目标所有呼叫寄存轨道到业务服务器 2019年池的 Skype。 如果在池中已配置自定义的保留音乐文件，这些文件需要复制到新 Skype 业务服务器 2019年池。 此外，建议您备份任何呼叫寄存自定义保留音乐文件从至其他目标保留一份任何自定义保留音乐文件已上载的呼叫寄存的单独备份。 呼叫寄存应用程序的自定义的保留音乐文件存储在文件存储的池。 若要从一个池的文件存储的音频文件复制到 Skype 业务服务器 2019年文件存储，请与以下参数使用 Xcopy 命令：
ms.openlocfilehash: 3d9c2904d66ac5d35bdd94631ec23c67288a5c3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887621"
---
# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

呼叫寄存应用程序的迁移包括设置 Skype 业务服务器 2019年池与旧 install，还原的服务级别设置和重新设定所有呼叫寄存轨道已上载的任何自定义保留音乐文件为业务服务器 2019年池 Skype。 如果在池中已配置自定义的保留音乐文件，这些文件需要复制到新 Skype 业务服务器 2019年池。 此外，建议您备份任何呼叫寄存自定义保留音乐文件至其他目标保留一份任何自定义保留音乐文件已上载的呼叫寄存的单独备份。 呼叫寄存应用程序的自定义的保留音乐文件存储在文件存储的池。 若要从一个池的文件存储的音频文件复制到 Skype 业务服务器 2019年文件存储，请与以下参数使用**Xcopy**命令： 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

当所有自定义音频文件已复制到业务服务器 2019年文件存储的 Skype 时，必须配置池，业务服务器 2019年 Skype 的呼叫寄存应用程序设置和呼叫寄存通道范围与旧池关联的必须重新分配给业务服务器 2019年池 Skype。

呼叫寄存应用程序设置包括分拣超时阈值，启用或禁用音乐、 最大呼叫分拣次数和超时请求。 您必须通过使用 Business Server 命令行管理程序 Skype 运行**Set-cscpsconfiguration** cmdlet 来管理呼叫寄存应用程序设置。 您无法管理用于业务 Server Control Panel Skype 的呼叫寄存应用程序设置。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新配置呼叫寄存服务设置

1. 从业务 Server 2019 前端服务器的 Skype，打开业务 Server 命令行管理程序 Skype。

2. 在命令行中键入：

    > [!NOTE]
    > 如果您的业务服务器 2019年呼叫寄存应用程序设置的 Skype 到旧设置相同，则可以跳过此步骤。 如果呼叫寄存应用程序设置的不同而不同业务服务器 2019年和旧环境 Skype，使用下面的 cmdlet 为模板更新这些更改。 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

要重新分配所有呼叫寄存轨道范围从旧池中到业务服务器 2019年池 Skype，可以为业务 Server 命令行管理程序中使用的业务 Server Control Panel Skype 或 Skype。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>重新分配所有呼叫寄存轨道范围 Skype 用于业务 Server Control Panel

1. 打开 Skype 业务 Server Control Panel。

2. 在左窗格中，选择**语音功能**。

3. 选择**呼叫寄存**选项卡。 

4. 对于分配给旧池的每个呼叫寄存通道范围，编辑**目标服务器的 FQDN**设置并选择将处理呼叫寄存请求的业务服务器 2019年池 Skype。 

5. 选择**提交**以保存所做的更改。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>重新分配所有呼叫寄存轨道范围 Skype 用于业务 Server 命令行管理程序

1. 打开 Skype 业务 Server 命令行管理程序。

2. 在命令行中键入：

   ```
   Get-CsCallParkOrbit
   ```

    此 cmdlet 列出所有部署中的呼叫寄存通道范围。 必须重新分配所有呼叫寄存轨道已设置为旧池的**CallParkServiceId**和**CallParkServerFqdn**参数。 

    若要重新分配旧的呼叫寄存轨道范围到业务服务器 2019年池，请在命令行中的 Skype 键入以下命令：

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

后重新分配到业务服务器 2019年池 Skype 的所有呼叫寄存轨道范围，将完成迁移过程的呼叫寄存应用程序和业务服务器 2019年池 Skype 将用来处理所有将来的呼叫寄存请求。


