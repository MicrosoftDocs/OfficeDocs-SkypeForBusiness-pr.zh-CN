---
title: Lync Server 2013：为用户启用 E9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23df1bfce00baece3dce55d74497135863b26759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="5b5e9-102">在 Lync Server 2013 中为用户启用 E9-1-1</span><span class="sxs-lookup"><span data-stu-id="5b5e9-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b5e9-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5b5e9-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5b5e9-104">在客户端注册过程中，Lync Server 使用位置策略为已启用企业语音的用户配置 E9-1-1 属性。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="5b5e9-105">此策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="5b5e9-106">例如，位置策略包含紧急拨号字符串等信息，以及在位置信息服务不自动提供某个位置时是否需要用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="5b5e9-107">有关位置策略的完整定义，请参阅[定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="5b5e9-108">Lync Server 可以基于子网将位置策略分配给客户端，也可以基于全局、每站点或每用户策略将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="5b5e9-109">为帮助确定启用用户的方式，应首先回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="5b5e9-110">**您计划启用所有用户还是限制为对企业的特定地理区域的支持？**</span><span class="sxs-lookup"><span data-stu-id="5b5e9-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="5b5e9-111">可以使用全局位置策略为企业中的所有用户分配位置。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="5b5e9-112">但是，通过将位置策略分配给 Lync Server 网络站点，然后将子网添加到站点中，可以将 E9-1-1 支持限制到企业内的选定位置，并以每个站点为基础指定 E9-1 路由行为。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="5b5e9-113">**您是否计划通过用户策略启用单个用户？**</span><span class="sxs-lookup"><span data-stu-id="5b5e9-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="5b5e9-114">如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="5b5e9-115">**当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="5b5e9-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="5b5e9-116">如果向用户分配了全局、站点或每用户位置策略，则当客户端不在已定义的子网中或位置信息服务未找到任何位置时，可以需要手动将该位置输入到客户端中。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="5b5e9-117">有关详细信息，请参阅在[Lync Server 2013 中定义用于手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5e9-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

