---
title: Lync Server 2013：验证外部用户连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="49071-102">在 Lync Server 2013 中验证外部用户连接</span><span class="sxs-lookup"><span data-stu-id="49071-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49071-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="49071-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="49071-104">验证外部用户的连接需要确保将用户与服务器和端口连接到访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="49071-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="49071-105">一个有价值的资源, 可用于确认您的配置, 以及连接、发送和接收外部用户访问所需方案的正确消息的功能是远程连接分析器<http://www.testocsconnectivity.com>网站 ()。</span><span class="sxs-lookup"><span data-stu-id="49071-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="49071-106">网站由 Microsoft 支持人员管理和维护。</span><span class="sxs-lookup"><span data-stu-id="49071-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="49071-107">若要访问远程连接分析器, 请在浏览器中打开网站, 然后按照说明选择方案。</span><span class="sxs-lookup"><span data-stu-id="49071-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="49071-108">测试外部用户和外部访问的连接性</span><span class="sxs-lookup"><span data-stu-id="49071-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="49071-109">外部用户访问的测试应包括你的组织支持的每种类型的外部用户, 包括以下任何或所有类型:</span><span class="sxs-lookup"><span data-stu-id="49071-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="49071-110">至少一个联盟域中的用户, 并测试即时消息、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="49071-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="49071-111">您的组织支持的每个公共 IM 服务提供商的用户 (以及已完成的预配)。</span><span class="sxs-lookup"><span data-stu-id="49071-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="49071-112">匿名用户。</span><span class="sxs-lookup"><span data-stu-id="49071-112">Anonymous users.</span></span>

  - <span data-ttu-id="49071-113">组织内远程登录 Lync 但不使用 VPN 的用户。</span><span class="sxs-lookup"><span data-stu-id="49071-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="49071-114">这些测试确定你的边缘服务器是否:</span><span class="sxs-lookup"><span data-stu-id="49071-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="49071-115">使用 Telnet 客户端从网络外侦听所需端口。</span><span class="sxs-lookup"><span data-stu-id="49071-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="49071-116">示例: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="49071-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="49071-117">根据你的部署, 对你在 Edge 服务器或 Edge 服务器池中使用的端口执行上述测试。</span><span class="sxs-lookup"><span data-stu-id="49071-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="49071-118">执行准确的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="49071-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="49071-119">从你的网络外部 ping 你的边缘或边缘池的每个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="49071-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="49071-120">即使 ping 失败, 您也可以看到 IP 地址, 您可以将其与您分配的 IP 地址进行比较。</span><span class="sxs-lookup"><span data-stu-id="49071-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

