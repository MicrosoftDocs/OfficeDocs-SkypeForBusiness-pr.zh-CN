---
title: Lync Server 2013：启用 Kerberos 身份验证的先决条件
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
ms.openlocfilehash: f5fa366ae27126ead478d66c3beb091581158d1a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="489e5-102">在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件</span><span class="sxs-lookup"><span data-stu-id="489e5-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="489e5-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="489e5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="489e5-104">在启用 Kerberos 身份验证之前，请确保完成所有先决条件配置和基础结构准备：</span><span class="sxs-lookup"><span data-stu-id="489e5-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="489e5-105">为 Lync Server 2013 扩展了 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="489e5-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="489e5-106">Lync Server 2013 的 Active Directory 林准备已完成。</span><span class="sxs-lookup"><span data-stu-id="489e5-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="489e5-107">Lync Server 2013 的 Active Directory 域准备已完成。</span><span class="sxs-lookup"><span data-stu-id="489e5-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="489e5-108">中央管理存储已成功安装且可用。</span><span class="sxs-lookup"><span data-stu-id="489e5-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="489e5-109">已使用拓扑生成器创建并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="489e5-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="489e5-110">已定义和部署需要 Web 服务的服务器和角色，包括前端服务器、Standard Edition 服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="489e5-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="489e5-111">Internet Information Services （IIS）使用推荐的角色服务进行配置和部署，以支持 Lync Server 2013 中的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="489e5-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="489e5-112">满足先决条件后，应准备好创建一个或多个帐户，以供用于部署的 Kerberos 身份验证的 Web 服务使用。</span><span class="sxs-lookup"><span data-stu-id="489e5-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="489e5-113">至少需要为每个部署创建一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="489e5-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="489e5-114">但是，可以为每个站点创建一个帐户，以在该站点提供本地 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="489e5-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="489e5-115">只能为每个站点指定一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="489e5-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

