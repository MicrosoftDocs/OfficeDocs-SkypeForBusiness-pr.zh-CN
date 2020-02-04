---
title: 预配要运行加载的拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>预配要运行加载的拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>预配要运行加载的拓扑

你可能需要在你的环境中进行以下更改，具体取决于 Lync Server 2013 的现有设置和配置：

1.  将 Windows PowerShell 执行策略设置为 "无限制"。 若要检查执行策略设置，请打开 Lync Server 命令行管理程序，然后运行以下命令：

    ``` powershell
        Get-ExecutionPolicy
    ```        

    如果此命令不会返回不受限制的值，请运行以下命令：

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  若要有效配置 Lync Server 2013，您需要：
    
      - 熟悉 Lync Server 2013 拓扑（例如，计算机名称、服务实例、站点名称和策略）。
    
      - 将已创建的某些用户分配给组，例如 "响应组查寻组" （例如 SIP Uri）。

3.  若要从命令行运行脚本，您可以使用：

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  通常，在此程序包中的某个脚本运行后，脚本生成的跟踪将存储在一个文件中，该文件位于调用脚本的同一路径中，名为\<scriptname\>$h $ m $ s .txt。 例如，在 12:15 P.M. 运行 ArchivingPolicy。 将生成一个日志文件，如 ArchivingPolicy121500。

5.  最后，请注意，虽然我们提供了配置服务器的示例，但你负责在运行完加载后修改或删除配置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

