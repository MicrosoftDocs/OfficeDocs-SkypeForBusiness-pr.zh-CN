---
title: 'Lync Server 2013: 配置位置数据库'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="be4e2-102">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be4e2-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be4e2-103">_**主题上次修改时间:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="be4e2-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="be4e2-104">为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。</span><span class="sxs-lookup"><span data-stu-id="be4e2-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="be4e2-105">如果未配置位置数据库, 并且位置策略中**需要的位置**设置为 **"是" 或 "** **免责声明**", 系统将提示用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="be4e2-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="be4e2-106">若要配置位置数据库, 您将执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="be4e2-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="be4e2-107">使用网络元素到位置的映射填充数据库。</span><span class="sxs-lookup"><span data-stu-id="be4e2-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="be4e2-108">如果您使用紧急位置识别号码 (ELIN) 网关, 则需要在 " \<公司名称\> " 字段中包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="be4e2-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="be4e2-109">根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。</span><span class="sxs-lookup"><span data-stu-id="be4e2-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="be4e2-110">发布更新的数据库。</span><span class="sxs-lookup"><span data-stu-id="be4e2-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be4e2-111">或者, 你可以定义可用于放置位置数据库的辅助位置源数据库。</span><span class="sxs-lookup"><span data-stu-id="be4e2-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="be4e2-112">有关详细信息, 请参阅<A href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中配置辅助位置信息服务</A>。</span><span class="sxs-lookup"><span data-stu-id="be4e2-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be4e2-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="be4e2-113">In This Section</span></span>

  - [<span data-ttu-id="be4e2-114">在 Lync Server 2013 中填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="be4e2-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="be4e2-115">在 Lync Server 2013 中验证地址</span><span class="sxs-lookup"><span data-stu-id="be4e2-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="be4e2-116">从 Lync Server 2013 发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="be4e2-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

