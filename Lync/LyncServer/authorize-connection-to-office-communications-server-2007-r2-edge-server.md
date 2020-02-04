---
title: 授权到 Office 通信服务器 2007 R2 Edge 服务器的连接
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
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授权到 Office 通信服务器 2007 R2 Edge 服务器的连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

对于你的试点池中的每个 Lync Server 2013 前端服务器或标准版服务器，你必须更新授权连接到 Office 通信服务器 2007 R2 Edge 服务器的内部服务器的列表。 如果没有这些更新，通过使用旧版 Edge 服务器加入的用户的外部音频/视频（A/V）会议将不起作用。

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>授权到 Office 通信服务器 2007 R2 Edge 服务器的连接

1.  从 Office 通信服务器 2007 R2 Edge 服务器的 "**管理工具**" 组中，打开 "**计算机管理**" 管理单元。

2.  在控制台树中，展开 "**服务和应用程序**"。

3.  右键单击 " **Office 通信服务器 2007 R2**"，然后单击 "**属性**"。

4.  单击 "**内部**" 选项卡。

5.  在 "**添加服务器**" 下，单击 "**添加**"。

6.  在 "**添加 Office 通信服务器**" 对话框中，输入相应的信息：
    
      - 指定每个 Lync Server 2013 前端服务器或标准版服务器的完全限定的域名（FQDN），以及 Lync Server 2013 池。
    
      - 如果在通过其 FQDN 指定下一跃点计算机的池中配置了静态路由，请指定 Lync Server 2013 控制器的 FQDN。

7.  为每个 Lync Server 2013、前端服务器、标准版服务器、池和控制器添加条目后，单击 "**应用**"，然后单击 **"确定"** 以关闭 "属性" 页面。

</div>

</div>

<span> </span>

</div>

</div>

</div>

