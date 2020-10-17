---
title: 授权与 Office 通信服务器 2007 R2 边缘服务器的连接
description: 授权与 Office 通信服务器 2007 R2 边缘服务器的连接。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8dadb2c476c892f4ffd548ce176d12d3b1a1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545828"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="bfeeb-103">授权与 Office 通信服务器 2007 R2 边缘服务器的连接</span><span class="sxs-lookup"><span data-stu-id="bfeeb-103">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfeeb-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bfeeb-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bfeeb-105">对于您的引导池中的每个 Lync Server 2013 前端服务器或 Standard Edition server，必须更新已授权连接到 Office 通信服务器 2007 R2 边缘服务器的内部服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-105">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="bfeeb-106">如果不进行这些更新，则用户使用旧边缘服务器加入的外部音频/视频 (A/V) 会议将不起作用。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-106">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="bfeeb-107">授权与 Office 通信服务器 2007 R2 边缘服务器的连接</span><span class="sxs-lookup"><span data-stu-id="bfeeb-107">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="bfeeb-108">从 "Office 通信服务器 2007 R2 边缘服务器" 的 " **管理工具** " 组中，打开 " **计算机管理** " 管理单元。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-108">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="bfeeb-109">在控制台树中，展开“服务和应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-109">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="bfeeb-110">右键单击“Office Communications Server 2007 R2”\*\*\*\*，然后单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-110">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="bfeeb-111">单击“内部”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-111">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="bfeeb-112">在“添加服务器”\*\*\*\* 下，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-112">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="bfeeb-113">在“添加 Office Communications Server”\*\*\*\* 对话框中，输入相应信息：</span><span class="sxs-lookup"><span data-stu-id="bfeeb-113">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="bfeeb-114">指定每个 Lync Server 2013 前端服务器或 Standard Edition server 和 Lync Server 2013 池的完全限定的域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-114">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="bfeeb-115">如果已在通过其 FQDN 指定下一跃点计算机的池中配置了静态路由，请指定 Lync Server 2013 控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-115">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="bfeeb-116">为每个 Lync Server 2013、前端服务器、Standard Edition Server、pool 和 Director 添加了一个条目后，单击 " **应用** "，然后单击 **"确定"** 以关闭 "属性" 页。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-116">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

