---
title: Lync Server 2013：对 Lync VDI 插件进行故障排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad67f17f3d12f72472ee8ddbc0e7605cf58dab52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>在 Lync Server 2013 中对 Lync VDI 插件进行故障排除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>解决在瘦客户端上安装 Lync VDI 插件时出现的问题

如果在瘦客户端上安装 VDI 插件时出现问题，请检查以下几点：

  - 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。

  - 确保已关闭写保护。有关说明，请参阅设备制造商的文档。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>排除配对问题

当 VDI 插件配对失败时，右下方的配对图标将显示为红色的“X”，如图所示：

![显示成功配对的 Lync VDI 图标](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "显示成功配对的 Lync VDI 图标")

以下是出现故障的可能原因以及可以采取的更正措施。

  - **用户在登录期间输入错误凭据。**
    
    用户应注销 Lync，然后使用正确的凭据重新登录。 配对对话框将重新出现，并显示配对是否成功。

  - **另一个远程桌面客户端的实例正在运行。**
    
    如果他们使用的是 Windows 中的远程桌面连接，则用户应执行以下操作：
    
    1.  启动任务管理器：按“Alt+Ctrl+Delete”****，然后单击“启动任务管理器”****。
    
    2.  单击“进程”**** 选项卡并在列表中查找名为“mstsc.exe”**** 的所有进程。
    
    3.  突出显示每个“mstsc.exe”**** 进程，然后单击“结束进程”****。
    
    4.  启动新远程桌面会话并尝试再次连接。

  - **必要的文件未正确安装。**
    
    将插件安装在本地计算机上后，下列文件应显示在 C：\\Program Files\\Microsoft Office\\Office15 （或相应的驱动器号）下：
    
      - LyncVdiPlugin
    
      - UcVdi
    
    如果 VDI 配对出现任何问题，请检查以确保本地计算机上显示这些文件。

  - **Lync 客户端正在本地计算机上运行。**
    
    若要使用 Lync VDI 插件，Lync 客户端不得在本地计算机上运行，否则配对将会失败。 最佳做法是，用户不应在本地计算机上安装 Lync 客户端。

</div>

</div>

<span> </span>

</div>

</div>

</div>

