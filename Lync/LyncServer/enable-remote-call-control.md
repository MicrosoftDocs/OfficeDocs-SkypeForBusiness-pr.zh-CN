---
title: 启用远程呼叫控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa81c938d69aedbc599194c1d820fa4c40e3337
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502889"
---
# <a name="enable-remote-call-control"></a><span data-ttu-id="0c7b5-102">启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="0c7b5-102">Enable remote call control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7b5-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0c7b5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0c7b5-104">远程呼叫控制使用户能够使用 Lync Server 2013 控制其桌面专用交换机 (PBX) 电话。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="0c7b5-105">如果您在旧版环境中部署了远程呼叫控制并且想要迁移它的 Lync Server 2013，则需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0c7b5-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="0c7b5-106">安装并配置 SIP/CSTA 网关以与 PBX 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="0c7b5-107">在部署 Lync Server 2013 试点池时，您需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="0c7b5-108">在合并拓扑并迁移策略和设置之后，请将 Lync Server 2013 配置为将 CSTA 请求路由到 SIP/CSTA 网关。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="0c7b5-109">该步骤是自动迁移后要执行的手动步骤。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="0c7b5-110">要配置 CSTA 请求的路由，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c7b5-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="0c7b5-111">在 Lync Server 2013) 中删除旧版授权主机项 (称为 " *受信任的服务器项* "。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="0c7b5-112">如果要从旧版部署中迁移用户，请确保在 "Lync Server 2013" 引导池上配置新的受信任应用程序项之前，先删除为 SIP/CSTA 网关创建的所有现有授权主机条目。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="0c7b5-113">有关如何删除旧版授权主机条目的详细信息，请参阅 [删除授权主机条目](remove-an-authorized-host-entry.md)。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="0c7b5-114">为远程呼叫控制配置静态路由。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="0c7b5-115">您可以为希望支持远程呼叫控制的单个池配置静态路由，也可以配置一个全局静态路由，以便未配置池级静态路由的每个池使用全局静态路由。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="0c7b5-116">有关如何配置静态路由的详细信息，请参阅部署文档中的在 [Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0c7b5-117">在您希望支持远程呼叫控制的每个池中为远程呼叫控制配置受信任应用程序条目。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="0c7b5-118">有关如何配置受信任的应用程序条目的详细信息，请参阅部署文档中的在 [Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="0c7b5-119">如果您部署了使用传输控制协议 (TCP) 连接到 Lync Server 2013 的 SIP/CSTA 网关，请在拓扑生成器中定义网关的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="0c7b5-120">有关定义 IP 地址的详细信息，请参阅部署文档中的在 [Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) 。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="0c7b5-121">通过启用远程呼叫控制并分配线路服务器统一资源标识符 (URI) 和线路 URI，为 Lync 2013 用户配置远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="0c7b5-122">将用户从旧版部署迁移到 Lync Server 2013 时，远程呼叫控制设置将随其他用户设置一起迁移。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="0c7b5-123">如果您在旧部署中自定义了通讯簿电话号码规范化规则，则完成策略和设置的自动迁移后，需要执行一些手动操作以迁移自定义的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="0c7b5-124">如果未自定义规范化规则，通讯簿将随拓扑的其余部分一起迁移。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="0c7b5-125">有关手动迁移自定义规范化规则的详细信息，请参阅[Migrate Address Book](migrate-address-book_1.md)。</span><span class="sxs-lookup"><span data-stu-id="0c7b5-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

