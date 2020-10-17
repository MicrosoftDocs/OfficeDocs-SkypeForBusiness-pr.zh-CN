---
title: 迁移呼叫寄存应用程序设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503559"
---
# <a name="migrate-call-park-application-settings"></a>迁移呼叫寄存应用程序设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

从 Lync Server 2010 到 Lync Server 2013 的呼叫寄存应用程序的迁移包括：预配 Lync Server 2013 池，其中包含已在 Lync Server 2010 中上载的任何自定义音乐 "保留" 文件，同时将服务级别设置和 retargeting 所有呼叫寄存轨道式还原到 Lync Server 2013 池。 如果已在 Lync Server 2010 池中配置了自定义的保持音乐的文件，则需要将这些文件复制到新的 Lync Server 2013 池。 此外，建议您将任何呼叫寄存自定义的音乐保留文件从 Lync Server 2010 备份到另一个目标，以保留为呼叫寄存上载的任何自定义的已保留音乐文件的单独备份副本。 呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。 若要将音频文件从 Lync Server 2010 池文件存储复制到 Lync Server 2013 文件存储，请使用 **Xcopy** 命令和以下参数：

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

将所有自定义音频文件复制到 Lync Server 2013 文件存储后，必须配置 Lync Server 2013 池的呼叫寄存应用程序设置，并且与 Lync Server 2010 池关联的呼叫寄存通道范围必须重新分配给 Lync Server 2013 池。

呼叫寄存应用程序设置包括应答超时阈值，启用或禁用保持音乐，最大呼叫应答尝试次数和超时请求。 您必须使用 Lync Server 命令行管理程序运行 **CsCpsConfiguration** cmdlet 来管理呼叫寄存应用程序设置。 您无法使用 Lync Server 控制面板管理呼叫寄存应用程序设置。

**重新配置呼叫寄存服务设置**

1.  在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
    <div>
    

    > [!NOTE]  
    > 如果你的 Lync Server 2013 呼叫寄存应用程序设置与旧版 Lync Server 2010 设置相同，则可以跳过运行此步骤。 如果 Lync Server 2013 和 Lync Server 2010 环境的呼叫寄存应用程序设置不同，请将下面的 cmdlet 用作模板以更新这些更改。

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```

若要将所有呼叫寄存通道范围从 Lync Server 2010 池重新分配到 Lync Server 2013 池，您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序。

**使用 Lync Server 控制面板重新分配所有呼叫寄存轨道范围**

1.  打开“Lync Server 控制面板”。

2.  在左窗格中，选择“语音功能”****。

3.  选择“呼叫寄存”**** 选项卡。

4.  对于分配给 Lync Server 2010 池的每个呼叫寄存通道范围，请编辑 " **目标服务器的 FQDN** " 设置，然后选择将处理呼叫寄存请求的 Lync Server 2013 池。

5.  单击“提交”**** 保存所做更改。

**使用 Lync Server 命令行管理程序重新分配所有呼叫寄存轨道范围**

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。 必须重新分配将 **CallParkServiceId** 和 **CallParkServerFqdn** 参数设置为 Lync Server 2010 池的所有呼叫寄存轨道。
    
    若要将 Lync Server 2010 呼叫寄存通道区域重新分配给 Lync Server 2013 池，请在命令行中键入以下命令：
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

将所有呼叫寄存通道区域重新分配给 Lync Server 2013 池之后，呼叫寄存应用程序的迁移过程将完成，Lync Server 2013 池将处理所有未来呼叫寄存请求。

</div>

<span> </span>

</div>

</div>

</div>

