---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>迁移公共区域电话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-29_

常见的区域电话是指通常位于共享工作区或通用区域（如大厅、厨房或工厂地板）的 IP 电话。 常用的区域电话无需连接到计算机即可提供 Lync Server UC 功能。 将 Lync Server 2010 部署迁移到 Lync Server 2013 之后，您还必须迁移与旧式公共区域电话相关联的联系人对象。 使用 Lync Server 管理外壳程序将首先检索与 Lync Server 2010 公共区域电话相关联的所有联系人对象，然后将这些对象移动到 Lync Server 2013 池。

**迁移公共区域电话**

1.  从 Lync Server 2013 前端服务器，打开 Lync Server 命令行管理程序。

2.  在命令行中，键入以下内容：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要验证所有联系人对象是否已被移动到 Lync Server 2013 池，请从 Lync Server Management Shell 键入以下内容：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    验证所有联系人对象现在是否与 Lync Server 2013 池相关联。

</div>

<span> </span>

</div>

</div>

</div>

