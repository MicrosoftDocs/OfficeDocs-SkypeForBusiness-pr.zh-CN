---
title: 授权与 Office 通信服务器 2007 R2 边缘服务器的连接
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db737eae5ec02a015fac3a894b5f19079743c4c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授权与 Office 通信服务器 2007 R2 边缘服务器的连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

对于您的引导池中的每个 Lync Server 2013 前端服务器或 Standard Edition server，必须更新已授权连接到 Office 通信服务器 2007 R2 边缘服务器的内部服务器的列表。 如果不进行这些更新，则用户使用旧边缘服务器加入的外部音频/视频 (A/V) 会议将不起作用。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授权与 Office 通信服务器 2007 R2 边缘服务器的连接

1.  从 "Office 通信服务器 2007 R2 边缘服务器" 的 "**管理工具**" 组中，打开 "**计算机管理**" 管理单元。

2.  在控制台树中，展开“服务和应用程序”****。

3.  右键单击“Office Communications Server 2007 R2”****，然后单击“属性”****。

4.  单击“内部”**** 选项卡。

5.  在“添加服务器”**** 下，单击“添加”****。

6.  在“添加 Office Communications Server”**** 对话框中，输入相应信息：
    
      - 指定每个 Lync Server 2013 前端服务器或 Standard Edition server，以及 Lync Server 2013 池的完全限定域名（FQDN）。
    
      - 如果已在通过其 FQDN 指定下一跃点计算机的池中配置了静态路由，请指定 Lync Server 2013 控制器的 FQDN。

7.  为每个 Lync Server 2013、前端服务器、Standard Edition Server、pool 和 Director 添加了一个条目后，单击 "**应用**"，然后单击 **"确定"** 以关闭 "属性" 页。

</div>

</div>

<span> </span>

</div>

</div>

</div>

