---
title: Lync Server 2013：创建设备以测试更新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67712f981d8061b8dd3c90de812092e01dc5d1b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>在 Lync Server 2013 中创建用于测试更新功能的设备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

可将测试设备添加到“测试设备”**** 页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 您可以在全局范围内（在整个 Lync Server 环境中）或在单个站点中测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 Lync Server 控制面板的 "**测试设备**" 页上的列表中。

<div>

## <a name="to-add-a-test-device"></a>添加测试设备

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“客户端”****，然后单击“测试设备”****。

3.  单击“新建”****，然后单击“全局测试设备”**** 或“站点测试设备”****。

4.  执行下列操作之一：
    
      - 如果单击了“全局测试设备”****，则跳到下一步。
    
      - 如果单击了“站点测试设备”****，则从可用站点列表中选择一个站点，然后单击“确定”****。

5.  在“新建测试设备”**** 上的“设备名称”**** 中，键入设备的名称。

6.  在“标识符类型”**** 下，单击“MAC 地址”**** 或“序列号”****。

7.  在“唯一标识符”**** 框中，键入设备的 MAC 地址或序列号。

8.  单击“提交”****。

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建测试设备

可以使用 Windows PowerShell 和 CsTestDevice cmdlet 创建测试设备。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

使用此 cmdlet 创建测试设备时，必须执行以下两个操作：

  - 指定 MACAddress 或 SerialNumber 为 IdentifierType。

  - 指定设备标识时包括作用域。要在全局作用域创建新设备，请使用类似如下的语法：
    
        -Identity "global/WindowsPhone"
    
    要在站点作用域创建测试设备，请使用类似如下的语法：
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>使用 MAC 地址创建测试设备

  - 以下命令在全局作用域创建测试设备，并使用 MAC 地址作为 IdentifierType：
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>使用序列号创建测试设备

  - 以下命令在站点作用域（对于 Redmond 站点）创建测试设备，并使用序列号作为 IdentifierType：
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

有关详细信息，请参阅[CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

