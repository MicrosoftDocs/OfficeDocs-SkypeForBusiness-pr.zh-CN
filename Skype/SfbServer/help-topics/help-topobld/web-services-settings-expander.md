---
title: Web 服务设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: 在拓扑生成器内，您可以修改用于内部和外部 Web 服务的端口设置。 此外，如果要部署域名系统 (DNS) 负载平衡，可以使用拓扑生成器配置池的完全限定域名 (FQDN) ，该域名解析为该池中所有服务器的物理 IP 地址。
ms.openlocfilehash: 00fbf89b6e8121b5e2cd8d1b8d544531cc411e3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817812"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="084fe-104">Web 服务设置扩展器</span><span class="sxs-lookup"><span data-stu-id="084fe-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="084fe-105">在拓扑生成器内，您可以修改用于内部和外部 Web 服务的端口设置。</span><span class="sxs-lookup"><span data-stu-id="084fe-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="084fe-106">此外，如果要部署域名系统 (DNS) 负载平衡，可以使用拓扑生成器配置池的完全限定域名 (FQDN) ，该域名解析为该池中所有服务器的物理 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="084fe-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="084fe-107">编辑 Web 服务设置</span><span class="sxs-lookup"><span data-stu-id="084fe-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="084fe-108">选择相应的 Standard Edition 前端服务器或相应的 Enterprise Edition 前端池，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="084fe-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="084fe-109">在“编辑属性”对话框中，单击“Web 服务”选项卡。</span><span class="sxs-lookup"><span data-stu-id="084fe-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="084fe-110">如果您具有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="084fe-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="084fe-111">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 **pool01.contoso.com，** 则不能将 pool01.contoso.com **用于另** 一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="084fe-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="084fe-112">如果还要部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器是唯一的。</span><span class="sxs-lookup"><span data-stu-id="084fe-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="084fe-113">如果您决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。</span><span class="sxs-lookup"><span data-stu-id="084fe-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="084fe-114">如果要编辑 Enterprise Edition 池的属性，则可以选择“覆盖 FQDN”。</span><span class="sxs-lookup"><span data-stu-id="084fe-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="084fe-115">仅在使用域名系统 (DNS) 负载平衡时，才能选择此选项。</span><span class="sxs-lookup"><span data-stu-id="084fe-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="084fe-116">如果正在使用 DNS 负载平衡，请选择“覆盖 FQDN”，然后在文本框中键入池的 FQDN，该 FQDN 会解析为该池中所有服务器的物理 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="084fe-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="084fe-117">如果没有使用 DNS 负载平衡且没有选择“覆盖 FQDN”，则无法更改内部 Web 服务 FQDN。</span><span class="sxs-lookup"><span data-stu-id="084fe-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="084fe-118">内部 Web 服务 FQDN 是内部用户用于连接到 Skype for Business Server 的 URL。</span><span class="sxs-lookup"><span data-stu-id="084fe-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="084fe-p105">或者，为“侦听端口”和“已发布端口”输入新的 HTTP、HTTPS 或 HTTP 和 HTTPS 的值。侦听端口是 Internet 信息服务 (IIS) 用于侦听传入会话初始协议 (SIP) 流量的端口；已发布端口是在负载平衡器或反向代理服务器上配置的端口，同样用于侦听传入 SIP 流量。默认情况下，HTTP 侦听端口和 HTTP 已发布端口均设置为端口 80；对应的 HTTPS 端口均设置为 443。两个 HTTP 已发布端口的默认值为 8080，对应的 HTTPS 端口则设置为 4443。</span><span class="sxs-lookup"><span data-stu-id="084fe-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="084fe-123">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="084fe-123">Click **OK**.</span></span>
    
<span data-ttu-id="084fe-124">如果修改内部 FQDN 或任何侦听端口分配，则必须在池中的所有服务器上重新运行本地设置才能使那些更改生效。</span><span class="sxs-lookup"><span data-stu-id="084fe-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

