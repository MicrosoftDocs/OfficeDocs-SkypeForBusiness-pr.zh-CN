---
title: 将语音路由更改为使用新的 Lync Server 2013 中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4998057543f6695104ecbe759135b6735160c23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>将语音路由更改为使用新的 Lync Server 2013 中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

此过程将语音路由更改为使用 Lync Server 2013 中介服务器，而不是旧版 Office 通信服务器 2007 R2 中介服务器。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>将语音路由更改为使用新中介服务器

1.  Lync Server 2013 控制面板

2.  在左窗格中，选择“语音路由”****，然后选择“路由”****。

3.  单击“新建”**** 以创建新语音路由。

4.  填写以下字段：
    
      - **名称**：键入语音路由的描述性名称。在本文档中，我们使用 **W15PSTNRoute**。
    
      - **说明**：键入语音路由的简要说明。

5.  跳过所有其余部分，直到到达“关联网关”****。单击“添加”****。选择新默认网关，然后单击“确定”****。

6.  在“关联的 PSTN 用法”**** 下，单击“选择”****。

7.  从“选择 PSTN 用法记录”**** 页中，选择一个记录名称，然后单击“确定”****。

8.  从“新建语音路由”**** 页中，单击“确定”**** 以创建“语音路由”****。

9.  从“语音路由”**** 页中，选择“路由”****。

10. 将新创建的路由移至列表的顶部，然后选择“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

