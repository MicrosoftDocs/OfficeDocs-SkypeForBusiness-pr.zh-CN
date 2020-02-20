---
title: Lync Server 2013：测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625de6144ca793ef475ec77721f8a76178a87404
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7cdfb-102">在 Lync Server 2013 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="7cdfb-102">Test SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cdfb-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7cdfb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7cdfb-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="7cdfb-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="7cdfb-106">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="7cdfb-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="7cdfb-108">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="7cdfb-109">安装 Microsoft Lync Server 2013 时，将为您创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="7cdfb-110">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="7cdfb-111">管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-111">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="7cdfb-112">只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 测试中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-112">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="7cdfb-113">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7cdfb-114">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="7cdfb-115">测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="7cdfb-115">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="7cdfb-116">以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。</span><span class="sxs-lookup"><span data-stu-id="7cdfb-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

