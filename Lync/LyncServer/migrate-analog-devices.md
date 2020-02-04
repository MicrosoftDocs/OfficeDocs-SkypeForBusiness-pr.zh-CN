---
title: 迁移模拟设备
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>迁移模拟设备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-16_

Lync 服务器提供模拟设备的支持。 具体说来，受支持的模拟设备是模拟音频电话和模拟传真计算机。 你可以配置合格的网关以支持在 Lync Server 环境中使用模拟设备。 从 Lync Server 2010 迁移到 Lync Server 2013 后，您还必须迁移与模拟设备相关联的联系人对象。 使用 Lync Server Management Shell 首先检索与 Lync Server 2010 模拟设备关联的所有联系人对象，然后将这些对象移动到 Lync Server 2013 池。

<div>

## <a name="to-migrate-analog-devices"></a>迁移模拟设备

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  验证是否已将所有联系人对象移动到 Lync Server 2013 池。 在命令行中键入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  验证所有联系人对象现在是否与 Lync Server 2013 池相关联。

</div>

</div>

<span> </span>

</div>

</div>

</div>

