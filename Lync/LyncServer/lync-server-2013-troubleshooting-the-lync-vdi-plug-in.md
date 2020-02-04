---
title: Lync Server 2013：疑难解答 Lync VDI 插件
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
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>在 Lync Server 2013 中对 Lync VDI 插件进行故障排除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>解决在瘦客户端上安装 Lync VDI 插件时遇到的问题

如果在瘦客户端上安装 VDI 插件时出现问题，请检查以下事项：

  - 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。

  - 确保已关闭写保护。有关说明，请参阅设备制造商的文档。

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>排除在配对时出现的问题

当 VDI 插件配对失败时，右下角的配对图标将显示为红色的 "X"，如下所示：

![Lync VDI 图标显示成功配对](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI 图标显示成功配对")

以下是失败的可能原因以及可以执行的纠正操作。

  - **用户在登录期间输入的凭据不正确。**
    
    用户应注销 Lync，然后使用正确的凭据再次登录。 配对对话框将重新出现，并显示配对是否成功。

  - **远程桌面客户端的另一个实例正在运行。**
    
    如果他们使用的是 Windows 中的远程桌面连接，则用户应该执行以下操作：
    
    1.  启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。
    
    2.  单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。
    
    3.  突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。
    
    4.  启动新的远程桌面会话并再次尝试连接。

  - **未正确安装必要的文件。**
    
    在本地计算机上安装插件后，以下文件应存在于 C：\\Program 文件\\Microsoft Office\\Office15 （或相应的驱动器号）下：
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    如果 VDI 配对存在任何问题，请检查以确保本地计算机上存在这些文件。

  - **Lync 客户端正在本地计算机上运行。**
    
    若要使用 Lync VDI 插件，Lync 客户端不能在本地计算机上运行，否则配对将失败。 最佳做法是，用户不应在本地计算机上安装 Lync 客户端。

</div>

</div>

<span> </span>

</div>

</div>

</div>

