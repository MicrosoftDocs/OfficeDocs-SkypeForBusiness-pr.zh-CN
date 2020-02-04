---
title: Lync Server 2013：为特定网站创建新的文件传输筛选器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>在 Lync Server 2013 中为特定网站创建新的文件传输筛选器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-18_

除了修改全局文件传输筛选器，还可以为 Lync Server 2013 部署中的特定网站配置自定义文件传输筛选器。 有关文件传输筛选的详细信息，请参阅[在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>为特定网站创建文件传输筛选器

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 " **IM 和状态**"，然后单击 "**文件筛选器**"。

4.  在 "**文件筛选器**" 页面上，单击 "**新建**"。

5.  在 "**选择网站**" 对话框中，单击要为其创建文件传输筛选器的网站，然后单击 **"确定"**。

6.  在 "**新建文件筛选器**" 中，单击 "**启用文件筛选器**" 复选框。

7.  在 "**文件传输**" 下拉列表框中，单击 "**阻止全部**" 或 "**阻止特定文件类型**"。

8.  如果单击 "**全部阻止**"，请跳到步骤10。

9.  如果单击了 "**阻止特定文件类型**"，请执行下列操作：
    
    1.  单击 "**选择**" 以修改要阻止的文件类型扩展名的默认列表。
    
    2.  在 "**选择文件类型**" 对话框中，从 "**文件类型扩展**" 下的类别中添加或删除扩展名，选择要阻止或允许的文件类型。
    
    3.  如果看不到要阻止的文件类型的扩展名，请在文本框中的 "**向列表添加文件类型扩展名**" 下键入扩展名，然后单击 "**添加**"。
    
    4.  单击“**确定**”。

10. 单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[在 Lync Server 2013 中修改默认文件传输筛选器](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[在 Lync Server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

