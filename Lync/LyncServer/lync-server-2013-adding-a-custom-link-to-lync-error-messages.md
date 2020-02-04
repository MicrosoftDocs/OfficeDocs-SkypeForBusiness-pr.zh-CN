---
title: Lync Server 2013：向 Lync 错误消息添加自定义链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63523013d8df74a52fee307192d3f60eb5232121
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>在 Lync Server 2013 中向 Lync 错误消息添加自定义链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

通过添加您自己的疑难解答或技术支持信息的链接，自定义 Lync 2013 错误消息。 若要执行此操作，请将**set-csclientpolicy**或**set-csclientpolicy** Lync Server Management Shell cmdlet 与 CustomLinkInErrorMessages 参数一起使用。 自定义链接的文本为 "单击此处获取来自管理员的支持主题"，无法对其进行自定义。

例如，以下命令会使自定义链接显示在每个 Lync 2013 错误消息的脚注区域中，并将链接目标设置为http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用**Grant-set-csclientpolicy**将此新策略分配给用户。 有关详细信息，请参阅 Lync Server Management Shell 文档中的 "**新建-set-csclientpolicy** " 和 "**授予" set-csclientpolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

