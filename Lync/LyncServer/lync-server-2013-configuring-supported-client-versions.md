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
ms.openlocfilehash: 326a428003a7836adef588942765909b753124ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="a66ab-102">在 Lync Server 2013 中配置支持的客户端版本</span><span class="sxs-lookup"><span data-stu-id="a66ab-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a66ab-103">_**上次修改的主题：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="a66ab-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="a66ab-104">在 Lync Server 2013 中，可以设置客户端版本策略以指定您的环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="a66ab-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="a66ab-105">此外，可以使用全局客户端版本配置，为尚未定义版本策略并因此尚未明确得到支持或限制的客户端指定默认操作。</span><span class="sxs-lookup"><span data-stu-id="a66ab-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="a66ab-p102">您也可以使用客户端版本策略来管理客户端更新。如果设置客户端版本策略并使用“允许并升级”\*\*\*\* 和“阻止并升级”\*\*\*\* 选项，客户端将从 Windows Server 更新服务（如果正在使用此服务）或 Microsoft Update 接收更新的软件。</span><span class="sxs-lookup"><span data-stu-id="a66ab-p102">You can also use client version policies to manage client updates. When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="a66ab-108">客户端版本策略设置</span><span class="sxs-lookup"><span data-stu-id="a66ab-108">Client Version Policy Settings</span></span>

<span data-ttu-id="a66ab-109">默认客户端版本策略要求所有客户端都运行 Lync。</span><span class="sxs-lookup"><span data-stu-id="a66ab-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="a66ab-110">如果环境中的客户端运行的是早期版本的 Communicator，您可能需要重新配置客户端版本规则，以防止在连接到 Lync Server 2013 时意外地阻止或更新客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="a66ab-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="a66ab-111">您可以修改默认规则，也可以在“客户端版本策略”列表的更高位置添加一个规则来覆盖默认规则。</span><span class="sxs-lookup"><span data-stu-id="a66ab-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="a66ab-112">此外，由于发布累计更新 (CU)，应将客户端版本策略配置为要求最新更新。</span><span class="sxs-lookup"><span data-stu-id="a66ab-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="a66ab-113">有关详细信息，请参阅操作文档中的[指定可用于登录 Lync Server 2013 的客户端应用程序](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="a66ab-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

