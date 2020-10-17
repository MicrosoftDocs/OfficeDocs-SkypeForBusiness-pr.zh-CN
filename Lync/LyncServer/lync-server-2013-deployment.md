---
title: Lync Server 2013：部署
description: Lync Server 2013：部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555358"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="6d4f0-103">Lync Server 2013 的部署</span><span class="sxs-lookup"><span data-stu-id="6d4f0-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d4f0-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6d4f0-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6d4f0-105">部署 Lync Server 2013 通信软件包括准备 Active Directory 域服务、部署前端服务器和其他核心 Lync Server 2013 内部组件，然后部署您的组织可能需要的任何其他服务器角色和功能，例如外部用户访问和企业语音。</span><span class="sxs-lookup"><span data-stu-id="6d4f0-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="6d4f0-106">本文档介绍了用于部署 Lync Server 2013 的三种方案：</span><span class="sxs-lookup"><span data-stu-id="6d4f0-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="6d4f0-107">Lync Server 2013 Enterprise Edition 的新部署</span><span class="sxs-lookup"><span data-stu-id="6d4f0-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="6d4f0-108">Lync Server 2013 的全新部署，Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6d4f0-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="6d4f0-109">将 Lync Server 2013 Standard Edition 或 Enterprise Edition 全新部署到现有 Lync Server 2010 Standard Edition 或 Enterprise Edition 部署中</span><span class="sxs-lookup"><span data-stu-id="6d4f0-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="6d4f0-110">有关在现有 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 环境中部署 Lync Server 2013 的信息，请参阅 [迁移](migration.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="6d4f0-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d4f0-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="6d4f0-111">In This Section</span></span>

  - [<span data-ttu-id="6d4f0-112">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d4f0-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="6d4f0-113">在 Lync Server 2013 中部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="6d4f0-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="6d4f0-114">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="6d4f0-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="6d4f0-115">在 Lync Server 2013 中部署监控</span><span class="sxs-lookup"><span data-stu-id="6d4f0-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="6d4f0-116">在 Lync Server 2013 中部署存档</span><span class="sxs-lookup"><span data-stu-id="6d4f0-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="6d4f0-117">在 Lync Server 2013 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="6d4f0-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="6d4f0-118">在 Lync Server 2013 中规划和部署视频</span><span class="sxs-lookup"><span data-stu-id="6d4f0-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="6d4f0-119">在 Lync Server 2013 中部署分支站点</span><span class="sxs-lookup"><span data-stu-id="6d4f0-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="6d4f0-120">在 Lync Server 2013 中部署持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="6d4f0-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="6d4f0-121">在 Lync Server 2013 中部署客户端和设备</span><span class="sxs-lookup"><span data-stu-id="6d4f0-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="6d4f0-122">在 Lync Server 2013 中规划和部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="6d4f0-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="6d4f0-123">在 Lync Server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="6d4f0-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="6d4f0-124">从 Lync Server 2013 评估版更新</span><span class="sxs-lookup"><span data-stu-id="6d4f0-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="6d4f0-125">在 Lync Server 2013 中部署远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6d4f0-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="6d4f0-126">在 Lync Server 2013 中部署移动功能</span><span class="sxs-lookup"><span data-stu-id="6d4f0-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="6d4f0-127">配置与 Office Web Apps Server 和 Lync Server 2013 的集成</span><span class="sxs-lookup"><span data-stu-id="6d4f0-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="6d4f0-128">Lync Server 2013 中的运行状况配置</span><span class="sxs-lookup"><span data-stu-id="6d4f0-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

