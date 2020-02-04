---
title: Lync Server 2013：设置控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d0b309e87dddb621d6c3a90b16b6c2e02845df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="8f838-102">在 Lync Server 2013 中设置控制器</span><span class="sxs-lookup"><span data-stu-id="8f838-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f838-103">_**主题上次修改时间：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="8f838-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="8f838-104">如果你通过部署 Edge 服务器为外部用户启用访问权限，则可以选择部署 Director。</span><span class="sxs-lookup"><span data-stu-id="8f838-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="8f838-105">Director 是运行 Microsoft Lync Server 2013 的服务器，用于验证用户请求，但不会在家任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8f838-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="8f838-106">现在，这不是必需的，但如果担心性能并希望帮助简化身份验证请求，它将非常有用。</span><span class="sxs-lookup"><span data-stu-id="8f838-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="8f838-107">如果你认为这对你的组织来说是个好主意，则设置 Director 或主管池的步骤类似于设置企业版前端池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="8f838-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="8f838-108">在拓扑生成器中定义导演后，您需要执行本部分中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8f838-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f838-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f838-109">In This Section</span></span>

  - [<span data-ttu-id="8f838-110">在 Lync Server 2013 中安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="8f838-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="8f838-111">在控制器上安装 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f838-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="8f838-112">在 Lync Server 2013 中为控制器配置证书</span><span class="sxs-lookup"><span data-stu-id="8f838-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="8f838-113">在 Lync Server 2013 中的控制器上启动服务</span><span class="sxs-lookup"><span data-stu-id="8f838-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="8f838-114">在 Lync Server 2013 中测试控制器</span><span class="sxs-lookup"><span data-stu-id="8f838-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="8f838-115">在 Lync Server 2013 中配置自动客户端登录以使用控制器</span><span class="sxs-lookup"><span data-stu-id="8f838-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

