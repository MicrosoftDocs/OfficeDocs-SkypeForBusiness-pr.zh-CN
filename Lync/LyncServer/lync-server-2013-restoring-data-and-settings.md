---
title: Lync Server 2013：还原数据和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b8575ee1362b240df0bfc0a1a1a6b27afde268
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="4cd4f-102">在 Lync Server 2013 中还原数据和设置</span><span class="sxs-lookup"><span data-stu-id="4cd4f-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cd4f-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4cd4f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4cd4f-104">如果已通过配对池实施了灾难恢复拓扑，并且其中一个前端池已关闭，需要快速将服务还原到用户，请参阅[在 Lync Server 2013 中通过池进行故障转移](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd4f-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="4cd4f-105">否则，请使用以下主题中的信息以及[Lync server 2013 备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中的工作表，以便在发生故障或中断后还原 Lync server。</span><span class="sxs-lookup"><span data-stu-id="4cd4f-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4cd4f-106">若要减少停机时间和潜在的数据丢失，请仅在故障排除过程不能有效确定和更正问题时执行本文档中所述的还原过程。</span><span class="sxs-lookup"><span data-stu-id="4cd4f-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="4cd4f-107">在故障排除过程中，在关闭并重新启动服务器时，请尽量减少对其他服务器和组件的影响。</span><span class="sxs-lookup"><span data-stu-id="4cd4f-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4cd4f-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4cd4f-108">In This Section</span></span>

  - [<span data-ttu-id="4cd4f-109">准备还原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cd4f-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="4cd4f-110">在 Lync Server 2013 中还原 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="4cd4f-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="4cd4f-111">在 Lync Server 2013 中还原承载中央管理存储的服务器</span><span class="sxs-lookup"><span data-stu-id="4cd4f-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="4cd4f-112">在 Lync Server 2013 中还原企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="4cd4f-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="4cd4f-113">在 Lync Server 2013 中还原企业版成员服务器</span><span class="sxs-lookup"><span data-stu-id="4cd4f-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="4cd4f-114">在 Lync Server 2013 中还原 Lync Server 池</span><span class="sxs-lookup"><span data-stu-id="4cd4f-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="4cd4f-115">在 Lync Server 2013 中执行 ABC 前端池故障转移</span><span class="sxs-lookup"><span data-stu-id="4cd4f-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="4cd4f-116">在 Lync Server 2013 中还原文件存储</span><span class="sxs-lookup"><span data-stu-id="4cd4f-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="4cd4f-117">在 Lync Server 2013 中还原监视或存档数据</span><span class="sxs-lookup"><span data-stu-id="4cd4f-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="4cd4f-118">在 Lync Server 2013 中还原持久聊天数据</span><span class="sxs-lookup"><span data-stu-id="4cd4f-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

