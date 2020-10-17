---
title: 导出拓扑并将其复制到外部媒体以进行边缘安装
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dd461e6a8ce184e5e418feddede258af68d2c25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528369"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="725c3-102">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</span><span class="sxs-lookup"><span data-stu-id="725c3-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="725c3-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="725c3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="725c3-104">发布拓扑后，Lync Server 部署向导需要访问中央管理存储数据，以便在服务器上启动部署过程。</span><span class="sxs-lookup"><span data-stu-id="725c3-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="725c3-105">在内部网络中，数据可直接来自服务器，但不在内部域中的边缘服务器将无法访问数据。</span><span class="sxs-lookup"><span data-stu-id="725c3-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="725c3-106">若要使拓扑配置数据可用于边缘服务器部署，必须将拓扑数据导出到一个文件，并将其复制到外部媒体 (例如，在边缘服务器上运行 Lync Server 部署向导之前，在边缘服务器上提供的 USB 驱动器或网络共享) 。</span><span class="sxs-lookup"><span data-stu-id="725c3-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="725c3-107">使用以下过程可使拓扑配置数据在要部署的边缘服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="725c3-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="725c3-108">在边缘服务器上安装 Lync Server 2013 之后，可以使用内部网络中的管理工具管理边缘服务器，这会自动将配置复制到部署中的任何边缘服务器上。</span><span class="sxs-lookup"><span data-stu-id="725c3-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="725c3-109">唯一的例外是分配并安装证书，并停止和启动服务，这两种情况都必须在边缘服务器上完成。</span><span class="sxs-lookup"><span data-stu-id="725c3-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="725c3-110">使用 Lync Server 命令行管理程序使拓扑数据在边缘服务器上可用</span><span class="sxs-lookup"><span data-stu-id="725c3-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="725c3-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="725c3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="725c3-112">在 Lync Server 命令行管理程序中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="725c3-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="725c3-113">将导出的文件复制到外部媒体 (例如，在部署) 期间，从边缘服务器获取的 USB 驱动器或网络共享。</span><span class="sxs-lookup"><span data-stu-id="725c3-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

