---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535d5d9a34d450c964300e9caaa16c6b80734732
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>配置受信任应用程序服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-11_

在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 Lync Server 2013 池。 在混合环境中，旧的 Lync Server 2010 池和 Lync Server 2013 池都将显示在下拉列表中。 此环境不支持选择旧池。

**创建受信任的应用程序服务器时，选择 Lync Server 2013 作为下一个跃点**

1.  打开拓扑生成器。

2.  在左窗格中，右键单击“受信任的应用程序服务器”****，然后单击“新建受信任的应用程序池”****。

3.  输入受信任应用程序池的“池 FQDN”****，选择该池是包含一台服务器还是多台服务器。

4.  单击“下一步”****。

5.  在 "**选择下一个跃点**" 页上的列表中，选择 "Lync Server 2013 前端池"。

6.  单击“完成”****。

7.  选择顶层节点“Lync Server”****，然后从“操作”**** 窗格中选择“发布”****。
    
    确认“受信任应用程序池”**** 已成功创建并且与正确的前端池关联。

</div>

<span> </span>

</div>

</div>

</div>

