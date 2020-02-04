---
title: Lync Server 2013：使用 Cmdlet 反向执行林准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="0d130-102">针对 Lync Server 2013 使用 Cmdlet 反向执行林准备</span><span class="sxs-lookup"><span data-stu-id="0d130-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d130-103">_**主题上次修改时间：** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="0d130-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="0d130-104">使用**CsAdForest** cmdlet 可撤消林准备步骤。</span><span class="sxs-lookup"><span data-stu-id="0d130-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0d130-105">如果你在还安装了早期版本的 Lync Server 的环境中运行<STRONG>CsAdForest</STRONG> cmdlet，则以前版本的全局设置也将被删除。</span><span class="sxs-lookup"><span data-stu-id="0d130-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="0d130-106">使用 cmdlet 执行反向林准备</span><span class="sxs-lookup"><span data-stu-id="0d130-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="0d130-107">以林根域中的 "域管理员" 组的成员身份登录加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d130-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="0d130-108">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="0d130-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0d130-109">运行：</span><span class="sxs-lookup"><span data-stu-id="0d130-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="0d130-110">例如：</span><span class="sxs-lookup"><span data-stu-id="0d130-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="0d130-111">Force 参数指定是否强制运行任务。</span><span class="sxs-lookup"><span data-stu-id="0d130-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="0d130-112">如果此参数不存在，并且即使林中的一个域仍为 Lync Server 2013 准备好，该命令也不会运行。</span><span class="sxs-lookup"><span data-stu-id="0d130-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="0d130-113">如果指定了 Force 参数，则无论林中其他域的状态如何，操作都将继续。</span><span class="sxs-lookup"><span data-stu-id="0d130-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="0d130-114">如果不指定 GroupDomain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="0d130-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d130-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d130-115">See Also</span></span>


[<span data-ttu-id="0d130-116">为 Lync Server 2013 运行林准备</span><span class="sxs-lookup"><span data-stu-id="0d130-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="0d130-117">为 Lync Server 2013 准备林</span><span class="sxs-lookup"><span data-stu-id="0d130-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

