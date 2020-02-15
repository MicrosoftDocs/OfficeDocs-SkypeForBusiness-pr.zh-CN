---
title: 迁移后更改简单 Url
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0d6666f4ea824d59a97eb1f63b66016c75d547
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 Url

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

Lync Server 支持三个简单的 Url：

  - ****“会议”用作站点或组织中所有会议的基 URL。 通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。

  - ****“拨入”允许访问“电话拨入式会议设置”网页。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。

  - **管理员**可以快速访问 Lync Server 控制面板。 管理简单 URL 是组织内部的。

在迁移到 Lync Server 2013 之后，您必须了解更改如何影响简单 Url 的 DNS 记录和证书。 如果旧版 Lync Server 2010 控制器在拓扑中仍处于使用中，则不需要对简单 Url 进行任何更改。 如果在迁移后从拓扑中删除了 Lync Server 2010 控制器，则必须将简单 URL DNS 记录更新为指向某个 Lync Server 2013 池。 但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，以注册该更改。

<div>

## <a name="changing-simple-urls-after-migration"></a>迁移后更改简单 Url

**更新 "符合简单 URL"**

1.  在拓扑生成器中，右键单击顶部节点**Lync Server**，然后单击 "**编辑属性**"。

2.  在左窗格中选择 "**简单 url** "，然后单击 "**会议 url"：** 选择 "满足 url"，然后单击 "**编辑 URL**"。

3.  将 URL 更新为所需的值，然后单击“确定”**** 保存已编辑的 URL。

**更新管理员简单 URL**

1.  在拓扑生成器中，右键单击顶部节点**Lync Server**，然后单击 "**编辑属性**"。

2.  在左窗格中选择 "**简单 url** "，然后在 "**管理访问 URL** " 框下，输入要用于对 Lync Server 2013 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。
    
    <div>
    

    > [!TIP]  
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的方法是<STRONG> https://admin。</STRONG>&lt;域&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划简单 Url](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

