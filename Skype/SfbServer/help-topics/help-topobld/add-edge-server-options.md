---
title: 添加边缘服务器选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 选择要为边缘池启用的每个功能。 默认情况下，边缘池支持组织中使用虚拟专用网络通过 VPN (从防火墙外部登录) 。 此外，还具有以下边缘池功能选项：
ms.openlocfilehash: f653f6a5b2c242416d6c644d5c7a5fc4daffc441
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835492"
---
# <a name="add-edge-server-options"></a><span data-ttu-id="41135-105">添加边缘服务器选项</span><span class="sxs-lookup"><span data-stu-id="41135-105">Add Edge Server Options</span></span>

<span data-ttu-id="41135-106">选择要为边缘池启用的每个功能。</span><span class="sxs-lookup"><span data-stu-id="41135-106">Select each feature that you want to enable for the Edge pool.</span></span> <span data-ttu-id="41135-107">默认情况下，边缘池支持组织中使用虚拟专用网络通过 VPN (从防火墙外部登录) 。</span><span class="sxs-lookup"><span data-stu-id="41135-107">By default, the Edge pool supports remote users in your organization who sign in to from outside the firewall by using a virtual private network (VPN).</span></span> <span data-ttu-id="41135-108">此外，还具有以下边缘池功能选项：</span><span class="sxs-lookup"><span data-stu-id="41135-108">You also have the following Edge pool feature options:</span></span>

- <span data-ttu-id="41135-109">为所有边缘服务（包括访问边缘服务、Web 会议边缘服务和 A/V 边缘服务）使用单个完全限定域名 (FQDN) 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="41135-109">Use of a single fully qualified domain name (FQDN) and IP address for all edge services, including the Access Edge service, Web Conferencing Edge service, and A/V Edge service.</span></span> <span data-ttu-id="41135-110">如果不选择使用单个 FQDN 和 IP 地址的选项，则需要在部署过程中分别为这三个边缘服务指定单独的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="41135-110">If you do not select the option to use a single FQDN and IP address, you will need to specify a separate FQDN and IP address for each of these three Edge services as part of the deployment process.</span></span> <span data-ttu-id="41135-111">有关边缘服务的详细信息，请参阅规划文档中的[外部用户访问所需的组件](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41135-111">For details about the Edge services, see [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) in the Planning documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41135-p104">如果选择此选项，则必须为每个边缘服务指定不同的端口号（推荐的默认端口设置为：访问边缘服务为 444，Web 会议边缘服务为 8057，A/V 边缘服务为 443）。选择此选项可帮助防止潜在的连接问题，并简化配置，因为可以输入一个同时用于三个服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="41135-p104">If you select this option, you must specify a different port number for each of the Edge services (recommended default port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then enter one FQDN that is used for all three services.</span></span>

- <span data-ttu-id="41135-114">支持联盟。</span><span class="sxs-lookup"><span data-stu-id="41135-114">Support for federation.</span></span> <span data-ttu-id="41135-115">如果要支持内部用户与组织外受信任域中的用户（包括支持的公共即时消息 (IM) 提供商的任何用户）之间的通信，可选择此选项。</span><span class="sxs-lookup"><span data-stu-id="41135-115">Select this option if you want to support communication between internal users and users in trusted domains outside your organization, including any users of a supported public instant messaging (IM) provider.</span></span> <span data-ttu-id="41135-116">如果选择此选项，则需要配置对要支持的特定联盟域和公共 IM 连接服务提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="41135-116">If you select this option, you will need to configure support for the specific federated domains and public IM connectivity service providers that you want to support.</span></span> <span data-ttu-id="41135-117">有关配置对联盟和其他类型的外部用户访问的支持的详细信息，请参阅边缘服务器部署文档中的[配置对外部用户访问的支持](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41135-117">For details about configuring support for federation and other types of external user access, see [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) in the Edge Server Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41135-p106">只能为联盟对外发布组织中的一个前端池或 Standard 边缘服务器。联盟用户（包括公共 IM 用户）的所有访问都将通过相同的边缘池或单个边缘服务器。例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="41135-p106">Only one Front End pool or Standard Edge Server in your organization may be published externally for federation. All access by federated users, including public IM users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

- <span data-ttu-id="41135-p107">启用 XMPP 联盟。如果要支持内部用户和信任的 XMPP 合作伙伴之间的通信，则选择此选项。</span><span class="sxs-lookup"><span data-stu-id="41135-p107">Enable XMPP federation. Select this option if you want to support communication between internal users and trusted XMPP partners.</span></span>

<span data-ttu-id="41135-124">可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="41135-124">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="41135-125">有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41135-125">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


