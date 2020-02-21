---
title: Lync Server 2013：检查磁盘使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cb167d2a7aed3f5c107d4beba568c00ac501e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="d32f9-102">在 Lync Server 2013 中检查磁盘使用率</span><span class="sxs-lookup"><span data-stu-id="d32f9-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d32f9-103">_**上次修改的主题：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="d32f9-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="d32f9-104">硬盘是 Lync Server 2013 部署的重要组件。</span><span class="sxs-lookup"><span data-stu-id="d32f9-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="d32f9-105">如果没有足够的可用磁盘卷，操作系统和 Lync Server 2013 数据库都不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="d32f9-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="d32f9-106">您必须每天监视 Lync Server 2013 后端数据库统计信息，以帮助确保服务器不会用尽磁盘空间，并准备好根据需要添加存储资源。</span><span class="sxs-lookup"><span data-stu-id="d32f9-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="d32f9-107">除了检查承载操作系统、程序文件、数据库和事务日志的磁盘空间（Lync Server 2013 后端）之外，还应监视文件系统的使用情况，其中包括包含以下重要项的文件共享的磁盘空间数据</span><span class="sxs-lookup"><span data-stu-id="d32f9-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="d32f9-108">会议内容</span><span class="sxs-lookup"><span data-stu-id="d32f9-108">Meeting content</span></span>

  - <span data-ttu-id="d32f9-109">会议内容元数据</span><span class="sxs-lookup"><span data-stu-id="d32f9-109">Meeting content metadata</span></span>

  - <span data-ttu-id="d32f9-110">会议合规性日志</span><span class="sxs-lookup"><span data-stu-id="d32f9-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="d32f9-111">应用程序数据文件（由应用程序服务器组件在内部使用）</span><span class="sxs-lookup"><span data-stu-id="d32f9-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="d32f9-112">组聊天服务器 web 服务和合规性文件夹（用于存储上载到组聊天 web 服务的文件）</span><span class="sxs-lookup"><span data-stu-id="d32f9-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="d32f9-113">Group Chat 合规性 XML 文件（包含组聊天合规性记录）</span><span class="sxs-lookup"><span data-stu-id="d32f9-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="d32f9-114">更新文件（适用于设备更新服务）</span><span class="sxs-lookup"><span data-stu-id="d32f9-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="d32f9-115">通讯簿文件</span><span class="sxs-lookup"><span data-stu-id="d32f9-115">Address Book files</span></span>

<span data-ttu-id="d32f9-116">Lync Server 2013 需要硬盘空间来存储其数据库和事务日志，以及以前列出的文件共享上的文件。</span><span class="sxs-lookup"><span data-stu-id="d32f9-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="d32f9-117">应定期监视磁盘空间，以帮助确保由于存储资源不足，Lync Server 2013 部署不会产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="d32f9-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="d32f9-118">比较并维护每个 Lync Server 2013 卷上的可用磁盘空间的统计信息，以及数据库和事务日志文件的预期增长。</span><span class="sxs-lookup"><span data-stu-id="d32f9-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="d32f9-119">这有助于在存储资源需要时进行容量规划和添加存储。</span><span class="sxs-lookup"><span data-stu-id="d32f9-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="d32f9-120">为了适应故障排除和灾难恢复情况，我们建议可用的可用卷空间等于或大于数据库大小的110%。</span><span class="sxs-lookup"><span data-stu-id="d32f9-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="d32f9-121">您可以使用以下方法检查可用磁盘空间：</span><span class="sxs-lookup"><span data-stu-id="d32f9-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="d32f9-122">\*\*\*\*   当卷空间受到限制时，可以使用 system center operations manager system center operations manager 向管理员发出警告。</span><span class="sxs-lookup"><span data-stu-id="d32f9-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="d32f9-123">\*\*\*\*   如果可用硬盘空间低于20%，则运行脚本以运行脚本来监视磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="d32f9-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="d32f9-124">你可以在 TechNet 上的 Microsoft 脚本中心找到一个示例脚本，请检查以下内容：[https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="d32f9-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="d32f9-125">**Windows 资源管理器**   使用 windows 资源管理器检查存储 Lync Server 2013 日志和数据库的卷上的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="d32f9-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

