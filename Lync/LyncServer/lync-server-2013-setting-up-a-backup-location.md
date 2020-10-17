---
title: Lync Server 2013：设置备份位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ee86d2cf3d68b65c03e851980b21fb0293c5362
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509739"
---
# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="36019-102">为 Lync Server 2013 设置备份位置</span><span class="sxs-lookup"><span data-stu-id="36019-102">Setting up a backup location for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36019-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="36019-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="36019-104">在首次备份 Lync Server 之前，请设置所需的硬件和软件，以便存储和维护备份。</span><span class="sxs-lookup"><span data-stu-id="36019-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="36019-105">您需要根据需要获取媒体和内容的访问权，并在要备份的每个服务器和备份媒体之间提供网络连接。</span><span class="sxs-lookup"><span data-stu-id="36019-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="36019-106">应在备份和还原策略中定义您使用的媒体和位置。</span><span class="sxs-lookup"><span data-stu-id="36019-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="36019-107">您用于常规备份的位置可以是本地的，也可以是远程的，但必须是安全的，并且在备份和还原时必须可访问。</span><span class="sxs-lookup"><span data-stu-id="36019-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="36019-108">我们建议使用远程位置来防范主站点的灾难性事件。</span><span class="sxs-lookup"><span data-stu-id="36019-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="36019-109">在设置并测试单个组件后，验证从每个服务器备份的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="36019-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

