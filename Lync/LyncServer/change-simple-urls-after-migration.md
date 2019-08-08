---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811296efc12badd61d148b7dbd60a3489e74a747
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-22_

Lync 服务器支持三个简单的 Url:

  - "**开会**" 用作网站或组织中的所有会议的基本 URL。 通过 "满足简单 URL", 加入会议的链接易于理解, 并且易于沟通和分发。

  - 通过**拨入功能**, 可以访问 "电话拨入式会议设置" 网页。 拨入式简单 URL 包含在所有会议邀请中, 以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。

  - **管理员**可快速访问 Lync Server 控制面板。 管理员简单的 URL 是您的组织内部的。

迁移到 Lync Server 2013 后, 必须知道更改对简单 Url 的 DNS 记录和证书有何影响。 如果旧版 Lync Server 2010 控制器在拓扑中保持使用, 则不需要对您的简单 Url 进行任何更改。 如果在迁移后从拓扑中删除了 Lync Server 2010 控制器, 则必须更新简单 URL DNS 记录以指向其中一个 Lync Server 2013 池。 但是, 当您更改简单的 URL 名称时, 必须在每个 Director 和前端服务器上运行 Enable-CsComputer 以注册更改。

<div>

## <a name="changing-simple-urls-after-migration"></a>迁移后更改简单的 Url

**更新 "满足简单 URL"**

1.  在拓扑生成器中, 右键单击顶部节点**Lync 服务器**, 然后单击 "**编辑属性**"。

2.  在左窗格中选择 "**简单 url** ", 然后单击 "**会议 url":** 选择 "满足 url", 然后单击 "**编辑 URL**"。

3.  将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。

**更新管理员简单 URL**

1.  在拓扑生成器中, 右键单击顶部节点**Lync 服务器**, 然后单击 "**编辑属性**"。

2.  在左窗格中选择 "**简单 url** ", 然后在 "**管理访问 URL** " 框下方输入要用于管理对 Lync Server 2013 控制面板的简单 URL, 然后单击 **"确定"**。
    
    <div>
    

    > [!TIP]  
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项是<STRONG> https://admin。</STRONG>&lt;域&gt;。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

