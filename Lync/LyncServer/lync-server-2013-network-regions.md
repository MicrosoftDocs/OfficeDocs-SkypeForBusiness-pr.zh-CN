---
title: Lync Server 2013：网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd0a41aae0244eb6f0212c6c620d23f1bbf6400
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="f0583-102">Lync Server 2013 中的网络区域</span><span class="sxs-lookup"><span data-stu-id="f0583-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0583-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f0583-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f0583-104">*网络区域* 是在呼叫允许控制、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。</span><span class="sxs-lookup"><span data-stu-id="f0583-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="f0583-105">使用以下过程可查看、创建或修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="f0583-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="f0583-106">例如，如果已为一个语音功能创建网络区域，则不需要创建新的网络区域；其他高级企业语音功能也将使用相同的网络区域。</span><span class="sxs-lookup"><span data-stu-id="f0583-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="f0583-107">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="f0583-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f0583-108">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="f0583-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="f0583-109">有关详细信息，请参阅[在 Lync Server 2013 中配置 CAC 的网络区域](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="f0583-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0583-110">有关网络区域定义的任何特定于功能的要求均编档在相应功能的部署主题中。</span><span class="sxs-lookup"><span data-stu-id="f0583-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0583-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f0583-111">In This Section</span></span>

  - [<span data-ttu-id="f0583-112">在 Lync Server 2013 中查看网络区域信息</span><span class="sxs-lookup"><span data-stu-id="f0583-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="f0583-113">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="f0583-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="f0583-114">在 Lync Server 2013 中删除现有网络区域</span><span class="sxs-lookup"><span data-stu-id="f0583-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="f0583-115">参考</span><span class="sxs-lookup"><span data-stu-id="f0583-115">Reference</span></span>

[<span data-ttu-id="f0583-116">在 Lync Server 2013 中部署高级企业语音功能</span><span class="sxs-lookup"><span data-stu-id="f0583-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

