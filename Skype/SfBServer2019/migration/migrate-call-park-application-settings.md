---
title: 迁移呼叫寄存应用程序设置
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
description: 呼叫保留应用程序的迁移包括为 Skype for Business Server 2019 池设置已在旧安装中上载的任何自定义保持音乐文件、还原服务级别设置以及将所有呼叫保留通道重新定向到 Skype for Business Server 2019 池。 如果在池中配置了自定义保持音乐文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池中。 此外，建议您将任何呼叫保留音乐自定义文件从另一个目标备份到另一个目标，以保留为呼叫保留上载的任何自定义保持音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用带下列参数的 Xcopy 命令：
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312320"
---
# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

呼叫保留应用程序的迁移包括为 Skype for Business Server 2019 池设置已在旧安装中上载的任何自定义保持音乐文件、还原服务级别设置以及将所有呼叫保留通道重新定向到 Skype for Business Server 2019 池。 如果在池中配置了自定义保持音乐文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池中。 此外，建议您将任何呼叫保留自定义保持音乐文件备份到另一个目标，以保留为呼叫保留上载的任何自定义保持音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用带下列参数的 **Xcopy** 命令： 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

当所有自定义音频文件都复制到 Skype for Business Server 2019 文件存储时，必须配置 Skype for Business Server 2019 池的呼叫保留应用程序设置，并且必须将与旧池关联的呼叫保留通道范围重新分配给 Skype for Business Server 2019 池。

呼叫保留应用程序设置包括分拣超时阈值、启用或禁用保持音乐、最大呼叫接听尝试次数和超时请求。 必须使用命令行管理程序管理呼叫Skype for Business Server运行 **Set-CsCpsConfiguration** cmdlet。 不能使用控制面板管理呼叫Skype for Business Server设置。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新配置呼叫寄存服务设置

1. 从 Skype for Business Server 2019 前端服务器中，打开 Skype for Business Server 命令行管理程序。

2. 在命令行中键入：

    > [!NOTE]
    > 如果您的 2019 Skype for Business Server 2019 呼叫管理应用程序设置与旧设置相同，可以跳过此步骤。 如果 2019 和旧环境中呼叫Skype for Business Server应用程序设置不同，请使用下面的 cmdlet 作为模板来更新这些更改。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

若要将旧池的所有呼叫Skype for Business Server范围重新分配给 Skype for Business Server 2019 池，可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>使用控制面板重新分配所有呼叫Skype for Business Server范围

1. 打开Skype for Business Server控制面板"。

2. 在左窗格中，选择“语音功能”。

3. 选择“呼叫寄存”选项卡。 

4. 对于分配给旧池的每个呼叫库通道范围，编辑目标服务器的 **FQDN** 设置并选择将处理呼叫库请求的 Skype for Business Server 2019 池。 

5. 单击“提交”保存所做更改。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>使用命令行管理程序重新分配所有呼叫Skype for Business Server范围

1. 打开Skype for Business Server命令行管理程序"。

2. 在命令行中键入：

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。 必须重新分配将 **CallParkServiceId** 和 **CallParkServerFqdn** 参数设置为旧池的所有呼叫保留通道。 

    若要将旧呼叫Skype for Business Server范围重新分配给 Skype for Business Server 2019 池，在命令行中键入以下内容：

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

将所有呼叫库通道范围重新分配给 Skype for Business Server 2019 池后，将完成呼叫库应用程序的迁移过程，并且 Skype for Business Server 2019 池将处理所有将来的呼叫库请求。


