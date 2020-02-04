---
title: 为 Lync Server 2013 准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server 2013
ms:assetid: d0978eb6-d842-40e9-b475-73197cc34e08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205265(v=OCS.15)
ms:contentKeyID: 48185413
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6bedd4e0d008f448da97ad5fc5bf62d810cfedc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server-2013"></a><span data-ttu-id="e859e-102">为 Lync Server 2013 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="e859e-102">Prepare Active Directory for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e859e-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e859e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e859e-104">在使用 Office 通信服务器 2007 R2 在共存状态中部署 Lync Server 2013 之前，必须执行一些其他 Active Directory 任务，以便为 Lync Server 2013 配置架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="e859e-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="e859e-105">架构扩展添加 Lync Server 所需的 Active Directory 类和属性。</span><span class="sxs-lookup"><span data-stu-id="e859e-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span> <span data-ttu-id="e859e-106">有关其他信息，请参阅[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)主题。</span><span class="sxs-lookup"><span data-stu-id="e859e-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="e859e-107">**为 Lync Server 2013 准备 Active Directory**</span><span class="sxs-lookup"><span data-stu-id="e859e-107">**Prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="e859e-108">在 Lync Server 2013 前端服务器上，运行 Lync Server 2013 安装程序。</span><span class="sxs-lookup"><span data-stu-id="e859e-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="e859e-109">选择 "**准备 Active Directory** "</span><span class="sxs-lookup"><span data-stu-id="e859e-109">Select **Prepare Active Directory**</span></span>
    
    <span data-ttu-id="e859e-110">![Lync Server 2013 部署向导，"欢迎" 页面](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 部署向导，"欢迎" 页面")</span><span class="sxs-lookup"><span data-stu-id="e859e-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="e859e-111">完成步骤1至步骤5。</span><span class="sxs-lookup"><span data-stu-id="e859e-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="e859e-112">![部署向导的 Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "部署向导的 Active Directory Prearation")</span><span class="sxs-lookup"><span data-stu-id="e859e-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

