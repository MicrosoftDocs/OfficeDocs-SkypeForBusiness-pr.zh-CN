---
title: Lync Server 2013：域名系统（DNS）要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="155e5-102">Lync Server 2013 的域名系统（DNS）要求</span><span class="sxs-lookup"><span data-stu-id="155e5-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="155e5-103">_**上次修改的主题：** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="155e5-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="155e5-104">若要部署 Lync Server，您必须创建可启用客户端和服务器发现的域名系统（DNS）记录，如果您的组织想要支持自动客户端登录，也可以选择支持它。</span><span class="sxs-lookup"><span data-stu-id="155e5-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="155e5-105">Lync Server 通过以下方式使用 DNS：</span><span class="sxs-lookup"><span data-stu-id="155e5-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="155e5-106">发现内部服务器或池以进行服务器至服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="155e5-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="155e5-107">允许客户端发现用于各种 SIP 事务的前端池或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="155e5-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="155e5-108">允许未登录的统一通信（UC）设备发现运行设备更新 Web 服务的前端池或 Standard Edition 服务器，获取更新和发送日志。</span><span class="sxs-lookup"><span data-stu-id="155e5-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="155e5-109">允许外部服务器和客户端连接到边缘服务器或 HTTP 反向代理，以实现即时消息（IM）或会议。</span><span class="sxs-lookup"><span data-stu-id="155e5-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="155e5-110">允许外部 UC 设备通过边缘服务器或 HTTP 反向代理连接到设备更新 Web 服务，并获取更新。</span><span class="sxs-lookup"><span data-stu-id="155e5-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="155e5-111">使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。</span><span class="sxs-lookup"><span data-stu-id="155e5-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="155e5-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="155e5-112">In This Section</span></span>

  - [<span data-ttu-id="155e5-113">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="155e5-114">Lync Server 2013 中前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="155e5-115">Lync Server 2013 中的 Standard Edition 服务器的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="155e5-116">Lync Server 2013 中简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="155e5-117">Lync Server 2013 中自动客户端登录的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="155e5-118">具有 Lync Server 2013 的移动性的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="155e5-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="155e5-119">Lync Server 2013 中的 DNS 负载平衡</span><span class="sxs-lookup"><span data-stu-id="155e5-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

