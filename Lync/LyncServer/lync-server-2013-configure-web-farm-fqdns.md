---
title: Lync Server 2013：配置 web 场 Fqdn
description: Lync Server 2013：配置 web 场 Fqdn。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566658"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="bac2c-103">为 Lync Server 2013 配置 web 场 Fqdn</span><span class="sxs-lookup"><span data-stu-id="bac2c-103">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac2c-104">_**上次修改的主题：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="bac2c-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="bac2c-105">在拓扑生成器中定义 Standard Edition server、前端池、控制器或控制器池的配置时，请将外部 web 服务完全限定的域名配置 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="bac2c-105">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="bac2c-106">在托管在 Standard Edition server 或前端池中的客户端登录过程中，配置的 web 服务的 Fqdn 是通过带内设置的方式发送的。</span><span class="sxs-lookup"><span data-stu-id="bac2c-106">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="bac2c-107">如果需要添加或更改外部 web 服务 URL，请使用拓扑生成器配置或重新配置 web 服务配置（使用本主题中的过程）。</span><span class="sxs-lookup"><span data-stu-id="bac2c-107">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="bac2c-108">配置 Web 服务的外部池 FQDN</span><span class="sxs-lookup"><span data-stu-id="bac2c-108">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="bac2c-109">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="bac2c-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="bac2c-110">在拓扑生成器中，在 " **Standard Edition 前端**"、" **Enterprise edition 前端**" 和 " **控制器**" 下的控制台树中，右键单击需要编辑的池名称，然后单击 " **编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="bac2c-110">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="bac2c-111">在“Web 服务”\*\*\*\* 部分，添加或编辑“外部 Web 服务 FQDN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bac2c-111">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="bac2c-p102">查看并调整 HTTP 和 HTTPS 的“侦听端口”\*\*\*\*。默认值为：</span><span class="sxs-lookup"><span data-stu-id="bac2c-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="bac2c-114">**侦听端口：** HTTP 8080、HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="bac2c-114">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="bac2c-115">**发布端口：** HTTP 80、HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="bac2c-115">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="bac2c-116">其中“侦听端口”\*\*\*\* 是外部 Web 服务将配置为通过其接收来自反向代理的请求的端口，而“已发布端口”\*\*\*\* 是由反向代理外部发布的端口且用于在带内设置期间与客户端进行通信。</span><span class="sxs-lookup"><span data-stu-id="bac2c-116">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="bac2c-117">在完成添加和更新后，单击“确定”\*\*\*\* 继续。</span><span class="sxs-lookup"><span data-stu-id="bac2c-117">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="bac2c-118">右键单击 " **Lync Server 2013**"，然后单击 " **发布**"。</span><span class="sxs-lookup"><span data-stu-id="bac2c-118">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bac2c-119">成功完成发布后，可能会显示一个链接，告知您需要执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="bac2c-119">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="bac2c-120">如果单击此链接，则会打开受拓扑生成器中所做更改影响的服务器列表，这将要求您在列出的每台服务器上重新运行 Lync Server 部署向导，以更新添加、删除或更改的组件的配置。</span><span class="sxs-lookup"><span data-stu-id="bac2c-120">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="bac2c-121">对组织中的每个 Standard Edition 服务器、前端池、控制器或控制器池重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="bac2c-121">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

