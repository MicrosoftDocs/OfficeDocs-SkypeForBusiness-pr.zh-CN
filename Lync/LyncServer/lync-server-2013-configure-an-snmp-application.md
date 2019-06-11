---
title: 'Lync Server 2013: 配置 SNMP 应用程序'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15a911abc614ff30c4130fb2a35886458fcb1dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="92589-102">在 Lync Server 2013 中配置 SNMP 应用程序</span><span class="sxs-lookup"><span data-stu-id="92589-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92589-103">_**主题上次修改时间:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="92589-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="92589-104">Lync Server 2013 包含一个标准的 web 服务接口, 可用于将 Location 信息服务连接到与端口和交换机信息相匹配的 MAC 地址的简单网络管理协议 (SNMP) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="92589-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="92589-105">如果已安装 SNMP 应用程序, 并且位置信息服务无法在位置数据库中找到匹配项, 则位置信息服务将使用客户端提供的 MAC 地址自动查询应用程序。</span><span class="sxs-lookup"><span data-stu-id="92589-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="92589-106">然后, 位置信息服务使用 SNMP 应用程序返回的端口和交换信息再次查询位置数据库。</span><span class="sxs-lookup"><span data-stu-id="92589-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="92589-107">有关详细信息, 请参阅[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="92589-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92589-108">MAC 地址在运行 Windows 8 的计算机上不可用。</span><span class="sxs-lookup"><span data-stu-id="92589-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="92589-109">配置 SNMP 应用程序 URL</span><span class="sxs-lookup"><span data-stu-id="92589-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="92589-110">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="92589-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="92589-111">运行以下 cmdlet 为 SNMP 应用程序配置 URL。</span><span class="sxs-lookup"><span data-stu-id="92589-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

