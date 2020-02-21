---
title: Lync Server 2013：服务器软件和基础结构支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server software and infrastructure support
ms:assetid: 4ee5fe38-0191-4710-9aa2-df8895e8c51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398319(v=OCS.15)
ms:contentKeyID: 48184127
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92794db01db02ec8c9413fdab8c2c31cc624dfaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-software-and-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="b6ee2-102">Lync Server 2013 中的服务器软件和基础结构支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-102">Server software and infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6ee2-103">_**上次修改的主题：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="b6ee2-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="b6ee2-104">服务器组件的软件支持，包括所有 Lync Server 2013 服务器角色和存储，其中包括支持的操作系统、数据库软件、基础结构软件以及支持特定功能所需的其他软件。</span><span class="sxs-lookup"><span data-stu-id="b6ee2-104">Software support for server components, including all Lync Server 2013 server roles and storage, includes supported operating systems, database software, infrastructure software, and other software required to support specific functionality.</span></span> <span data-ttu-id="b6ee2-105">还包括服务器组件的虚拟化。</span><span class="sxs-lookup"><span data-stu-id="b6ee2-105">It also includes virtualization of server components.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b6ee2-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b6ee2-106">In This Section</span></span>

  - [<span data-ttu-id="b6ee2-107">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-107">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="b6ee2-108">Lync Server 2013 中的数据库软件支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-108">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="b6ee2-109">Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-109">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)

  - [<span data-ttu-id="b6ee2-110">Lync Server 2013 中的证书基础结构支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-110">Certificate infrastructure support in Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-support.md)

  - [<span data-ttu-id="b6ee2-111">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-111">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)

  - [<span data-ttu-id="b6ee2-112">Lync Server 2013 中的 DNS 基础结构支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-112">DNS infrastructure support in Lync Server 2013</span></span>](lync-server-2013-dns-infrastructure-support.md)

  - [<span data-ttu-id="b6ee2-113">Lync Server 2013 中的 IIS 支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-113">IIS support in Lync Server 2013</span></span>](lync-server-2013-iis-support.md)

  - [<span data-ttu-id="b6ee2-114">Lync Server 2013 中的 IP 和网络协议支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-114">IP and networking protocol support in Lync Server 2013</span></span>](lync-server-2013-ip-and-networking-protocol-support.md)

  - [<span data-ttu-id="b6ee2-115">Lync Server 2013 中的公共即时消息支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-115">Public instant messaging support in Lync Server 2013</span></span>](lync-server-2013-public-instant-messaging-support.md)

  - [<span data-ttu-id="b6ee2-116">Lync Server 2013 控制面板的浏览器支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-116">Browser support for Lync Server 2013 Control Panel</span></span>](lync-server-2013-browser-support-for-lync-server-control-panel.md)

  - [<span data-ttu-id="b6ee2-117">Lync Server 2013 中的语音支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-117">Voice support in Lync Server 2013</span></span>](lync-server-2013-voice-support.md)

  - [<span data-ttu-id="b6ee2-118">Lync Server 2013 中的虚拟化支持</span><span class="sxs-lookup"><span data-stu-id="b6ee2-118">Virtualization support in Lync Server 2013</span></span>](lync-server-2013-virtualization-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

