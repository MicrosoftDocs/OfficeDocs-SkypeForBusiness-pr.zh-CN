---
title: Lync Server 2013：配置辅助位置信息服务
description: Lync Server 2013：配置辅助位置信息服务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1721299a0c70535dff8dd05e31712ee6a8d93691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551707"
---
# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="ed3bc-103">在 Lync Server 2013 中配置辅助位置信息服务</span><span class="sxs-lookup"><span data-stu-id="ed3bc-103">Configure a secondary Location Information service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed3bc-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ed3bc-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ed3bc-105">Lync Server 2013 提供了一个 web 服务接口，可用于将 Location 信息服务指向辅助位置源 (SLS) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-105">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="ed3bc-106">连接到 SLS 数据库的 web 服务接口必须符合 Location Information service WSDL。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="ed3bc-107">如果同时配置了位置数据库和辅助位置数据库，则位置信息服务首先查询位置数据库，如果找不到匹配项，则会将位置请求从客户端发送到 SLS 数据库。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="ed3bc-108">如果该位置存在于 SLS 中，则位置信息服务随后会将该位置发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="ed3bc-109">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed3bc-109">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="ed3bc-110">**CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ed3bc-110">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="ed3bc-111">配置辅助位置数据库</span><span class="sxs-lookup"><span data-stu-id="ed3bc-111">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="ed3bc-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed3bc-113">运行以下 cmdlet 为辅助位置数据库位置配置 URL。</span><span class="sxs-lookup"><span data-stu-id="ed3bc-113">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

