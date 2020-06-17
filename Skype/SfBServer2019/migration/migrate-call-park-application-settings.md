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
description: 呼叫寄存应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义音乐 "保留" 文件，并将所有呼叫寄存轨道式还原到 Skype for Business Server 2019 池。 如果已在池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外，建议您将任何呼叫寄存自定义的即用音乐文件从另一个目标备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用 Xcopy 命令和以下参数：
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752814"
---
# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

呼叫寄存应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义的音乐文件，还原服务级别设置并将所有呼叫寄存轨道式重新定向到 Skype for Business Server 2019 池。 如果已在池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外，建议您将任何呼叫寄存自定义的即用音乐文件备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for Business Server 2019 文件存储，请使用**Xcopy**命令和以下参数： 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

将所有自定义音频文件复制到 Skype for business Server 2019 文件存储后，必须配置 Skype for business Server 2019 池的呼叫寄存应用程序设置，并且与旧版池关联的呼叫寄存通道范围必须重新分配给 Skype for business Server 2019 池。

呼叫寄存应用程序设置包括装货超时阈值、启用或禁用保留的音乐、最大呼叫尝试次数和超时请求。 您必须通过使用 Skype for Business Server 命令行管理程序运行**CsCpsConfiguration** cmdlet 来管理呼叫寄存应用程序设置。 您无法使用 Skype for Business Server 控制面板管理呼叫寄存应用程序设置。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新配置呼叫寄存服务设置

1. 在 Skype for Business Server 2019 前端服务器中，打开 Skype for Business Server 命令行管理程序。

2. 在命令行中键入：

    > [!NOTE]
    > 如果 Skype for Business Server 2019 呼叫寄存应用程序设置与旧设置相同，则可以跳过此步骤。 如果 Skype for business Server 2019 和旧版环境的呼叫寄存应用程序设置不同，请将下面的 cmdlet 用作模板以更新这些更改。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

若要将所有呼叫寄存通道范围从旧版池重新分配到 Skype for Business Server 2019 池，可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板重新分配所有呼叫寄存通道范围

1. 打开 "Skype for Business Server 控制面板"。

2. 在左窗格中，选择“语音功能”****。

3. 选择“呼叫寄存”**** 选项卡。 

4. 对于分配给旧版池的每个呼叫寄存通道范围，请编辑 "**目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Skype For business server 2019 池。 

5. 单击“提交”**** 保存所做更改。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序重新分配所有呼叫寄存通道范围

1. 打开 Skype for Business Server 命令行管理程序。

2. 在命令行中键入：

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。 将**CallParkServiceId**和**CallParkServerFqdn**参数设置为旧版池的所有呼叫寄存轨道都必须重新分配。 

    若要将旧式呼叫寄存通道范围重新分配给 Skype for Business Server 2019 池，请在命令行中键入以下命令：

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

将所有呼叫寄存通道区域重新分配给 Skype for Business Server 2019 池后，呼叫寄存应用程序的迁移过程将完成，Skype for Business Server 2019 池将处理所有将来的呼叫寄存请求。


