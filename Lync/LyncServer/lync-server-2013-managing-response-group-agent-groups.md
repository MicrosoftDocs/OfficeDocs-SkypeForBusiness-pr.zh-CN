---
title: Lync Server 2013：管理响应组代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f791ea6a2091ab50e159b541ef19789ffcde02b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理响应组代理组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

代理组由指定应答响应组呼叫的一组人员组成。创建代理组时，要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。

<div>


> [!NOTE]  
> 必须先为用户启用企业语音，然后才能将其添加到代理组。 有关如何为用户启用企业语音的详细信息，请参阅<A href="lync-server-2013-enable-users-for-enterprise-voice.md">enable users For Enterprise voice In Lync Server 2013</A>。



</div>

<div>


> [!NOTE]  
> 只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。



</div>

必须登录和注销组（不同于登录或注销 Lync Server）的代理称为*正式代理*。 正式代理必须登录到组，然后才能接收路由至该组的呼叫。 这对于以兼职形式应答组中的呼叫的代理很有用。 正式代理通过单击 Lync 2013 中的菜单项来打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录和注销其组。

不登录到组或从组注销的代理称为*非正式代理*。 非正式代理在登录 Lync Server 时自动登录到组，并且无法注销组。

<div>


> [!IMPORTANT]  
> 如果将用户分配为响应组代理，需告知用户，如果他们已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中创建或修改代理组](lync-server-2013-create-or-modify-an-agent-group.md)

  - [在 Lync Server 2013 中删除代理组](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

