---
title: Lync Server 2013：呼叫寄存使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="93924-102">Lync Server 2013 中呼叫寄存使用的组件</span><span class="sxs-lookup"><span data-stu-id="93924-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93924-103">_**上次修改的主题：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="93924-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="93924-104">当您部署企业语音时，呼叫寄存应用程序将自动安装。</span><span class="sxs-lookup"><span data-stu-id="93924-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="93924-105">通过配置语音策略启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="93924-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="93924-106">以下 Lync Server 2013 组件支持呼叫寄存应用程序：</span><span class="sxs-lookup"><span data-stu-id="93924-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="93924-107">**Application service**   Application service 提供用于部署、托管和管理统一通信应用程序（如呼叫寄存应用程序）的平台。</span><span class="sxs-lookup"><span data-stu-id="93924-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="93924-108">应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="93924-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="93924-109">**呼叫寄存应用**   程序呼叫寄存应用程序是由应用程序服务托管的统一通信应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="93924-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="93924-110">在部署企业语音时，它会自动包含在内。</span><span class="sxs-lookup"><span data-stu-id="93924-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="93924-111">呼叫寄存公园和检索呼叫并管理呼叫寄存轨道式。</span><span class="sxs-lookup"><span data-stu-id="93924-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="93924-112">**音乐-开**   即用文件如果启用了音乐，则在呼叫寄存时播放音乐文件。</span><span class="sxs-lookup"><span data-stu-id="93924-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="93924-113">安装呼叫寄存应用程序时，会包含一个默认的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="93924-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="93924-114">**文件存储**   呼叫寄存应用程序使用文件存储来保存自定义音频文件。</span><span class="sxs-lookup"><span data-stu-id="93924-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="93924-115">**Lync server 控制面板**   您可以使用 lync server 控制面板配置呼叫寄存通道表，并为用户启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="93924-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="93924-116">**Lync server 命令行**   管理程序可以使用 Lync server 命令行管理程序 cmdlet 执行所有呼叫寄存应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="93924-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

