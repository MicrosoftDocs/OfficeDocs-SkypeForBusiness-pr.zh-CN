---
title: 为远程呼叫控制配置受信任的应用程序条目
description: 为远程呼叫控制配置受信任的应用程序条目。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5341dc220853670cf000f5b0d5dc379c02fa51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570068"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="925d6-103">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目</span><span class="sxs-lookup"><span data-stu-id="925d6-103">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="925d6-104">_**上次修改的主题：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="925d6-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="925d6-105">必须将 SIP/CSTA 网关配置为受信任的应用程序，Lync Server 才能应用静态路由以将呼叫路由到网关。</span><span class="sxs-lookup"><span data-stu-id="925d6-105">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="925d6-106">如果要从以前版本的 Lync Server 部署迁移用户，请确保已删除所有现有的受信任的应用程序条目 (之前已) 您在执行本主题中的过程之前为 SIP/CSTA 网关创建的已授权主机条目。</span><span class="sxs-lookup"><span data-stu-id="925d6-106">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="925d6-107">有关详细信息，请参阅 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机 (可选) </A>。</span><span class="sxs-lookup"><span data-stu-id="925d6-107">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="925d6-108">如果您计划使用传输控制协议 (TCP) 连接来部署新的远程呼叫控制，则需要验证是否应在现有受信任的应用程序和池上设置 <STRONG>对所选 IP 地址的限制服务使用情况</STRONG> （如果要对新的受信任应用程序使用相同的 TCP 端口）。</span><span class="sxs-lookup"><span data-stu-id="925d6-108">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="925d6-109">为 SIP/CSTA 网关配置受信任的应用程序项</span><span class="sxs-lookup"><span data-stu-id="925d6-109">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="925d6-110">登录到安装了 Lync Server 命令行管理程序的计算机上，将其作为 RTCUniversalServerAdmins 组的成员或基于角色的访问控制 (RBAC) role （已为该角色分配了 **CsTrustedApplicationPool** cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="925d6-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="925d6-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="925d6-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="925d6-112">要创建受信任的应用程序项，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="925d6-112">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="925d6-113">对于传输层安全性 (TLS) 连接，请在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="925d6-113">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="925d6-114">例如：</span><span class="sxs-lookup"><span data-stu-id="925d6-114">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="925d6-115">对于传输控制协议 (TCP) 连接，请在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="925d6-115">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="925d6-116">例如：</span><span class="sxs-lookup"><span data-stu-id="925d6-116">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="925d6-117">要将受信任应用程序添加到池，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="925d6-117">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="925d6-118">对于 TLS 连接，请在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="925d6-118">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="925d6-119">例如：</span><span class="sxs-lookup"><span data-stu-id="925d6-119">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="925d6-120">对于 TCP 连接，请在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="925d6-120">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="925d6-121">例如：</span><span class="sxs-lookup"><span data-stu-id="925d6-121">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="925d6-122">要实现对拓扑所做的已发布更改，请在命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="925d6-122">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="925d6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="925d6-123">See Also</span></span>


[<span data-ttu-id="925d6-124">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="925d6-124">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="925d6-125">在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址</span><span class="sxs-lookup"><span data-stu-id="925d6-125">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

