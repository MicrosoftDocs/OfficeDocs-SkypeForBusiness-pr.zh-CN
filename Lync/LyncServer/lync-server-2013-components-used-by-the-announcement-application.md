---
title: Lync Server 2013：通知应用程序使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="3eb7f-102">Lync Server 2013 中的通知应用程序使用的组件</span><span class="sxs-lookup"><span data-stu-id="3eb7f-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb7f-103">_**主题上次修改时间:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="3eb7f-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="3eb7f-104">在 Lync Server 2013 中, 公告应用程序是响应组应用程序的一个组件。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="3eb7f-105">部署企业语音时, 将自动安装通知应用程序并与响应组应用程序一起激活。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="3eb7f-106">本部分介绍支持公告应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="3eb7f-107">公告应用程序组件</span><span class="sxs-lookup"><span data-stu-id="3eb7f-107">Announcement Application Components</span></span>

<span data-ttu-id="3eb7f-108">以下 Lync Server 组件支持公告应用程序:</span><span class="sxs-lookup"><span data-stu-id="3eb7f-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="3eb7f-109">**应用程序服务**   应用程序服务提供用于部署、托管和管理统一通信应用程序的平台。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="3eb7f-110">应用程序服务将自动安装在前端池和每个标准版服务器上的每个前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="3eb7f-111">**响应组应用**   程序响应组应用程序是由应用程序服务托管的统一通信应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="3eb7f-112">如果将未分配的电话号码范围配置为路由到公告, 则需要响应组应用程序来路由对电话号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="3eb7f-113">(如果所有范围都配置为路由到 Exchange 统一消息 (UM), 则不需要响应组应用程序。)</span><span class="sxs-lookup"><span data-stu-id="3eb7f-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="3eb7f-114">**音频文件**   音频文件用于公告。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="3eb7f-115">**文件存储**   : 公告应用程序使用文件存储来存储其音频文件。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="3eb7f-116">**Lync server 控制面板**   您可以使用 lync server "控制面板" 配置 "未分配的号码" 表。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="3eb7f-117">**Lync server 管理外壳**   程序您可以使用 lync server management shell cmdlet 配置公告设置和 "未分配的号码" 表。</span><span class="sxs-lookup"><span data-stu-id="3eb7f-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

