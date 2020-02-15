---
title: Lync Server 2013：在虚拟机上登录和使用 Lync 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e530f24150bac692717cefb2412712bf3bf8dd1c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>在虚拟机上登录和使用 Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

启用 VDI 插件后，当用户登录 Lync 2013 时，将执行以下步骤。

1.  用户在运行在虚拟机上的 Lync 2013 客户端中键入他或她的凭据。

2.  Lync 检测到 VDI 插件的可用性后，Lync 将提示用户重新输入其凭据。 在此对话框中，建议用户选中“保存我的密码”**** 复选框以在后续登录期间不需要输入凭据。

3.  Lync 会开始对 VDI 插件配对。 配对完成之前，客户端将在 Lync 状态栏中显示两个图标。 左下方的图标指示没有可用的音频设备，而右下角的闪烁图标指示 VDI 配对正在进行中，如下所示：
    
    ![显示成功配对的 Lync VDI 图标](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "显示成功配对的 Lync VDI 图标")  

4.  VDI 配对成功后，这两个图标将更改为分别指示将用于呼叫的音频设备和 VDI 配对成功：
    
    ![显示成功的 Lync VDI 配对图标](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "显示成功的 Lync VDI 配对图标")  

5.  在 Lync 对使用 VDI 插件后，用户可以在连接到本地计算机的 Lync 兼容设备上看到他或她的状态。 用户现在可以正常发出和应答呼叫。

</div>

<span> </span>

</div>

</div>

</div>

