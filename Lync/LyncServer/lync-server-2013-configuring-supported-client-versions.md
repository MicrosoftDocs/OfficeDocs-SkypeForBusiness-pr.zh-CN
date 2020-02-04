---
title: Lync Server 2013：配置支持的客户端版本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="1a427-102">在 Lync Server 2013 中配置支持的客户端版本</span><span class="sxs-lookup"><span data-stu-id="1a427-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a427-103">_**主题上次修改时间：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="1a427-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="1a427-104">在 Lync Server 2013 中，你可以设置客户端版本策略来指定你的环境支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1a427-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="1a427-105">此外，你可以使用全局客户端版本配置为尚未定义版本策略的客户端指定默认操作，因此不会明确支持或限制这些客户端。</span><span class="sxs-lookup"><span data-stu-id="1a427-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="1a427-106">你还可以使用客户端版本策略管理客户端更新。</span><span class="sxs-lookup"><span data-stu-id="1a427-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="1a427-107">当设置客户端版本策略并使用 "**允许和升级**" 和 "**阻止和升级**" 选项时，客户端将从 Windows Server 更新服务接收更新的软件（如果你使用的是此服务），或者从 Microsoft Update 接收更新的软件。</span><span class="sxs-lookup"><span data-stu-id="1a427-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="1a427-108">客户端版本策略设置</span><span class="sxs-lookup"><span data-stu-id="1a427-108">Client Version Policy Settings</span></span>

<span data-ttu-id="1a427-109">默认客户端版本策略要求所有客户端都运行 Lync。</span><span class="sxs-lookup"><span data-stu-id="1a427-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="1a427-110">如果你的环境中的客户运行的是早期版本的 Communicator，则你可能需要重新配置客户端版本规则，以防止在连接到 Lync Server 2013 时意外阻止或更新客户端设备。</span><span class="sxs-lookup"><span data-stu-id="1a427-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="1a427-111">你可以修改默认规则，也可以在客户端版本策略列表中添加更高的规则，以替代默认规则。</span><span class="sxs-lookup"><span data-stu-id="1a427-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="1a427-112">此外，随着累积更新（CUs）的发布，你应该将客户端版本策略配置为需要最新的更新。</span><span class="sxs-lookup"><span data-stu-id="1a427-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="1a427-113">有关详细信息，请参阅在操作文档中[指定可用于登录 Lync Server 2013 的客户端应用程序](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="1a427-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

