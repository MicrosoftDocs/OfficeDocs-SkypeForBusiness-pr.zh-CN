---
title: Lync Server 2013：为分支站点定义 PSTN 网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08e2010b79213607992ab383b606e7b609ca75e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="94c33-102">在 Lync Server 2013 中为分支站点定义 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="94c33-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c33-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="94c33-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="94c33-104">在中心网站上执行此过程，其中包含至少一个前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="94c33-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94c33-105">执行该过程之前，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="94c33-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="94c33-106">必须在中央&nbsp;站点设置 Lync Server 2013 通信软件。</span><span class="sxs-lookup"><span data-stu-id="94c33-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="94c33-107">必须在中央站点上部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="94c33-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="94c33-108">定义 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="94c33-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="94c33-109">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server”\*\*\*\*，然后单击“Lync Server 拓扑生成器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94c33-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="94c33-110">在控制台树中展开中央站点，展开“分支机构站点”\*\*\*\*，再展开要为其定义公用电话交换网 (PSTN) 网关的分支站点的名称，然后展开“共享组件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94c33-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="94c33-111">右键单击“PSTN 网关”\*\*\*\*，然后单击“新建 IP/PSTN 网关”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94c33-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="94c33-112">在“定义新的 IP/PSTN 网关”\*\*\*\* 对话框中，单击“网关 FQDN 或 IP 地址”\*\*\*\*，然后键入要在分支站点部署的网关的完全限定域名 (FQDN) 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="94c33-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="94c33-113">单击“IP/PSTN 网关的侦听端口”\*\*\*\*，然后接受默认值。</span><span class="sxs-lookup"><span data-stu-id="94c33-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="94c33-114">在“SIP 传输协议”\*\*\*\* 列表中，单击网关使用的传输协议，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94c33-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94c33-115">出于安全考虑，强烈建议使用支持传输层安全性 (TLS) 的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="94c33-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="94c33-116">使用 cmdlet <STRONG>Set-CsPstnGateway</STRONG> 修改 PSTN 网关的属性。</span><span class="sxs-lookup"><span data-stu-id="94c33-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="94c33-117">有关详细信息，请参阅 Lync Server 命令行管理程序帮助中的<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">CsPstnGateway</A>。</span><span class="sxs-lookup"><span data-stu-id="94c33-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="94c33-118">分支站点恢复的**下一步**：[在 Lync Server 2013 中为分支站点恢复配置用户](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="94c33-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94c33-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94c33-119">See Also</span></span>


[<span data-ttu-id="94c33-120">Lync Server 2013 中的 PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="94c33-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

