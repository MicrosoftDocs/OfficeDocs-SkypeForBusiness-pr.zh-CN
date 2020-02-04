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
ms.openlocfilehash: adb722f69dcd975d7f346b6e4db8f8ff140f4ac3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="a0245-102">在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件</span><span class="sxs-lookup"><span data-stu-id="a0245-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0245-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a0245-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a0245-104">在启用 Kerberos 身份验证之前，请确保完成所有先决条件配置和基础结构准备：</span><span class="sxs-lookup"><span data-stu-id="a0245-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="a0245-105">Active Directory 架构已针对 Lync Server 2013 进行了扩展。</span><span class="sxs-lookup"><span data-stu-id="a0245-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="a0245-106">已完成 Lync Server 2013 的 Active Directory 林准备。</span><span class="sxs-lookup"><span data-stu-id="a0245-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="a0245-107">已完成 Lync Server 2013 的 Active Directory 域准备。</span><span class="sxs-lookup"><span data-stu-id="a0245-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="a0245-108">中央管理存储已成功安装且可用。</span><span class="sxs-lookup"><span data-stu-id="a0245-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="a0245-109">拓扑结构已使用拓扑生成器创建和发布。</span><span class="sxs-lookup"><span data-stu-id="a0245-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="a0245-110">已定义并部署需要 Web 服务的服务器和角色，包括前端服务器、标准版服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="a0245-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="a0245-111">Internet Information Services （IIS）已使用推荐的角色服务进行配置和部署，以支持 Lync Server 2013 中的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="a0245-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="a0245-112">满足先决条件后，您应该准备好创建一个或多个用于部署的 Kerberos 身份验证的 Web 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a0245-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="a0245-113">至少，你需要为每个部署创建一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="a0245-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="a0245-114">但是，你可以为每个网站创建一个帐户，以便在网站上提供本地 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="a0245-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="a0245-115">你只能为每个站点指定一个 Kerberos 身份验证帐户。</span><span class="sxs-lookup"><span data-stu-id="a0245-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

