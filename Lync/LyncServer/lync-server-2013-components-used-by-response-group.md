---
title: Lync Server 2013：响应组使用的组件
description: Lync Server 2013：响应组使用的组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a1e916d9e4bf986bf0337a6f1f1dd918ff2772e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571698"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="79f88-103">Lync Server 2013 中的响应组使用的组件</span><span class="sxs-lookup"><span data-stu-id="79f88-103">Components used by Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79f88-104">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="79f88-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="79f88-105">当您部署企业语音时，将自动启用响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="79f88-105">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="79f88-106">本节介绍支持响应组应用程序的组件。</span><span class="sxs-lookup"><span data-stu-id="79f88-106">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="79f88-107">响应组组件</span><span class="sxs-lookup"><span data-stu-id="79f88-107">Response Group Components</span></span>

<span data-ttu-id="79f88-108">以下 Microsoft Lync Server 2013 组件支持响应组应用程序：</span><span class="sxs-lookup"><span data-stu-id="79f88-108">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="79f88-109">**应用程序服务**    应用程序服务提供了用于部署、托管和管理统一通信应用程序（如响应组）的平台。</span><span class="sxs-lookup"><span data-stu-id="79f88-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="79f88-110">应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="79f88-110">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="79f88-111">**响应组应用程序**    响应组应用程序是由应用程序服务承载的统一通信应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="79f88-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="79f88-112">当您部署响应组时，它会自动包括在内。</span><span class="sxs-lookup"><span data-stu-id="79f88-112">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="79f88-113">响应组应用程序将传入呼叫路由并排队到代理组。</span><span class="sxs-lookup"><span data-stu-id="79f88-113">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="79f88-114">**语言包**    需要语言包才能支持文本到语音转换和语音识别。</span><span class="sxs-lookup"><span data-stu-id="79f88-114">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="79f88-115">在配置邮件（如欢迎消息和其他提示，以及交互式语音响应 (IVR) 问题和解答）时，将使用这些语音技术。</span><span class="sxs-lookup"><span data-stu-id="79f88-115">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="79f88-116">默认情况下，在部署 Lync Server 2013 时，会安装26个受支持的语言包。</span><span class="sxs-lookup"><span data-stu-id="79f88-116">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="79f88-117">**音频文件**    音频文件用于邮件和保留音乐。</span><span class="sxs-lookup"><span data-stu-id="79f88-117">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="79f88-118">**文件存储**    响应组使用文件存储来存储音频文件。</span><span class="sxs-lookup"><span data-stu-id="79f88-118">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="79f88-119">多个响应组池可以使用同一实例的文件存储。</span><span class="sxs-lookup"><span data-stu-id="79f88-119">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="79f88-120">**响应组配置工具**    响应组配置工具是一个基于 web 的工具，用于创建和配置响应组。</span><span class="sxs-lookup"><span data-stu-id="79f88-120">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="79f88-121">当您安装 Web 服务时，将包含响应组配置工具。</span><span class="sxs-lookup"><span data-stu-id="79f88-121">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="79f88-122">**Microsoft Lync Server 2013 控制面板**    您可以使用 Lync Server 控制面板设置和配置响应组的代理组和队列。</span><span class="sxs-lookup"><span data-stu-id="79f88-122">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="79f88-123">**Lync Server 命令行**     管理程序可以使用 Lync Server 命令行管理程序 cmdlet 配置所有响应组设置。</span><span class="sxs-lookup"><span data-stu-id="79f88-123">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="79f88-124">**Microsoft Lync 2013**    必须先登录到组的正式代理 (代理，然后才能接受对组的呼叫) 使用 Lync 2013 登录到该组并从组中注销。</span><span class="sxs-lookup"><span data-stu-id="79f88-124">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="79f88-125">如果为正式代理配置了代理组，则代理将单击 Lync 2013 中的菜单项，以打开 Internet Explorer，并显示用于登录和注销组的网页控制台。</span><span class="sxs-lookup"><span data-stu-id="79f88-125">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="79f88-126">**Web 服务**    响应组配置工具（代理的登录和注销控制台、Lync Server 控制面板和响应组客户端 web 服务）需要 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="79f88-126">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="79f88-127">**响应组客户端 Web 服务**    响应组应用程序提供了一个客户端 web 服务，该服务可供第三方应用程序用来检索有关代理、代理组成员身份、代理登录状态、组的呼叫状态以及支持匿名呼叫的组的信息。</span><span class="sxs-lookup"><span data-stu-id="79f88-127">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="79f88-128">Lync 2013 和 Lync 2010 助理使用响应组客户端 Web 服务检索代理可用于进行匿名呼叫的响应组的列表。</span><span class="sxs-lookup"><span data-stu-id="79f88-128">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="79f88-129">当您安装 Web 服务时，将包含客户端 web 服务。</span><span class="sxs-lookup"><span data-stu-id="79f88-129">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

