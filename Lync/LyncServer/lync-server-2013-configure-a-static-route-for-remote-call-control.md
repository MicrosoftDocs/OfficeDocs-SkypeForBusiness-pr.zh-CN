---
title: Lync Server 2013：为远程呼叫控制配置静态路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6a388c602d30e6f60eac0c575d7640f63993f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="1e95a-102">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="1e95a-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e95a-103">_**主题上次修改时间:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="1e95a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="1e95a-104">远程呼叫控制要求每个 Lync 服务器池都配置了一个从该池中的路径到连接到专用分支交换 (PBX) 的 SIP/CSTA 网关。</span><span class="sxs-lookup"><span data-stu-id="1e95a-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="1e95a-105">此路径要求每个池对每个网关都有一个静态路由, 池将向该网关发送与 PBX 调用相关联的 SIP 呼叫控制消息。</span><span class="sxs-lookup"><span data-stu-id="1e95a-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="1e95a-106">如果为远程呼叫控制配置全局静态路由, 则未使用池级别的静态路由配置的每个池都将使用全局静态路由。</span><span class="sxs-lookup"><span data-stu-id="1e95a-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="1e95a-107">为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="1e95a-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="1e95a-108">登录到安装了 Lync Server Management Shell 的计算机作为 RTCUniversalServerAdmins 组的成员或为其分配了**CsStaticRoute** cmdlet 的基于角色的访问控制 (RBAC) 角色。</span><span class="sxs-lookup"><span data-stu-id="1e95a-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="1e95a-109">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="1e95a-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e95a-110">若要创建静态路由并将其放在 $TLSRoute 或 $TCPRoute 的变量中, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="1e95a-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="1e95a-111">若要匹配域的子域, 可以在 MatchUri 参数中指定一个通配符值。</span><span class="sxs-lookup"><span data-stu-id="1e95a-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="1e95a-112">例如, <STRONG>\*. contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1e95a-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="1e95a-113">该值匹配以后缀<STRONG>contoso.net</STRONG>结尾的任何域。</span><span class="sxs-lookup"><span data-stu-id="1e95a-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="1e95a-114">对于传输层安全 (TLS) 连接, 请在命令提示符处键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="1e95a-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        <span data-ttu-id="1e95a-115">例如：</span><span class="sxs-lookup"><span data-stu-id="1e95a-115">For example:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        <span data-ttu-id="1e95a-116">如果 UseDefaultCertificate 设置为 False, 则必须指定 TLSCertIssuer 和 TLSCertSerialNumber 参数。</span><span class="sxs-lookup"><span data-stu-id="1e95a-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="1e95a-117">这些参数指示颁发证书的证书颁发机构 (CA) 的名称, 该证书颁发机构 (CA) 分别用于在静态路由中使用的证书以及该 TLS 证书的序列号。</span><span class="sxs-lookup"><span data-stu-id="1e95a-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="1e95a-118">有关这些参数的详细信息, 请参阅 Lync Server Management Shell 帮助, 方法是在命令提示符处键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="1e95a-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full
    
      - <span data-ttu-id="1e95a-119">对于传输控制协议 (TCP) 连接, 请在命令提示符处键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="1e95a-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="1e95a-120">如果你指定完全限定的域名 (FQDN), 则必须首先配置域名系统 (DNS) A 记录。</span><span class="sxs-lookup"><span data-stu-id="1e95a-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        <span data-ttu-id="1e95a-121">例如：</span><span class="sxs-lookup"><span data-stu-id="1e95a-121">For example:</span></span>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        <span data-ttu-id="1e95a-122">以下是静态路由的可选参数的默认值:</span><span class="sxs-lookup"><span data-stu-id="1e95a-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="1e95a-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="1e95a-123">Enabled = True</span></span>
        
          - <span data-ttu-id="1e95a-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="1e95a-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="1e95a-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="1e95a-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="1e95a-126">我们强烈建议您不要更改这些默认值。</span><span class="sxs-lookup"><span data-stu-id="1e95a-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="1e95a-127">但是, 如果必须更改这些参数中的任何一个, 请参阅 Lync Server Management Shell 帮助, 方法是在命令提示符处键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="1e95a-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full

4.  <span data-ttu-id="1e95a-128">若要在中央管理存储中保留新创建的静态路由, 请根据需要运行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="1e95a-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e95a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e95a-129">See Also</span></span>


[<span data-ttu-id="1e95a-130">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项</span><span class="sxs-lookup"><span data-stu-id="1e95a-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="1e95a-131">在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址</span><span class="sxs-lookup"><span data-stu-id="1e95a-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

