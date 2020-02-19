---
title: Lync Server 2013：配置辅助位置信息服务
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
ms.openlocfilehash: 8255e23a2478329588a3383d8c3999e60d4aea21
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="63a41-102">在 Lync Server 2013 中配置辅助位置信息服务</span><span class="sxs-lookup"><span data-stu-id="63a41-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63a41-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="63a41-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="63a41-104">Lync Server 2013 提供了可用于将位置信息服务指向辅助位置源（SLS）数据库的 web 服务接口。</span><span class="sxs-lookup"><span data-stu-id="63a41-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="63a41-105">连接到 SLS 数据库的 web 服务接口必须符合 Location Information service WSDL。</span><span class="sxs-lookup"><span data-stu-id="63a41-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="63a41-106">如果同时配置了位置数据库和辅助位置数据库，则位置信息服务首先查询位置数据库，如果找不到匹配项，则会将位置请求从客户端发送到 SLS 数据库。</span><span class="sxs-lookup"><span data-stu-id="63a41-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="63a41-107">如果该位置存在于 SLS 中，则位置信息服务随后会将该位置发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="63a41-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="63a41-108">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="63a41-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="63a41-109">**CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="63a41-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="63a41-110">配置辅助位置数据库</span><span class="sxs-lookup"><span data-stu-id="63a41-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="63a41-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63a41-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="63a41-112">运行以下 cmdlet 为辅助位置数据库位置配置 URL。</span><span class="sxs-lookup"><span data-stu-id="63a41-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

