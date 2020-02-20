---
title: 创建新的 URL 筛选器以处理 IM 对话中的超链接
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
ms.openlocfilehash: 250533f8de89eb1cd5aaa72d8f66cfd0800a1bc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>在 Lync Server 2013 中创建一个新的 URL 筛选器，以处理 IM 对话中的超链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-26_

除了修改全局 URL 筛选器之外，还可以为 Lync Server 2013 部署中的各个网站配置自定义 URL 筛选器。 有关 URL 筛选的详细信息，请参阅[Lync Server 2013 中的为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-create-a-new-url-filter"></a>创建新的 URL 筛选器

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“IM 和状态”****，然后单击“URL 筛选器”****。

4.  在“URL 筛选器”**** 页上，单击“新建”****。

5.  在“选择站点”**** 中，单击要为其创建 URL 筛选器的站点，然后单击“确定”****。

6.  在“新建 URL 筛选器”**** 对话框中，选中“启用 URL 筛选器”**** 复选框以启用站点的 URL 筛选。

7.  要阻止包含具有“编辑文件筛选器”**** 中“要阻止的文件类型扩展名”**** 下所列扩展名的文件的任何活动 URL，请选中“阻止带文件扩展名的 URL”**** 复选框。

8.  在“超链接前缀”**** 下拉列表框中，单击与希望的即时消息对话中的 URL 处理方式对应的选项。
    
    当用户发送允许发送的超链接时，将通过“允许消息”**** 框向其发送警告消息。

9.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 for a 特定网站中创建新的文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

