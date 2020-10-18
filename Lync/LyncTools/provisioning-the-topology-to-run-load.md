---
title: 设置要运行负载的拓扑
description: 设置要运行负载的拓扑。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da482fde949675acc1722305433b95b7a6a6b523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578408"
---
# <a name="provisioning-the-topology-to-run-load"></a>设置要运行负载的拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-04_

<div>

根据您现有的 Lync Server 2013 的设置和配置，您可能需要在您的环境中进行以下更改：

1.  将 Windows PowerShell 执行策略设置为无限制。 若要检查执行策略设置，请打开 Lync Server 命令行管理程序，并运行以下命令：

    ``` powershell
        Get-ExecutionPolicy
    ```        

    如果此命令不会返回不受限制的值，请运行以下命令：

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  若要有效配置 Lync Server 2013，您将需要：
    
      - 熟悉 Lync Server 2013 拓扑 (例如，计算机名称、服务实例、站点名称和策略) 。
    
      - 将一些已创建的用户分配给组，如 "响应组" 智能组 (例如，SIP Uri) 。

3.  若要从命令行运行脚本，您可以使用：

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  通常，在此包中的一个脚本运行之后，脚本生成的跟踪将存储在一个文件中，该文件与从中调用脚本的同一路径，名为 \<scriptname\> $h $ m $s.txt。 例如，运行 ArchivingPolicy.ps1 下午12:15 点。 将生成日志文件，如 ArchivingPolicy121500.txt。

5.  最后，请注意，虽然我们提供了配置服务器的示例，但您负责在运行完负载后修改或删除配置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

