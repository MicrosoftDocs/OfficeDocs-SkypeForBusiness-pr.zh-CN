---
title: Lync Server 2013：部署
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
ms.openlocfilehash: 56d0ce8ddd96ec0e77136e95cf7d415acec7a96b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="3e57b-102">Lync Server 2013 的部署</span><span class="sxs-lookup"><span data-stu-id="3e57b-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e57b-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3e57b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3e57b-104">部署 Lync Server 2013 通信软件包括准备 Active Directory 域服务、部署前端服务器和其他核心 Lync Server 2013 内部组件，然后部署任何其他服务器角色和功能您的组织可能需要，例如外部用户访问和企业语音。</span><span class="sxs-lookup"><span data-stu-id="3e57b-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="3e57b-105">本文档介绍了用于部署 Lync Server 2013 的三种方案：</span><span class="sxs-lookup"><span data-stu-id="3e57b-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="3e57b-106">Lync Server 2013 Enterprise Edition 的新部署</span><span class="sxs-lookup"><span data-stu-id="3e57b-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="3e57b-107">Lync Server 2013 的全新部署，Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3e57b-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="3e57b-108">将 Lync Server 2013 Standard Edition 或 Enterprise Edition 全新部署到现有 Lync Server 2010 Standard Edition 或 Enterprise Edition 部署中</span><span class="sxs-lookup"><span data-stu-id="3e57b-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="3e57b-109">有关在现有 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 环境中部署 Lync Server 2013 的信息，请参阅[迁移](migration.md)文档。</span><span class="sxs-lookup"><span data-stu-id="3e57b-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e57b-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3e57b-110">In This Section</span></span>

  - [<span data-ttu-id="3e57b-111">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e57b-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="3e57b-112">在 Lync Server 2013 中部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="3e57b-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="3e57b-113">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="3e57b-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="3e57b-114">在 Lync Server 2013 中部署监控</span><span class="sxs-lookup"><span data-stu-id="3e57b-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="3e57b-115">在 Lync Server 2013 中部署存档</span><span class="sxs-lookup"><span data-stu-id="3e57b-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="3e57b-116">在 Lync Server 2013 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="3e57b-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="3e57b-117">在 Lync Server 2013 中规划和部署视频</span><span class="sxs-lookup"><span data-stu-id="3e57b-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="3e57b-118">在 Lync Server 2013 中部署分支站点</span><span class="sxs-lookup"><span data-stu-id="3e57b-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="3e57b-119">在 Lync Server 2013 中部署持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="3e57b-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="3e57b-120">在 Lync Server 2013 中部署客户端和设备</span><span class="sxs-lookup"><span data-stu-id="3e57b-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="3e57b-121">在 Lync Server 2013 中规划和部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="3e57b-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="3e57b-122">在 Lync Server 2013 中管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="3e57b-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="3e57b-123">从 Lync Server 2013 评估版更新</span><span class="sxs-lookup"><span data-stu-id="3e57b-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="3e57b-124">在 Lync Server 2013 中部署远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="3e57b-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="3e57b-125">在 Lync Server 2013 中部署移动功能</span><span class="sxs-lookup"><span data-stu-id="3e57b-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="3e57b-126">配置与 Office Web Apps Server 和 Lync Server 2013 的集成</span><span class="sxs-lookup"><span data-stu-id="3e57b-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="3e57b-127">Lync Server 2013 中的运行状况配置</span><span class="sxs-lookup"><span data-stu-id="3e57b-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

