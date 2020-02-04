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
ms.openlocfilehash: 9f9b7ef52da78219f66df79d9e02bc67786b76d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-software-and-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="8a49b-102">Lync Server 2013 中的服务器软件和基础结构支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-102">Server software and infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a49b-103">_**主题上次修改时间：** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="8a49b-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="8a49b-104">服务器组件的软件支持，包括所有 Lync Server 2013 服务器角色和存储，包括支持的操作系统、数据库软件、基础结构软件和支持特定功能所需的其他软件。</span><span class="sxs-lookup"><span data-stu-id="8a49b-104">Software support for server components, including all Lync Server 2013 server roles and storage, includes supported operating systems, database software, infrastructure software, and other software required to support specific functionality.</span></span> <span data-ttu-id="8a49b-105">它还包括服务器组件的虚拟化。</span><span class="sxs-lookup"><span data-stu-id="8a49b-105">It also includes virtualization of server components.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a49b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a49b-106">In This Section</span></span>

  - [<span data-ttu-id="8a49b-107">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-107">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="8a49b-108">Lync Server 2013 中的数据库软件支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-108">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="8a49b-109">Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-109">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)

  - [<span data-ttu-id="8a49b-110">Lync Server 2013 中的证书基础结构支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-110">Certificate infrastructure support in Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-support.md)

  - [<span data-ttu-id="8a49b-111">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-111">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)

  - [<span data-ttu-id="8a49b-112">Lync Server 2013 中的 DNS 基础结构支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-112">DNS infrastructure support in Lync Server 2013</span></span>](lync-server-2013-dns-infrastructure-support.md)

  - [<span data-ttu-id="8a49b-113">Lync Server 2013 中的 IIS 支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-113">IIS support in Lync Server 2013</span></span>](lync-server-2013-iis-support.md)

  - [<span data-ttu-id="8a49b-114">Lync Server 2013 中的 IP 和网络协议支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-114">IP and networking protocol support in Lync Server 2013</span></span>](lync-server-2013-ip-and-networking-protocol-support.md)

  - [<span data-ttu-id="8a49b-115">Lync Server 2013 中的公共即时消息支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-115">Public instant messaging support in Lync Server 2013</span></span>](lync-server-2013-public-instant-messaging-support.md)

  - [<span data-ttu-id="8a49b-116">Lync Server 2013 控制面板的浏览器支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-116">Browser support for Lync Server 2013 Control Panel</span></span>](lync-server-2013-browser-support-for-lync-server-control-panel.md)

  - [<span data-ttu-id="8a49b-117">Lync Server 2013 中的语音支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-117">Voice support in Lync Server 2013</span></span>](lync-server-2013-voice-support.md)

  - [<span data-ttu-id="8a49b-118">Lync Server 2013 中的虚拟化支持</span><span class="sxs-lookup"><span data-stu-id="8a49b-118">Virtualization support in Lync Server 2013</span></span>](lync-server-2013-virtualization-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

