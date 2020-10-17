---
title: Lync Server 2013：指定可用于登录 Lync Server 2013 的客户端应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd82012bfd09f6f0f40215a179a33c2f2f16337a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519539"
---
# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="836b5-102">指定可用于登录 Lync Server 2013 的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="836b5-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="836b5-103">_**上次修改的主题：** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="836b5-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="836b5-104">Lync Server 2013 使您能够指定在您的环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="836b5-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="836b5-105">使用客户端版本策略可帮助降低与支持多个客户端版本相关的成本。</span><span class="sxs-lookup"><span data-stu-id="836b5-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="836b5-106">它还可以改进总体用户体验，因为在更早和更高版本的客户端进行交互时，可通过早期版本的客户端来限制可用功能。</span><span class="sxs-lookup"><span data-stu-id="836b5-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="836b5-107">客户端版本控制有三个组件：</span><span class="sxs-lookup"><span data-stu-id="836b5-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="836b5-108">客户端版本配置设置用于为全局或对特定网站启用或禁用客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="836b5-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="836b5-109">客户端版本策略用于全局或特定网站、池或用户组分配一组规则。</span><span class="sxs-lookup"><span data-stu-id="836b5-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="836b5-110">客户端版本策略规则构成了一个客户端版本策略，用于定义当用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="836b5-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="836b5-111">由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="836b5-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="836b5-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="836b5-112">In This Section</span></span>

  - [<span data-ttu-id="836b5-113">Lync Server 2013 中的客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="836b5-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="836b5-114">Lync Server 2013 中的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="836b5-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="836b5-115">Lync Server 2013 中的客户端版本规则</span><span class="sxs-lookup"><span data-stu-id="836b5-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="836b5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="836b5-116">See Also</span></span>


[<span data-ttu-id="836b5-117">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="836b5-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

