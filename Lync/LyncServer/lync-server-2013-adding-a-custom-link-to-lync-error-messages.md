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
ms.openlocfilehash: 3c9f15b72f105edf291007569999c549b8b2c841
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>在 Lync Server 2013 中向 Lync 错误消息添加自定义链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

通过添加指向您自己的故障排除或技术支持信息的链接来自定义 Lync 2013 错误消息。 若要执行此操作，请使用 CustomLinkInErrorMessages 参数的**set-csclientpolicy**或**set-csclientpolicy** Lync Server 命令行管理程序 cmdlet。 自定义链接的文本是 "单击此处获取来自管理员的支持主题"，无法对其进行自定义。

例如，以下命令使自定义链接显示在每个 Lync 2013 错误消息的脚注区域中，并将链接目标设置为http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用 **Grant-CSClientPolicy** 将此新策略分配给用户。 有关详细信息，请参阅 Lync Server 命令行管理程序文档中的**set-csclientpolicy**和**Grant set-csclientpolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

