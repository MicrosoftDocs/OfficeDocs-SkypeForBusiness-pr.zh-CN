---
title: Lync Server 2013：发布位置数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512369"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="ea1ef-102">从 Lync Server 2013 发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="ea1ef-102">Publish the location database from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea1ef-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ea1ef-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ea1ef-104">在发布之前，您添加到位置数据库的新位置将不会对客户端可用。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="ea1ef-105">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea1ef-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="ea1ef-106">**发布-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ea1ef-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="ea1ef-107">如果使用的是紧急位置标识号 (ELIN) 网关，则还需要将 Elin 上载到公共交换电话网络 (PSTN) 运营商的自动位置标识 (阿里) database。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="ea1ef-108">您的 PSTN 运营商可能要求您对 ELIN 记录使用特定的格式。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="ea1ef-109">有关详细信息，请与 PSTN 运营商联系。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="ea1ef-110">您可以从位置信息服务数据库中导出记录，并根据需要对其进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="ea1ef-111">发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="ea1ef-111">To publish the location database</span></span>

  - <span data-ttu-id="ea1ef-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="ea1ef-113">运行以下 cmdlet 以发布位置数据库。</span><span class="sxs-lookup"><span data-stu-id="ea1ef-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

