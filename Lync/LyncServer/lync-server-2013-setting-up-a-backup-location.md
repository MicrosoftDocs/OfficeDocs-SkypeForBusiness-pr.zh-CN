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
ms.openlocfilehash: 723bcbc2aeaae5264645d824a9b10a939b6770ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="03d78-102">为 Lync Server 2013 设置备份位置</span><span class="sxs-lookup"><span data-stu-id="03d78-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03d78-103">_**主题上次修改时间：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="03d78-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="03d78-104">在执行 Lync Server 的首次备份之前，请设置所需的硬件和软件，以便存储和维护备份。</span><span class="sxs-lookup"><span data-stu-id="03d78-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="03d78-105">你需要根据需要获取对媒体和内容的访问权限，并提供要备份的每台服务器与备份媒体之间的网络连接。</span><span class="sxs-lookup"><span data-stu-id="03d78-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="03d78-106">你使用的媒体和位置应在你的备份和还原策略中定义。</span><span class="sxs-lookup"><span data-stu-id="03d78-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="03d78-107">用于常规备份的位置可以是本地还是远程，但它必须是安全的，并且在备份和还原时必须可访问。</span><span class="sxs-lookup"><span data-stu-id="03d78-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="03d78-108">我们建议使用远程位置来防止主站点发生灾难性事件。</span><span class="sxs-lookup"><span data-stu-id="03d78-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="03d78-109">设置并测试单个组件后，请验证每台服务器中的备份的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="03d78-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

