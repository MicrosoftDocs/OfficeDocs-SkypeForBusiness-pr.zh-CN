---
title: Lync Server 2013：部署存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d31a4bdf75b649dec1d18a834335b0d47a69a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="ef099-102">在 Lync Server 2013 中部署存档</span><span class="sxs-lookup"><span data-stu-id="ef099-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef099-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ef099-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ef099-104">Lync Server 2013 提供了用于在 Lync Server 中存档即时消息（IM）内容和会议通信的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ef099-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="ef099-105">您可以通过将存档存储与 Exchange 2013 存储集成，使用 SQL Server 数据库存储 Lync Server 2013 存档数据，或者同时使用 Lync Server 2013 和 Exchange 2013 存储来实现存档支持。</span><span class="sxs-lookup"><span data-stu-id="ef099-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="ef099-106">您可以使用策略和存档配置来控制数据的存档方式。</span><span class="sxs-lookup"><span data-stu-id="ef099-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="ef099-107">有关详细信息，请参阅规划文档、部署文档或操作文档中的规划文档中的在[lync server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)和[存档在 lync server 2013 中的工作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="ef099-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="ef099-108">可以使用本节中的信息初步设置和配置存档。</span><span class="sxs-lookup"><span data-stu-id="ef099-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="ef099-109">部署后可以更改存档设置。</span><span class="sxs-lookup"><span data-stu-id="ef099-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="ef099-110">若要详细了解如何实现对日常管理的存档支持或满足组织中的新要求，请参阅操作文档中的[管理 Lync Server 2013 存档](lync-server-2013-managing-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="ef099-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef099-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ef099-111">In This Section</span></span>

  - [<span data-ttu-id="ef099-112">Lync Server 2013 中的存档工作原理</span><span class="sxs-lookup"><span data-stu-id="ef099-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="ef099-113">Lync Server 2013 中存档的部署清单</span><span class="sxs-lookup"><span data-stu-id="ef099-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="ef099-114">在 Lync Server 2013 中设置用于存档的系统和基础结构</span><span class="sxs-lookup"><span data-stu-id="ef099-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="ef099-115">将存档数据库添加到现有 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="ef099-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="ef099-116">在 Lync Server 2013 中配置对存档的支持</span><span class="sxs-lookup"><span data-stu-id="ef099-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

