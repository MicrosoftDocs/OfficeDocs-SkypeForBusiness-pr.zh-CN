---
title: 'Lync Server 2013: 部署 Lync 会议室系统管理 Web 门户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="b43bc-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b43bc-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b43bc-103">_**主题上次修改时间:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="b43bc-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="b43bc-104">Microsoft Lync Server 2013 Lync 会议室系统 (LRS) 管理 Web 门户是一个 Web 门户, 组织可以使用该门户维护其 Lync 会议室系统会议室。</span><span class="sxs-lookup"><span data-stu-id="b43bc-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="b43bc-105">管理员可以使用 LRS 管理 Web 门户监视 LRS 运行状况, 例如通过监视连接的音频/视频设备进行监视。</span><span class="sxs-lookup"><span data-stu-id="b43bc-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="b43bc-106">通过此门户, 管理员可以远程收集诊断信息以监控会议室的运行状况。</span><span class="sxs-lookup"><span data-stu-id="b43bc-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="b43bc-107">在每个 Lync 前端服务器上部署 LRS 管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="b43bc-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="b43bc-108">本指南提供有关如何安装和配置 LRS 管理 Web 门户的管理员的说明。</span><span class="sxs-lookup"><span data-stu-id="b43bc-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="b43bc-109">它适用于了解 Lync Server 管理知识的管理员, 以及拥有修改 Lync Server 拓扑的管理员用户权限的人员。</span><span class="sxs-lookup"><span data-stu-id="b43bc-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="b43bc-110">在服务器上部署 LRS 管理 Web 门户后, 管理员可以通过从其自己的计算机或笔记本电脑登录网站来检查所有 LRS 聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="b43bc-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b43bc-111">在 Microsoft Lync Server 2013 部署中安装 LRS 管理 Web 门户时, 应使用<A href="http://go.microsoft.com/fwlink/p/?linkid=544806">适用于 Lync server 2013 的 Microsoft Lync 会议室系统管理 Web 门户</A>。</span><span class="sxs-lookup"><span data-stu-id="b43bc-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="b43bc-112">Skype for business Server 2015 提供了新版本的 LRS 管理 Web 门户, 但除非已部署 Skype for business Server 2015, 否则不应安装该版本。</span><span class="sxs-lookup"><span data-stu-id="b43bc-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="b43bc-113">下载<A href="http://go.microsoft.com/fwlink/?linkid=544807">适用于 Skype for Business Server 2015 的 Microsoft Lync 会议室系统管理 Web 门户</A>。</span><span class="sxs-lookup"><span data-stu-id="b43bc-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b43bc-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="b43bc-114">In This Section</span></span>

[<span data-ttu-id="b43bc-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="b43bc-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="b43bc-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b43bc-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="b43bc-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b43bc-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b43bc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b43bc-118">See Also</span></span>


[<span data-ttu-id="b43bc-119">在 Lync Server 2013 中部署会议</span><span class="sxs-lookup"><span data-stu-id="b43bc-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

