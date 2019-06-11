---
title: 'Lync Server 2013: 发布位置数据库'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="f793d-102">从 Lync Server 2013 发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="f793d-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f793d-103">_**主题上次修改时间:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="f793d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="f793d-104">只有在添加到位置数据库的新位置发布后，客户端才能使用这些位置。</span><span class="sxs-lookup"><span data-stu-id="f793d-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="f793d-105">有关详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:</span><span class="sxs-lookup"><span data-stu-id="f793d-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="f793d-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f793d-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="f793d-107">如果使用紧急位置标识号 (ELIN) 网关，还需要将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="f793d-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="f793d-108">PSTN 运营商可能需要特定格式的 ELIN 记录。</span><span class="sxs-lookup"><span data-stu-id="f793d-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="f793d-109">请联系 PSTN 运营商了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f793d-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="f793d-110">你可以从位置信息服务数据库导出记录, 并根据需要设置其格式。</span><span class="sxs-lookup"><span data-stu-id="f793d-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="f793d-111">发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="f793d-111">To publish the location database</span></span>

  - <span data-ttu-id="f793d-112">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f793d-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="f793d-113">运行以下 cmdlet 发布位置数据库。</span><span class="sxs-lookup"><span data-stu-id="f793d-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

