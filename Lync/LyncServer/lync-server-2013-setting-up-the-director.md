---
title: Lync Server 2013：设置控制器
description: Lync Server 2013：设置控制器。
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
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554108"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="803d7-103">在 Lync Server 2013 中设置控制器</span><span class="sxs-lookup"><span data-stu-id="803d7-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="803d7-104">_**上次修改的主题：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="803d7-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="803d7-105">如果您正在通过部署边缘服务器为外部用户启用访问权限，则可以选择部署一个控制器。</span><span class="sxs-lookup"><span data-stu-id="803d7-105">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="803d7-106">Director 是一台运行 Microsoft Lync Server 2013 的服务器，它对用户请求进行身份验证，但不在家任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="803d7-106">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="803d7-107">现在，这不是必需的，但如果担心性能并希望帮助简化身份验证请求，它会非常有用。</span><span class="sxs-lookup"><span data-stu-id="803d7-107">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="803d7-108">如果您认为这对于您的组织来说是一个好主意，则设置控制器或控制器池的步骤类似于设置 Enterprise Edition 前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="803d7-108">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="803d7-109">在拓扑生成器中定义了控制器 (s) 后，需要执行本节中的步骤。</span><span class="sxs-lookup"><span data-stu-id="803d7-109">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="803d7-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="803d7-110">In This Section</span></span>

  - [<span data-ttu-id="803d7-111">在 Lync Server 2013 中安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="803d7-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="803d7-112">在控制器上安装 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="803d7-112">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="803d7-113">在 Lync Server 2013 中为控制器配置证书</span><span class="sxs-lookup"><span data-stu-id="803d7-113">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="803d7-114">在 Lync Server 2013 中的控制器上启动服务</span><span class="sxs-lookup"><span data-stu-id="803d7-114">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="803d7-115">在 Lync Server 2013 中测试控制器</span><span class="sxs-lookup"><span data-stu-id="803d7-115">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="803d7-116">将自动客户端 Sign-In 配置为在 Lync Server 2013 中使用控制器</span><span class="sxs-lookup"><span data-stu-id="803d7-116">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

