---
title: Lync Server 2013：通知配置先决条件和角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="0b5d0-102">Lync Server 2013 中的通知配置先决条件和角色</span><span class="sxs-lookup"><span data-stu-id="0b5d0-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b5d0-103">_**主题上次修改时间：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0b5d0-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0b5d0-104">"发布" 是企业语音呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="0b5d0-105">本主题介绍了在配置公告和执行配置任务所需的角色分配之前需要具备的准备工作。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="0b5d0-106">本部分假设你已阅读与公告相关的规划文档（请参阅[在 Lync Server 2013 中规划通话管理功能](lync-server-2013-planning-for-call-management-features.md)）。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="0b5d0-107">公告配置先决条件</span><span class="sxs-lookup"><span data-stu-id="0b5d0-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="0b5d0-108">通知应用程序需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="0b5d0-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="0b5d0-109">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="0b5d0-109">Application service</span></span>

  - <span data-ttu-id="0b5d0-110">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="0b5d0-110">Response Group application</span></span>

  - <span data-ttu-id="0b5d0-111">文件存储，用于保存音频文件</span><span class="sxs-lookup"><span data-stu-id="0b5d0-111">File Store, to hold audio files</span></span>

<span data-ttu-id="0b5d0-112">在部署企业语音时，默认情况下会安装所有这些组件。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="0b5d0-113">公告配置角色</span><span class="sxs-lookup"><span data-stu-id="0b5d0-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="0b5d0-114">可以使用以下管理工具配置公告：</span><span class="sxs-lookup"><span data-stu-id="0b5d0-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="0b5d0-115">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="0b5d0-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="0b5d0-116">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="0b5d0-116">Lync Server Management Shell</span></span>

<span data-ttu-id="0b5d0-117">配置公告应用程序需要以下管理角色之一：</span><span class="sxs-lookup"><span data-stu-id="0b5d0-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="0b5d0-118">**CsVoiceAdministrator**   此管理员角色可以创建、配置和管理所有与语音相关的设置和策略，包括公告设置。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="0b5d0-119">**CsServerAdministrator**   此管理员角色可以管理和监视服务器和服务并对其进行故障排除，并配置所有公告设置。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="0b5d0-120">**CsAdministrator**   此管理员角色可以执行所有管理任务和修改所有设置。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="0b5d0-121">**CsViewOnlyAdministrator**   此管理员角色可以查看部署以监控部署运行状况。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b5d0-122">有关管理员用户权限的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中规划基于角色的访问控制</A>。</span><span class="sxs-lookup"><span data-stu-id="0b5d0-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b5d0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b5d0-123">See Also</span></span>


[<span data-ttu-id="0b5d0-124">在 Lync Server 2013 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="0b5d0-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="0b5d0-125">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="0b5d0-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

