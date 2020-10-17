---
title: Lync Server 2013：编辑或配置简单 Url
description: Lync Server 2013：编辑或配置简单 Url。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551628"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中编辑或配置简单 Url

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-04_

此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。

Lync Server 2013 使用简单 Url 将内部和外部呼叫定向到前端服务器或控制器上的服务（如果已部署）。 有关简单 Url 的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md) 。 您可以从多个选项中选择简单 Url 的格式。 有关这些选项的详细信息，请参阅规划文档中的 [Lync Server 2013 中的简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md) 。

默认情况下，将按 (的形式配置简单 Url，例如，拨入简单 URL) ： https://dialin 。\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>配置简单 URL

1.  在拓扑生成器中，右键单击 " **Lync Server** " 节点，然后单击 " **编辑属性**"。

2.  在 " **简单 url** " 窗格中，选择 " **电话访问 url"：** (拨入) 或 **会议 url：** (") " 以进行编辑，然后单击 " **编辑 URL**"。

3.  将 URL 更新为所需的值，然后单击“确定”**** 保存已编辑的 URL。 此处显示的示例修改了拨入 URL https://pool01.contoso.net/dialin 。

4.  如有必要，使用相同的步骤编辑会议 URL。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>定义可选的管理简单 URL

1.  在拓扑生成器中，右键单击 " **Lync Server** " 节点，然后单击 " **编辑属性**"。

2.  在 " **管理访问 URL** " 框中，输入要用于对 Lync Server 2013 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。
    
    <div>
    

    > [!TIP]  
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的方法是<STRONG> https://admin 。</STRONG> &lt;域 &gt; 。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。 如果该更改影响简单 URL 的基础，则还必须更改 DNS 记录和证书。 例如，从更改 https://lync.contoso.com/Meet 为将 https://meet.contoso.com 基 URL 从 lync.contoso.com 更改为 meet.contoso.com，因此您需要将 DNS 记录和证书更改为引用 meet.contoso.com。 如果将简单 URL 从更改 https://lync.contoso.com/Meet 为 https://lync.contoso.com/Meetings ，lync.contoso.com 的基 url 将保持不变，因此不需要任何 DNS 或证书更改。 但是，只要您更改简单的 URL 名称，就必须在每个控制器和前端服务器上运行 <STRONG>CsComputer</STRONG> cmdlet 以注册更改。

    
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

