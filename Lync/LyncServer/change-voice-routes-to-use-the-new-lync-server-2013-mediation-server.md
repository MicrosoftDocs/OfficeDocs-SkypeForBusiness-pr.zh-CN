---
title: 将语音路由更改为使用新的 Lync Server 2013 中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898901690b1caf5d57b33ffaec7231080554cca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>将语音路由更改为使用新的 Lync Server 2013 中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

此过程会将语音路由更改为使用 Lync Server 2013 中介服务器, 而不是旧版 Office 通信服务器 2007 R2 中介服务器。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>将语音路由更改为使用新的中介服务器

1.  Lync Server 2013 控制面板

2.  在左窗格中, 选择 "**语音路由**", 然后选择 "**路由**"。

3.  单击 "**新建**" 以创建新的语音路由。

4.  填写以下字段:
    
      - **名称**: 键入语音路线的描述性名称。 对于本文档, 我们将使用**W15PSTNRoute**。
    
      - **说明**: 键入语音路线的简短说明。

5.  跳过其余所有分区, 直到您到达**相关网关**。 单击“添加”****。 选择新的默认网关, 然后单击 **"确定"**。

6.  在 "**关联的 PSTN 用法**" 下, 单击 "**选择**"。

7.  在 "**选择 PSTN 使用记录**" 页面上, 选择一个记录名称, 然后单击 **"确定"**。

8.  从新的 "**语音路由**" 页面上, 单击 **"确定"** 以创建**语音路由**。

9.  从 "**语音路由**" 页面上, 选择 "**传送**"。

10. 将新创建的路由移动到列表顶部, 然后选择 "**提交**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

