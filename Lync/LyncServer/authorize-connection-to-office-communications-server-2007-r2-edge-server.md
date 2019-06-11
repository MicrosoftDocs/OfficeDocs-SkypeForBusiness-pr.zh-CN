---
title: 授权到 Office 通信服务器 2007 R2 Edge 服务器的连接
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f81d8aaf9a01fc73516778487f8cc9a2d28a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="9f3ac-102">授权到 Office 通信服务器 2007 R2 Edge 服务器的连接</span><span class="sxs-lookup"><span data-stu-id="9f3ac-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f3ac-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9f3ac-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9f3ac-104">对于你的试点池中的每个 Lync Server 2013 前端服务器或标准版服务器, 你必须更新授权连接到 Office 通信服务器 2007 R2 Edge 服务器的内部服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="9f3ac-105">如果没有这些更新, 通过使用旧版 Edge 服务器加入的用户的外部音频/视频 (A/V) 会议将不起作用。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="9f3ac-106">授权到 Office 通信服务器 2007 R2 Edge 服务器的连接</span><span class="sxs-lookup"><span data-stu-id="9f3ac-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="9f3ac-107">从 Office 通信服务器 2007 R2 Edge 服务器的 "**管理工具**" 组中, 打开 "**计算机管理**" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="9f3ac-108">在控制台树中, 展开 "**服务和应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="9f3ac-109">右键单击 " **Office 通信服务器 2007 R2**", 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="9f3ac-110">单击 "**内部**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="9f3ac-111">在 "**添加服务器**" 下, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="9f3ac-112">在 "**添加 Office 通信服务器**" 对话框中, 输入相应的信息:</span><span class="sxs-lookup"><span data-stu-id="9f3ac-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="9f3ac-113">指定每个 Lync Server 2013 前端服务器或标准版服务器的完全限定的域名 (FQDN), 以及 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="9f3ac-114">如果在通过其 FQDN 指定下一跃点计算机的池中配置了静态路由, 请指定 Lync Server 2013 控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="9f3ac-115">为每个 Lync Server 2013、前端服务器、标准版服务器、池和控制器添加条目后, 单击 "**应用**", 然后单击 **"确定"** 以关闭 "属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="9f3ac-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

