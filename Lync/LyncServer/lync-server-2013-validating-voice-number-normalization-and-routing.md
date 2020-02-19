---
title: Lync Server 2013：验证语音号码规范化和路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92809d018bf8b69e6bc3fd5cc640c40836249de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="58f5b-102">在 Lync Server 2013 中验证语音号码规范化和路由</span><span class="sxs-lookup"><span data-stu-id="58f5b-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58f5b-103">_**上次修改的主题：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="58f5b-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="58f5b-104">正确的数字规范化和路由对于功能企业语音环境来说非常重要。</span><span class="sxs-lookup"><span data-stu-id="58f5b-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="58f5b-105">尤其是在从专用交换机（PBX）迁移到独立的 Lync Server 环境时，成功迁移的关键之一就是显示并记录所有现有的拨号规则，并创建适当的规范化规则、语音策略电话使用情况和路由。</span><span class="sxs-lookup"><span data-stu-id="58f5b-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="58f5b-106">验证号码规范化和路由不仅是在迁移过程中很重要，而且在正常的系统稳定操作过程中也很重要。</span><span class="sxs-lookup"><span data-stu-id="58f5b-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="58f5b-107">我们建议您使用 Lync Server 控制面板每天执行此验证，从针对在 Lync Server 全局设置中发布的当前规范化规则集开发一组强大的测试事例开始。</span><span class="sxs-lookup"><span data-stu-id="58f5b-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="58f5b-108">应每天运行这些测试用例，以突出显示已完成并提交到拨号计划的任何不需要的更改。</span><span class="sxs-lookup"><span data-stu-id="58f5b-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="58f5b-109">Lync Server 控制面板还可帮助您可视化、测试、更改、存档和共享有关语音路由和更改企业语音号码规范化规则、拨号计划、语音策略和路由的配置信息。</span><span class="sxs-lookup"><span data-stu-id="58f5b-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="58f5b-110">它具有用于执行以下操作的附加功能：</span><span class="sxs-lookup"><span data-stu-id="58f5b-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="58f5b-111">导出和导入或备份系统之间的语音路由数据。</span><span class="sxs-lookup"><span data-stu-id="58f5b-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="58f5b-112">在将配置更改上载到实时系统之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="58f5b-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="58f5b-113">创建和运行配置测试用例，以帮助确保在对已部署的系统进行更改之后，路由数据的可用性。</span><span class="sxs-lookup"><span data-stu-id="58f5b-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="58f5b-114">创建和更改编号规范化规则、位置配置文件、语音策略和路由数据，而无需编写所需的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="58f5b-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="58f5b-115">分析位置配置文件以实现与 Lync Server Phone Edition 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="58f5b-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="58f5b-116">有关语音路由测试的详细信息，可参阅[Lync Server 2013 中的测试语音路由](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="58f5b-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="58f5b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58f5b-117">See Also</span></span>


[<span data-ttu-id="58f5b-118">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="58f5b-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

