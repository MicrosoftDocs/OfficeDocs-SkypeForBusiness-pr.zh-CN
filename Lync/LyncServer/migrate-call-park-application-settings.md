---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

将 Lync Server 2010 中的呼叫驻留应用程序迁移到 Lync Server 2013 包括预配 Lync Server 2013 池, 其中包含已在 Lync Server 2010 中上载的任何自定义音乐暂停文件, 还原服务级别设置和 retargeting所有呼叫公园轨道式到 Lync Server 2013 池。 如果已在 Lync Server 2010 池中配置了自定义的 "已保留的音乐" 文件, 则需要将这些文件复制到新的 Lync Server 2013 池。 此外, 建议您将任何呼叫寄存自定义的 "Lync Server 2010" 文件从 Lync Server 备份到另一个目的地, 以保留针对呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 用于呼叫寄存应用程序的自定义的 "保留式音乐" 文件存储在该池的文件存储中。 若要将音频文件从 Lync Server 2010 池文件存储复制到 Lync Server 2013 文件存储, 请使用带有以下参数的**Xcopy**命令:

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

当所有自定义音频文件已复制到 Lync Server 2013 文件存储时, 必须配置 Lync Server 2013 池的 "呼叫驻留" 应用程序设置, 并且与 Lync Server 2010 池中关联的呼叫寄存轨道范围必须重新分配给Lync Server 2013 池。

"呼叫驻留" 应用程序设置包括 "装货超时阈值"、"启用" 或 "禁用暂停的音乐"、最大的呼叫装货尝试和超时请求。 你必须使用 Lync Server Management Shell 运行**CsCpsConfiguration** cmdlet 来管理调用寄存应用程序设置。 无法使用 Lync Server 控制面板管理 "呼叫驻留" 应用程序设置。

**重新配置呼叫寄存服务设置**

1.  从 Lync Server 2013 前端服务器, 打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
    <div>
    

    > [!NOTE]  
    > 如果您的 Lync Server 2013 调用寄存应用程序设置与旧版 Lync Server 2010 设置相同, 则可以跳过运行此步骤。 如果对于 Lync Server 2013 和 Lync Server 2010 环境, 调用寄存应用程序设置不同, 请将以下 cmdlet 用作模板以更新这些更改。

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

要将所有呼叫公园轨道范围从 Lync Server 2010 池中重新分配到 Lync Server 2013 池, 您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序。

**使用 Lync Server 控制面板重新分配所有呼叫寄存的 "轨道" 范围**

1.  打开“Lync Server 控制面板”。

2.  在左窗格中, 选择 "**语音功能**"。

3.  选择 "**呼叫驻留**" 选项卡。

4.  对于分配给 Lync Server 2010 池的每个呼叫寄存轨道范围, 请编辑 "**目标服务器的 FQDN** " 设置, 然后选择将处理呼叫寄存请求的 Lync Server 2013 池。

5.  选择 "**提交**" 以保存更改。

**使用 Lync Server 命令行管理程序重新分配所有呼叫寄存的轨道范围**

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsCallParkOrbit
    
    此 cmdlet 列出部署中的所有呼叫寄存轨道范围。 必须重新分配将**CallParkServiceId**和**CallParkServerFqdn**参数设置为 Lync Server 2010 池的所有呼叫寄存 "轨道式"。
    
    若要将 Lync Server 2010 调用寄存轨道范围重新分配给 Lync Server 2013 池, 请在命令行键入以下命令:
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

将所有调用寄存轨道范围重新分配给 Lync Server 2013 池后, 将完成呼叫寄存应用程序的迁移过程, 并且 Lync Server 2013 池将处理所有未来呼叫驻留请求。

</div>

<span> </span>

</div>

</div>

</div>

