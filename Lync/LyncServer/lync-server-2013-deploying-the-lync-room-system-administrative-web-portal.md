---
title: Lync Server 2013：部署 Lync 会议室系统管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945532f4f0514263ed0d72e00ac5224aa6d7120b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="140c2-102">在 Lync Server 2013 中部署 Lync 会议室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="140c2-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="140c2-103">_**上次修改的主题：** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="140c2-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="140c2-104">Microsoft Lync Server 2013 Lync 会议室系统（LRS）管理 Web 门户是一个 Web 门户，组织可以使用它来维护其 Lync 会议室系统会议室。</span><span class="sxs-lookup"><span data-stu-id="140c2-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="140c2-105">管理员可以使用 LRS 管理 Web 门户来监视 LRS 运行状况，例如，通过监视连接的音频/视频设备。</span><span class="sxs-lookup"><span data-stu-id="140c2-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="140c2-106">通过此门户，管理员可以远程收集诊断信息，以监视会议室运行状况。</span><span class="sxs-lookup"><span data-stu-id="140c2-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="140c2-107">在每个 Lync 前端服务器上部署 LRS 管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="140c2-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="140c2-108">本指南为管理员提供了有关如何安装和配置 LRS 管理 Web 门户的说明。</span><span class="sxs-lookup"><span data-stu-id="140c2-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="140c2-109">它适用于熟悉 Lync Server 管理的管理员，以及拥有修改 Lync Server 拓扑的管理员用户权限的人员。</span><span class="sxs-lookup"><span data-stu-id="140c2-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="140c2-110">在服务器上部署 LRS 管理 Web 门户后，管理员可以通过从其自己的计算机或便携式计算机登录网站来检查所有 LRS 聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="140c2-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="140c2-111">在 Microsoft Lync Server 2013 部署中安装 LRS 管理 Web 门户时，应使用<A href="http://go.microsoft.com/fwlink/p/?linkid=544806">适用于 Lync server 2013 的 Microsoft Lync 会议室系统管理 Web 门户</A>。</span><span class="sxs-lookup"><span data-stu-id="140c2-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="140c2-112">新版本的 LRS 管理 Web 门户适用于 Skype for business Server 2015，但您不应安装该版本，除非您已部署 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="140c2-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="140c2-113">下载<A href="http://go.microsoft.com/fwlink/?linkid=544807">适用于 Skype for Business Server 2015 的 Microsoft Lync 会议室系统管理 Web 门户</A>。</span><span class="sxs-lookup"><span data-stu-id="140c2-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="140c2-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="140c2-114">In This Section</span></span>

[<span data-ttu-id="140c2-115">为 Lync 会议室系统管理 Web 门户配置 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="140c2-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="140c2-116">在 Lync Server 2013 中安装 Lync 会议室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="140c2-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="140c2-117">在 Lync Server 2013 中使用 Lync 会议室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="140c2-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="140c2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="140c2-118">See Also</span></span>


[<span data-ttu-id="140c2-119">在 Lync Server 2013 中部署会议</span><span class="sxs-lookup"><span data-stu-id="140c2-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

