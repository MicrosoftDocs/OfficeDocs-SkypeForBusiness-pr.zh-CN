---
title: Lync Server 2013：配置 SNMP 应用程序
description: Lync Server 2013：配置 SNMP 应用程序。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546698"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="40eb8-103">在 Lync Server 2013 中配置 SNMP 应用程序</span><span class="sxs-lookup"><span data-stu-id="40eb8-103">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40eb8-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="40eb8-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="40eb8-105">Lync Server 2013 包含一个标准的 web 服务接口，可用于将 Location 信息服务连接到简单网络管理协议 (SNMP) 应用程序，这些应用程序将 MAC 地址与端口和交换机信息相匹配。</span><span class="sxs-lookup"><span data-stu-id="40eb8-105">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="40eb8-106">如果安装了 SNMP 应用程序，并且 Location 信息服务未能在 location 数据库中找到匹配项，则位置信息服务将使用客户端提供的 MAC 地址自动查询应用程序。</span><span class="sxs-lookup"><span data-stu-id="40eb8-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="40eb8-107">然后，位置信息服务使用 SNMP 应用程序返回的端口和交换机信息再次查询位置数据库。</span><span class="sxs-lookup"><span data-stu-id="40eb8-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="40eb8-108">有关详细信息，请参阅 [CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="40eb8-108">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40eb8-109">MAC 地址在运行 Windows 8 的计算机上不可用。</span><span class="sxs-lookup"><span data-stu-id="40eb8-109">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="40eb8-110">配置 SNMP 应用程序 URL</span><span class="sxs-lookup"><span data-stu-id="40eb8-110">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="40eb8-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="40eb8-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="40eb8-112">运行以下 cmdlet 为 SNMP 应用程序配置 URL。</span><span class="sxs-lookup"><span data-stu-id="40eb8-112">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

