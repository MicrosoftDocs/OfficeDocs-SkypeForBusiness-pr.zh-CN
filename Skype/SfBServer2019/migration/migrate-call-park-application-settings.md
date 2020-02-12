---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 此呼叫驻留应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义音乐 "暂停" 文件，还原服务级别设置和 retargeting 所有呼叫公园轨道式Skype for Business Server 2019 池。 如果已在池中配置了自定义的 "已保留的音乐" 文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外，建议将任何呼叫寄存自定义的 "外出时" 文件从另一个目的地备份到另一个目的地，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for business Server 2019 文件存储，请使用 Xcopy 命令和以下参数：
ms.openlocfilehash: 058f2f1652dcb7c05730fd058e9867a4c2dee8af
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888131"
---
# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

呼叫驻留应用程序的迁移包括预配 Skype for Business Server 2019 池，其中包含已在旧安装中上载的任何自定义的音乐暂停文件，还原服务级别设置并重新定向所有呼叫寄存的轨道式Skype for business Server 2019 池。 如果已在池中配置了自定义的 "已保留的音乐" 文件，则需要将这些文件复制到新的 Skype for Business Server 2019 池。 此外，建议您将任何呼叫寄存自定义的 "已保留的音乐" 文件备份到另一个目的地，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。 若要将音频文件从池文件存储复制到 Skype for business Server 2019 文件存储，请使用**Xcopy**命令和以下参数： 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

将所有自定义音频文件复制到 Skype for business Server 2019 文件存储时，必须配置 Skype for business Server 2019 池的 "呼叫驻留" 应用程序设置，以及与旧版池相关联的 "呼叫驻留" 轨道范围必须重新分配给 Skype for Business Server 2019 池。

"呼叫驻留" 应用程序设置包括 "装货超时阈值"、启用或禁用 "暂停的音乐"、"呼叫最多尝试次数" 和 "超时请求"。 你必须通过使用 Skype for Business Server Management Shell 运行**CsCpsConfiguration** cmdlet 来管理 "呼叫驻留" 应用程序设置。 无法使用 Skype for Business Server 控制面板管理呼叫寄存应用程序设置。 

## <a name="reconfigure-the-call-park-service-settings"></a>重新配置呼叫寄存服务设置

1. 从 Skype for business 服务器2019前端服务器，打开 Skype for business 服务器命令行管理程序。

2. 在命令行中键入：

    > [!NOTE]
    > 如果您的 Skype for Business Server 2019 调用寄存应用程序设置与旧设置相同，则可以跳过此步骤。 如果 Skype for business Server 2019 和旧版环境中的 "调用寄存" 应用程序设置不同，请将以下 cmdlet 用作模板以更新这些更改。 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

若要将所有呼叫公园轨道范围从旧版池重新分配到 Skype for business Server 2019 池，可以使用 Skype for Business 服务器控制面板或 Skype for business 服务器命令行管理程序。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板重新分配所有呼叫寄存的 "轨道范围"

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左窗格中，选择 "**语音功能**"。

3. 选择 "**呼叫驻留**" 选项卡。 

4. 对于分配给旧版池的每个呼叫寄存轨道范围，请编辑 "**目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Skype For business server 2019 池。 

5. 选择 "**提交**" 以保存更改。 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序重新分配所有呼叫寄存的轨道范围

1. 打开 Skype for Business Server 命令行管理程序。

2. 在命令行中键入：

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    此 cmdlet 列出部署中的所有呼叫寄存轨道范围。 所有设置为旧版池的 CallParkServiceId 和**CallParkServerFqdn**参数的所有调用寄存的**** 都必须重新分配。 

    若要将旧式呼叫公园轨道范围重新分配给 Skype for business Server 2019 池，请在命令行键入以下命令：

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

将所有呼叫公园轨道范围重新分配给 Skype for business Server 2019 池后，将完成呼叫寄存应用程序的迁移过程，并且 Skype for Business Server 2019 池将处理所有未来呼叫寄存请求。


