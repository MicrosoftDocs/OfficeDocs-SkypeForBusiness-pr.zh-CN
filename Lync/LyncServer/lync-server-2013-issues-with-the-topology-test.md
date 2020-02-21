---
title: Lync Server 2013：拓扑测试问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3e9b587a286cdff2b7ef08ec217a420792b121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="eae90-102">Lync Server 2013 中的拓扑测试问题</span><span class="sxs-lookup"><span data-stu-id="eae90-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae90-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="eae90-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="eae90-104">与**enable-cstopology** cmdlet 类似，最佳实践分析工具提供了一种验证 Lync Server 2013 在全局级别正常运行的方法。</span><span class="sxs-lookup"><span data-stu-id="eae90-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="eae90-105">默认情况下，最佳实践分析工具（如 cmdlet）将检查整个 Lync Server 2013 基础结构，验证所需的服务是否正在运行，以及是否为这些服务以及通用用户权限设置了相应的用户权限和权限安装 Lync Server 2013 时创建的安全组。</span><span class="sxs-lookup"><span data-stu-id="eae90-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="eae90-106">除了验证 Lync Server 的整体有效性之外， **enable-cstopology**还会检查特定服务的有效性。</span><span class="sxs-lookup"><span data-stu-id="eae90-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="eae90-107">有关使用 cmdlet 测试特定服务的详细信息，请参阅 Lync Server 命令行管理程序文档中的[enable-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 。</span><span class="sxs-lookup"><span data-stu-id="eae90-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="eae90-108">使用以下信息可帮助解决您的拓扑问题。</span><span class="sxs-lookup"><span data-stu-id="eae90-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eae90-p103">最佳做法分析器可能无法访问和扫描您的边缘服务器，具体取决于您的边缘服务器的配置和任何相关外围网络设置（包括防火墙设置和权限）。如果将边缘服务器包含在扫描中并且报告指示访问边缘服务器时出现问题，请清除“边缘服务器”<STRONG></STRONG>复选框并重新运行扫描以防止报告中出现问题。</span><span class="sxs-lookup"><span data-stu-id="eae90-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="eae90-111">解决拓扑问题</span><span class="sxs-lookup"><span data-stu-id="eae90-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="eae90-112">如果拓扑测试发现您的拓扑有问题，那么这些问题可能由您在发布或启用拓扑时发生的问题导致。</span><span class="sxs-lookup"><span data-stu-id="eae90-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="eae90-113">对拓扑进行更改时，仅当发布和启用了这些更改，它们才会生效。</span><span class="sxs-lookup"><span data-stu-id="eae90-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="eae90-114">您必须使用拓扑生成器进行拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="eae90-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="eae90-115">在进行更改后，您可以使用拓扑生成器发布和启用这些更改。</span><span class="sxs-lookup"><span data-stu-id="eae90-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="eae90-116">发布更改时，新的信息（例如，新网站或新的服务器角色）将被写入到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="eae90-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="eae90-117">但是，这些新（或最新修改的）对象不会立即加入您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="eae90-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="eae90-118">仅当启用了已更新的拓扑，对象才会加入您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="eae90-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="eae90-119">如果在拓扑生成器中选择 "发布" 选项，则会发生这两个步骤：发布更改（即，它们被写入到中央管理存储），然后启用新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="eae90-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="eae90-120">默认情况下，RTCUniversalServerAdmins 组的成员有权运行 **Publish-CsTopology** cmdlet 和 **Enable-CsTopology** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eae90-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="eae90-121">但是，如果尚未委派安装权限，您必须以域管理员身份登录才能运行 **Publish-CsTopology**。</span><span class="sxs-lookup"><span data-stu-id="eae90-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="eae90-122">若要向 RTCUniversalServerAdmins 提供实际使用**enable-cstopology** cmdlet 的权限，您必须在每个包含运行 Lync Server 服务的计算机的 Active Directory 容器上运行**CsSetupPermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eae90-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="eae90-123">若要使 RTCUniversalServerAdmins 能够使用**enable-cstopology** cmdlet，您必须针对每个包含运行 Lync Server 服务的计算机的 Active Directory 域服务容器运行**CsSetupPermission** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eae90-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="eae90-124">请注意，这适用于使用拓扑生成器启用和发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="eae90-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="eae90-125">如果您没有使用**CsSetupPermission**委派权限，则只有域管理员可以通过拓扑生成器启用和发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="eae90-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

