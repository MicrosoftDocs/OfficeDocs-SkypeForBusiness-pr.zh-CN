---
title: Lync Server 2013：呼叫者 ID 演示
description: Lync Server 2013：呼叫者 ID 演示。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 651c9c8da8b6a1ed13669255008ca639a90e1806
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565188"
---
# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中的呼叫者 ID 演示

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

在 Lync Server 2010 中，被叫方的电话号码 (也就是说，呼叫) 的电话号码可以从 e.164 格式转换为中继 (对等方所需的本地拨号格式，即关联网关、专用分支 exchange (PBX) 或 SIP 中继) 。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

Lync Server 2013 还介绍了如何将呼叫方的电话号码转换 (也就是说，呼叫者拨打的电话号码从) 的电子号码格式到中继对等方所需的本地拨号格式。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

<div id="sectionSection0" class="section">

**使用 Lync Server 控制面板配置呼叫者 ID 的具体方法**

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。

4.  在“Trunk 配置”**** 页上，双击一个现有中继（例如，“全局”**** 中继）以显示“编辑 Trunk 配置”**** 对话框。

5.  配置呼叫者 ID 显示：
    
      - 要从企业语音部署中提供的所有转换规则列表中选择一个或多个规则，请单击 **“选择”**。 在“主叫号码转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    
      - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 有关定义新规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。
    
      - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。 有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。 有关详细信息，请参阅 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。
    
    <div>
    

    > [!WARNING]  
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

