---
title: Lync Server 2013：通知应用程序使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517709"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="66f73-102">Lync Server 2013 中通知应用程序使用的组件</span><span class="sxs-lookup"><span data-stu-id="66f73-102">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66f73-103">_**上次修改的主题：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="66f73-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="66f73-104">在 Lync Server 2013 中，通知应用程序是响应组应用程序的一个组件。</span><span class="sxs-lookup"><span data-stu-id="66f73-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="66f73-105">部署企业语音时，会自动安装并激活通知应用程序和响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="66f73-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="66f73-106">本节介绍支持通知应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="66f73-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="66f73-107">通知应用程序组件</span><span class="sxs-lookup"><span data-stu-id="66f73-107">Announcement Application Components</span></span>

<span data-ttu-id="66f73-108">以下 Lync Server 组件支持通知应用程序：</span><span class="sxs-lookup"><span data-stu-id="66f73-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="66f73-109">**应用程序服务**    应用程序服务提供了用于部署、托管和管理统一通信应用程序的平台。</span><span class="sxs-lookup"><span data-stu-id="66f73-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="66f73-110">应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="66f73-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="66f73-111">**响应组应用程序**    响应组应用程序是由应用程序服务承载的统一通信应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="66f73-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="66f73-112">如果将未分配的电话号码范围配置为路由到通知，则响应组应用程序需要将对电话号码的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="66f73-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="66f73-113">如果所有区域都配置为路由到 Exchange 统一消息 (UM) ，则不需要 (响应组应用程序。 ) </span><span class="sxs-lookup"><span data-stu-id="66f73-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="66f73-114">**音频文件**    音频文件用于通知。</span><span class="sxs-lookup"><span data-stu-id="66f73-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="66f73-115">**文件存储**    通知应用程序使用文件存储来存储其音频文件。</span><span class="sxs-lookup"><span data-stu-id="66f73-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="66f73-116">**Lync Server 控制面板**    您可以使用 Lync Server 控制面板配置未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="66f73-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="66f73-117">**Lync Server 命令行**     管理程序您可以使用 Lync Server 命令行管理程序 cmdlet 配置通知设置和未分配号码表。</span><span class="sxs-lookup"><span data-stu-id="66f73-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

