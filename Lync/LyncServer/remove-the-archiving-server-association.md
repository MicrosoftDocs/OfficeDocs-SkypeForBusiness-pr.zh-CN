---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bf1a5a3c68ab1123431543e08618c4eacb7559
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>删除存档服务器关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

若要删除存档服务器，你需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖关系。 编辑前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后，系统会通知你拓扑生成器中的相关数据库存储对象也将被删除。

<div>

## <a name="to-remove-the-archiving-server-association"></a>删除存档服务器关联

1.  打开 Lync Server 2013 前端服务器，打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  在拓扑生成器中，根据在其中定义存档服务器的位置，展开 "**企业版前端池**"、"**标准版前端服务器**" 或 "**分支站点**"。

4.  如果您有关联的 Survivable 分支服务器，请展开 "**分支站点**"，展开 "分支站点名称"，然后展开 "**分支机构" Survivable**。
    
    <div>
    

    > [!NOTE]  
    > 用户界面中的<STRONG>Survivable 分支装置</STRONG>适用于 Survivable 分支服务器和 Survivable 分支装置。

    
    </div>

5.  右键单击与存档服务器相关联的池、服务器或设备，然后单击 "**编辑属性**"。

6.  在 "**编辑属性**" 下的 "**常规**" 下的 "**关联**" 下，清除 "**关联存档服务器**" 复选框，然后单击 **"确定"**。

7.  对与要删除的存档服务器关联的任何其他池、服务器或设备重复上一步骤。

8.  右键单击存档服务器，然后单击 "**删除**"。

9.  在 "**删除从属存储**" 中，单击 **"确定"**。

10. 发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

