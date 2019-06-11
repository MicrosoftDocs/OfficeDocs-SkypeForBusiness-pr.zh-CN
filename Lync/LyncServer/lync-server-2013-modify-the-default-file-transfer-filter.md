---
title: 'Lync Server 2013: 修改默认文件传输筛选器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>在 Lync Server 2013 中修改默认文件传输筛选器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

Lync Server 2013 提供了全局文件传输筛选器, 可在 Lync Server 2013 部署中的以下与文件相关的活动期间阻止特定类型的文件:

  - 即时消息 (IM) 对话期间的文件传输请求

  - 使用 Office Live Meeting 2007 客户端中的讲义功能时的文件上载和下载

  - 在会议期间播放多媒体

根据要阻止或允许的文件类型, 您可以使用 Lync Server "控制面板" 修改全局筛选器。 有关文件传输筛选的详细信息, 请参阅[在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>修改默认文件传输筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 " **IM 和状态**", 然后单击 "**文件筛选器**"。

4.  在 "**文件筛选器**" 页面上, 双击 "**全局**" 筛选器。

5.  在 "**编辑文件筛选器**" 中, 选中 "**启用文件筛选器**" 复选框。

6.  在 "**文件传送**" 下拉列表框中, 单击 "**阻止全部**" 或 "**阻止特定文件类型**"。

7.  如果单击 "**全部阻止**", 请跳到步骤9。

8.  如果单击了 "**阻止特定文件类型**", 请执行下列操作:
    
    1.  单击 "**选择**" 以修改要阻止的文件类型扩展名的默认列表。
    
    2.  在 "**选择文件类型**" 中, 从 "**文件类型扩展**" 下的类别中添加或删除扩展名, 选择要阻止或允许的文件类型。
    
    3.  如果看不到要阻止的文件类型的扩展名, 请在文本框中的 "**向列表添加文件类型扩展名**" 下键入扩展名, 然后单击 "**添加**"。
    
    4.  单击“**确定**”。

9.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 中为特定网站创建新的文件传输筛选器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

