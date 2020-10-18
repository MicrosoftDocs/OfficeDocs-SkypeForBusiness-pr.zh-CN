---
title: Lync Server 2013：启用 Kerberos 身份验证的先决条件
description: Lync Server 2013：启用 Kerberos 身份验证的先决条件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579918"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="95108-103">在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件</span><span class="sxs-lookup"><span data-stu-id="95108-103">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95108-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="95108-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="95108-105">在启用 Kerberos 身份验证之前，请确保完成所有先决条件配置和基础结构准备：</span><span class="sxs-lookup"><span data-stu-id="95108-105">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="95108-106">为 Lync Server 2013 扩展了 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="95108-106">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="95108-107">Lync Server 2013 的 Active Directory 林准备已完成。</span><span class="sxs-lookup"><span data-stu-id="95108-107">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="95108-108">Lync Server 2013 的 Active Directory 域准备已完成。</span><span class="sxs-lookup"><span data-stu-id="95108-108">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="95108-109">中央管理存储已成功安装且可用。</span><span class="sxs-lookup"><span data-stu-id="95108-109">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="95108-110">已使用拓扑生成器创建并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="95108-110">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="95108-111">已定义和部署需要 Web 服务的服务器和角色，包括前端服务器、Standard Edition 服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="95108-111">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="95108-112">Internet 信息服务 (IIS) 使用推荐的角色服务进行配置和部署，以支持 Lync Server 2013 中的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="95108-112">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="95108-113">满足先决条件后，应准备好创建一个或多个帐户，以供用于部署的 Kerberos 身份验证的 Web 服务使用。</span><span class="sxs-lookup"><span data-stu-id="95108-113">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="95108-114">至少需要为每个部署创建一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="95108-114">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="95108-115">但是，可以为每个站点创建一个帐户，以在该站点提供本地 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="95108-115">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="95108-116">只能为每个站点指定一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="95108-116">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

