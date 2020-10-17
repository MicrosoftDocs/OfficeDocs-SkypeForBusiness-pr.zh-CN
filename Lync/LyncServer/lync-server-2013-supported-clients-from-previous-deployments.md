---
title: Lync Server 2013：以前的部署支持的客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f404dad679eeffa91465f3f8547fbe86ce74b0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524129"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013 中以前的部署支持的客户端

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-14_

在共存方案中，Lync Server 2013 客户端可以与早期版本的 Lync Server 和 Office 通信服务器进行交互。 与以前的版本不同，Lync Server 2010 支持新的 Lync 2013 客户端。 这使得从 Lync Server 2010 升级的组织可以独立于 Lync Server 升级来部署新的客户端。

<div>

## <a name="supported-server-and-client-combinations"></a>支持的服务器和客户端组合

下表显示受支持的客户端版本和服务器版本的组合。 Lync Server 2013 支持两个以前的客户端版本，Lync Server 2010 支持新的 Lync 2013 客户端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 组聊天</p></td>
<td><p>不适用</p></td>
<td><p>Supported1</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>不 Supported2</p></td>
<td><p>支持</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010，组聊天功能可用于 Lync Server 2010 的第三方受信任应用程序的组聊天服务器。 Lync 2013 客户端与 Lync Server 2010、组聊天不兼容。

2Lync Web App 2013 现在提供了完整的会议体验，包括计算机音频和视频，并被视为 Lync 2010 与会者的替代项。

Office Communicator 2007 R2 中的3The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。 从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。

<div>


> [!NOTE]  
> 有关 Lync Server 2013 客户端在早期版本的 Lync Server 和 Office 通信服务器中共存并与客户端交互的功能的详细信息，请参阅规划文档中的 <A href="lync-server-2013-client-interoperability-in-lync-2013.md">lync 2013 中的客户端互操作性</A> 。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

