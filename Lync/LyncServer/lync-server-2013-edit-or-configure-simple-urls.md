---
title: Lync Server 2013：编辑或配置简单 URL
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中编辑或配置简单 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-04_

此过程不需要本地管理员或特权域组的成员身份。 您应以标准用户身份登录到计算机。

Lync Server 2013 使用简单的 Url 将内部和外部调用用于前端服务器或控制器上的服务（如果已部署）。 有关简单 Url 的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md) 。 你可以从多个选项中选择简单 Url 的格式。 有关这些选项的详细信息，请参阅规划文档中[Lync Server 2013 中简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)。

默认情况下，将以（例如，拨入式简单 URL）的形式配置简单的 Url： https://dialin.\<SIP域\>

<div>

## <a name="to-configure-simple-urls"></a>配置简单 Url

1.  在拓扑生成器中，右键单击 " **Lync 服务器**" 节点，然后单击 "**编辑属性**"。

2.  在“**简单 URL**”窗格中，选择要编辑的“**电话访问 URL:**”（拨入）或“**会议 URL:**”（会议），然后单击“**编辑 URL**”。

3.  将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。 此处显示的示例已将拨入 URL 修改为https://pool01.contoso.net/dialin。

4.  如有必要，使用相同的步骤编辑会议 URL。

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>定义可选的管理简单 URL

1.  在拓扑生成器中，右键单击 " **Lync 服务器**" 节点，然后单击 "**编辑属性**"。

2.  在 "**管理访问 URL** " 框中，输入要用于管理访问 Lync Server 2013 控制面板的简单 URL，然后单击 **"确定"**。
    
    <div>
    

    > [!TIP]  
    > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项是<STRONG> https://admin。</STRONG>&lt;域&gt;。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果在初始部署后更改简单 URL，您必须注意哪些更改会影响简单 URL 的域名系统 (DNS) 记录和证书。 如果更改影响简单 URL 的基础，则必须同时更改 DNS 记录和证书。 例如，从https://lync.contoso.com/Meet https://meet.contoso.com lync.contoso.com 更改为 meet.contoso.com 的基本 URL，因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。 如果将简单 URL 更改https://lync.contoso.com/Meet为 "与https://lync.contoso.com/Meetings"，lync.contoso.com 的基 url 保持不变，因此不需要任何 DNS 或证书更改。 但是，每当你更改简单的 URL 名称时，你必须在每个 Director 和前端服务器上运行<STRONG>Enable-CsComputer</STRONG> cmdlet 来注册更改。

    
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

