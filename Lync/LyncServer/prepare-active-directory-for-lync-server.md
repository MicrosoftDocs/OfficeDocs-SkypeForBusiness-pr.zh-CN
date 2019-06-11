---
title: 为 Lync Server 准备 Active Directory
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ff5be6fbf3849c51979f3cf94dbc36d14e5b282
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="f9518-102">为 Lync Server 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="f9518-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9518-103">_**主题上次修改时间:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f9518-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f9518-104">在使用 Lync Server 2010 在共存状态中部署 Lync Server 2013 之前, 必须执行一些其他 Active Directory 任务, 以便为 Lync Server 2013 配置架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="f9518-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="f9518-105">架构扩展添加 Lync Server 2013 所需的 Active Directory 类和属性。</span><span class="sxs-lookup"><span data-stu-id="f9518-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="f9518-106">有关其他信息, 请参阅[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)主题。</span><span class="sxs-lookup"><span data-stu-id="f9518-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="f9518-107">**准备 Lync Server 2013 的 Active Directory**</span><span class="sxs-lookup"><span data-stu-id="f9518-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="f9518-108">在 Lync Server 2013 前端服务器上, 运行 Lync Server 2013 安装程序。</span><span class="sxs-lookup"><span data-stu-id="f9518-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="f9518-109">选择 "**准备 Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="f9518-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="f9518-110">![Lync Server 2013 部署向导, "欢迎" 页面](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 部署向导, \"欢迎\" 页面")</span><span class="sxs-lookup"><span data-stu-id="f9518-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="f9518-111">完成步骤1至步骤5。</span><span class="sxs-lookup"><span data-stu-id="f9518-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="f9518-112">![部署向导的 Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "部署向导的 Active Directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="f9518-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

