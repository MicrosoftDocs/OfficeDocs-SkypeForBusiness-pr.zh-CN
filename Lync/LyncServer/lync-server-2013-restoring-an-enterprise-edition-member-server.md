---
title: Lync Server 2013：还原企业版成员服务器
description: Lync Server 2013：还原企业版成员服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576048"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="2ee24-103">在 Lync Server 2013 中还原企业版成员服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee24-104">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2ee24-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2ee24-105">如果运行以下服务器角色之一的服务器出现故障，请按照本主题中的过程还原服务器。</span><span class="sxs-lookup"><span data-stu-id="2ee24-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="2ee24-106">如果多个服务器出现故障，请针对每个服务器单独执行该过程。</span><span class="sxs-lookup"><span data-stu-id="2ee24-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="2ee24-107">Front End Server － 前端服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-107">Front End Server</span></span>

  - <span data-ttu-id="2ee24-108">中介服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-108">Mediation Server</span></span>

  - <span data-ttu-id="2ee24-109">控制器</span><span class="sxs-lookup"><span data-stu-id="2ee24-109">Director</span></span>

  - <span data-ttu-id="2ee24-110">持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="2ee24-111">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2ee24-112">我们建议您先获取系统的图像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="2ee24-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2ee24-113">您可以将此图像用作回滚点，以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="2ee24-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2ee24-114">您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="2ee24-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="2ee24-115">还原成员服务器</span><span class="sxs-lookup"><span data-stu-id="2ee24-115">To restore a member server</span></span>

1.  <span data-ttu-id="2ee24-116">从具有相同完全限定的域名 (FQDN) 为故障服务器的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="2ee24-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ee24-117">按照您组织的服务器部署过程来执行该步骤。</span><span class="sxs-lookup"><span data-stu-id="2ee24-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="2ee24-118">从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="2ee24-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="2ee24-119">浏览到 Lync Server 安装文件夹或媒体，然后启动位于 \\ setup amd64Setup.exe 的 Lync Server 部署向导 \\ \\ 。</span><span class="sxs-lookup"><span data-stu-id="2ee24-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="2ee24-120">按照部署向导的提示执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ee24-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="2ee24-121">运行“步骤 1: 安装本地配置存储”\*\*\*\* 以安装本地配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ee24-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="2ee24-122">运行 **步骤2：安装或删除 Lync Server 组件** 以安装 lync server 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="2ee24-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="2ee24-123">运行“步骤 3: 请求、安装或分配证书”\*\*\*\* 以分配证书。</span><span class="sxs-lookup"><span data-stu-id="2ee24-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="2ee24-124">运行“步骤 4: 启动服务”\*\*\*\* 以在服务器上启动服务。</span><span class="sxs-lookup"><span data-stu-id="2ee24-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="2ee24-125">有关运行部署向导的详细信息，请参阅部署文档以了解要还原的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="2ee24-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

