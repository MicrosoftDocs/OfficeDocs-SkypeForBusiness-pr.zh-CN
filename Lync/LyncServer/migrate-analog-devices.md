---
title: 迁移模拟设备
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70e756fdaa49fc4c825a2c8548eb2c7f2e4acab2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>迁移模拟设备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

Lync Server 提供对模拟设备的支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 您可以配置合格的网关，以支持在 Lync Server 环境中使用模拟设备。 从 Lync Server 2010 迁移到 Lync Server 2013 之后，您还必须迁移与模拟设备关联的 contact 对象。 使用 Lync Server 命令行管理程序先检索与 Lync Server 2010 模拟设备关联的所有 contact 对象，然后将这些对象移至 Lync Server 2013 池。

<div>

## <a name="to-migrate-analog-devices"></a>迁移模拟设备

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  验证是否已将所有 contact 对象移动到 Lync Server 2013 池。 在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  确认所有联系人对象现在都与 Lync Server 2013 池相关联。

</div>

</div>

<span> </span>

</div>

</div>

</div>

