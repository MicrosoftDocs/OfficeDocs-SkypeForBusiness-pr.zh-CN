---
title: Lync Server 2013：配置位置数据库
description: Lync Server 2013：配置位置数据库。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877c83976ca0db9abc3a9e57d4a1cf5adaa1291a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544928"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="d6191-103">在 Lync Server 2013 中配置位置数据库</span><span class="sxs-lookup"><span data-stu-id="d6191-103">Configure the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6191-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="d6191-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="d6191-p101">为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。如果不配置位置数据库，且位置策略中的“所需位置”\*\*\*\* 设置为“是”\*\*\*\* 或“免责声明”\*\*\*\*，则会提示用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="d6191-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="d6191-107">要配置位置数据库，请执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="d6191-107">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="d6191-108">使用网络元素到位置的映射填充数据库。</span><span class="sxs-lookup"><span data-stu-id="d6191-108">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="d6191-109">如果使用的是紧急位置标识号 (ELIN) 网关，则需要在字段中包括 ELIN \<CompanyName\> 。</span><span class="sxs-lookup"><span data-stu-id="d6191-109">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="d6191-110">根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。</span><span class="sxs-lookup"><span data-stu-id="d6191-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="d6191-111">发布更新的数据库。</span><span class="sxs-lookup"><span data-stu-id="d6191-111">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6191-112">另外，可以定义可用于代替位置数据库的辅助位置源数据库。</span><span class="sxs-lookup"><span data-stu-id="d6191-112">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="d6191-113">有关详细信息，请参阅 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中配置辅助位置信息服务</A>。</span><span class="sxs-lookup"><span data-stu-id="d6191-113">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6191-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d6191-114">In This Section</span></span>

  - [<span data-ttu-id="d6191-115">在 Lync Server 2013 中填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="d6191-115">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="d6191-116">在 Lync Server 2013 中验证地址</span><span class="sxs-lookup"><span data-stu-id="d6191-116">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="d6191-117">从 Lync Server 2013 发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="d6191-117">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

