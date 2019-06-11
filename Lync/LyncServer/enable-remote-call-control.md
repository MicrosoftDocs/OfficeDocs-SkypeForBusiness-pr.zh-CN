---
title: 启用远程呼叫控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="3cd27-102">启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="3cd27-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cd27-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3cd27-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3cd27-104">远程呼叫控制使用户能够使用 Lync Server 2013 控制其桌面专用分支机构 (PBX) 手机。</span><span class="sxs-lookup"><span data-stu-id="3cd27-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="3cd27-105">如果你在旧环境中部署了远程呼叫控制, 并且希望迁移到 Lync Server 2013, 则需要执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="3cd27-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="3cd27-106">安装 SIP/CSTA 网关并将其配置为与你的 PBX 通信。</span><span class="sxs-lookup"><span data-stu-id="3cd27-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="3cd27-107">当您部署 Lync Server 2013 试验池时, 您需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="3cd27-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="3cd27-108">合并拓扑并迁移策略和设置后, 将 Lync Server 2013 配置为将 CSTA 请求路由到 SIP/CSTA 网关。</span><span class="sxs-lookup"><span data-stu-id="3cd27-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="3cd27-109">此步骤是遵循自动迁移的手动步骤。</span><span class="sxs-lookup"><span data-stu-id="3cd27-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="3cd27-110">若要为 CSTA 请求配置路由, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="3cd27-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="3cd27-111">删除旧式授权主机条目 (在 Lync Server 2013 中称为 "*受信任的服务器条目*")。</span><span class="sxs-lookup"><span data-stu-id="3cd27-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="3cd27-112">如果你要从旧部署迁移用户, 请确保删除你为 SIP/CSTA 网关创建的所有现有授权主机条目, 然后再在 Lync Server 2013 试验池上配置新的受信任的应用程序条目。</span><span class="sxs-lookup"><span data-stu-id="3cd27-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="3cd27-113">有关如何删除以前授权的主机条目的详细信息, 请参阅[删除授权主机条目](remove-an-authorized-host-entry.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd27-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="3cd27-114">为远程呼叫控制配置静态路由。</span><span class="sxs-lookup"><span data-stu-id="3cd27-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="3cd27-115">你可以为希望支持远程呼叫控制的单个池配置静态路由, 也可以配置全局静态路由, 以便未使用池级别的静态路由配置的每个池都使用全局静态路由。</span><span class="sxs-lookup"><span data-stu-id="3cd27-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="3cd27-116">有关如何配置静态路由的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)"。</span><span class="sxs-lookup"><span data-stu-id="3cd27-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3cd27-117">在要支持远程呼叫控制的每个池上配置 "远程呼叫控制" 的受信任应用程序条目。</span><span class="sxs-lookup"><span data-stu-id="3cd27-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="3cd27-118">有关如何配置受信任的应用程序条目的详细信息, 请参阅部署文档中的[Lync Server 2013 中的 "配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)"。</span><span class="sxs-lookup"><span data-stu-id="3cd27-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="3cd27-119">如果你部署了使用传输控制协议 (TCP) 连接到 Lync Server 2013 的 SIP/CSTA 网关, 请在拓扑生成器中定义网关的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3cd27-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="3cd27-120">有关定义 IP 地址的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)"。</span><span class="sxs-lookup"><span data-stu-id="3cd27-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="3cd27-121">通过启用远程呼叫控制并分配行服务器统一资源标识符 (URI) 和行 URI, 为远程呼叫控制配置 Lync 2013 用户。</span><span class="sxs-lookup"><span data-stu-id="3cd27-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="3cd27-122">将用户从旧版部署迁移到 Lync Server 2013 时, 将迁移远程呼叫控制设置和其他用户设置。</span><span class="sxs-lookup"><span data-stu-id="3cd27-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="3cd27-123">如果你在旧部署中自定义了通讯录电话号码规范化规则, 则需要在完成策略和设置的自动迁移后执行一些手动任务以迁移自定义的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="3cd27-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="3cd27-124">如果您没有自定义规范化规则, 通讯簿将随拓扑的其余部分一起迁移。</span><span class="sxs-lookup"><span data-stu-id="3cd27-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="3cd27-125">有关手动迁移自定义规范化规则的详细信息, 请参阅[迁移通讯簿](migrate-address-book_1.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd27-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

