---
title: Lync Server 2013：还原企业版成员服务器
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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="560bc-102">在 Lync Server 2013 中还原企业版成员服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="560bc-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="560bc-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="560bc-104">如果运行下列服务器角色之一的服务器失败，请按照本主题中的过程还原服务器。</span><span class="sxs-lookup"><span data-stu-id="560bc-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="560bc-105">如果多台服务器独立失败，请按照每台服务器的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="560bc-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="560bc-106">前端服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-106">Front End Server</span></span>

  - <span data-ttu-id="560bc-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-107">Mediation Server</span></span>

  - <span data-ttu-id="560bc-108">控制器</span><span class="sxs-lookup"><span data-stu-id="560bc-108">Director</span></span>

  - <span data-ttu-id="560bc-109">持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="560bc-110">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="560bc-111">我们建议你先拍摄系统的映像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="560bc-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="560bc-112">你可以将此映像用作回退点，以防在还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="560bc-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="560bc-113">您可能希望在安装操作系统和 SQL Server 后获取图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="560bc-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="560bc-114">还原成员服务器</span><span class="sxs-lookup"><span data-stu-id="560bc-114">To restore a member server</span></span>

1.  <span data-ttu-id="560bc-115">从具有与故障服务器相同的完全限定的域名（FQDN）开始，安装一个全新或新的服务器，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="560bc-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="560bc-116">按照组织的服务器部署过程执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="560bc-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="560bc-117">从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="560bc-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="560bc-118">通过浏览找到 Lync Server 安装文件夹或媒体，然后启动\\安装程序\\Amd64\\Setup.exe 中的 lync server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="560bc-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="560bc-119">按照部署向导执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="560bc-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="560bc-120">运行**步骤1：安装本地配置存储**以安装本地配置文件。</span><span class="sxs-lookup"><span data-stu-id="560bc-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="560bc-121">运行**步骤2：设置或删除 Lync Server 组件**以安装 lync server 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="560bc-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="560bc-122">运行**步骤3：请求、安装或分配证书**以分配证书。</span><span class="sxs-lookup"><span data-stu-id="560bc-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="560bc-123">运行**步骤4：启动服务**以启动服务器上的服务。</span><span class="sxs-lookup"><span data-stu-id="560bc-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="560bc-124">有关运行部署向导的详细信息，请参阅要还原的服务器角色的部署文档。</span><span class="sxs-lookup"><span data-stu-id="560bc-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

