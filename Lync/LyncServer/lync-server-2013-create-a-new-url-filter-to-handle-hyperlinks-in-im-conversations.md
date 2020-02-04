---
title: 创建新的 URL 筛选器以处理即时消息对话中的超链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f6cd39034dbc3114f5b89fb15d252b71149762
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-26_

除了修改全局 URL 筛选器之外，还可以为 Lync Server 2013 部署中的各个网站配置自定义 URL 筛选器。 有关 URL 筛选的详细信息，请参阅[在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-create-a-new-url-filter"></a>创建新的 URL 筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 " **IM 和状态**"，然后单击 " **URL 筛选器**"。

4.  在 " **URL 筛选**" 页面上，单击 "**新建**"。

5.  在 "**选择网站**" 中，单击要为其创建 URL 筛选器的网站，然后单击 **"确定"**。

6.  在 "**新建 URL 筛选器**" 对话框中，选中 "**启用 url 筛选**" 复选框以启用网站的 URL 筛选。

7.  若要阻止包含扩展名在 "**文件类型扩展**" 下列出的文件的任何活动 URL 位于 "**编辑文件筛选器**" 中，请选中 "**使用文件扩展名阻止 url** " 复选框。

8.  在 "**超链接前缀**" 下拉列表框中，单击与您希望在即时消息对话中处理 url 的方式相对应的选项。
    
    "**允许消息**" 框可在发送允许发送的超链接时向用户发送警告消息。

9.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 中为特定网站创建新的文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

