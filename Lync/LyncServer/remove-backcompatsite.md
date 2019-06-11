---
title: 删除 BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>删除 BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

在停用所有池并卸载所有边缘服务器之后, 请运行拓扑生成器合并向导删除**BackCompatSite**。

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>从拓扑生成器删除 BackCompat 网站

1.  从拓扑生成器打开现有部署。

2.  在 "**操作**" 菜单中, 单击 "**合并 2007 R2 拓扑**"。

3.  单击“**下一步**”继续。

4.  在 "**指定旧版 Edge** " 页面上, 确保 Edge 服务器列表为空。 如果列表不为空, 请使用 "**删除**" 按钮删除所有旧式边缘服务器, 然后单击 "**下一步**"。
    
    ![合并拓扑向导, "指定边缘设置" 页面](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合并拓扑向导, \"指定边缘设置\" 页面")  

5.  在 "**指定内部 SIP 端口设置**" 页面上, 单击 "**下一步**"。

6.  在 "**摘要**" 页面上, 单击 "**下一步**" 以开始合并拓扑以删除旧网站。

7.  在 "**状态**" 列中, 验证值是否**成功**, 然后单击 "**完成**" 关闭向导。

8.  在拓扑生成器的左窗格中, 展开 "BackCompatSite" 并确保未列出任何服务器。

9.  右键单击 " **BackCompatSite**", 然后单击 "**删除**"。

10. 在**拓扑生成器**中, 选择最前面的节点**Lync 服务器**。

11. 从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。

12. **发布向导**完成后, 单击 "**完成**" 关闭向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

