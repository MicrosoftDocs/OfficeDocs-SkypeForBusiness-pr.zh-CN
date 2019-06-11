---
title: 'Lync Server 2013: 音频/视频 (A/V) 边缘服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="bfeed-102">Lync Server 2013 中的音频/视频 (A/V) 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="bfeed-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfeed-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfeed-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfeed-104">A/V 边缘服务为内部用户 (登录到你的组织网络的用户) 提供一种方法, 以便与外部用户 (未登录到你的组织网络的用户) 共享音频和视频。</span><span class="sxs-lookup"><span data-stu-id="bfeed-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="bfeed-105">除了音频和视频, A/V 边缘服务还提供有关桌面共享和文件传输等方面的支持。</span><span class="sxs-lookup"><span data-stu-id="bfeed-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="bfeed-106">A/V 边缘服务主要通过使用 A/V 边缘配置进行管理;使用这些设置, 你可以管理每个端口和每个用户分配的最大带宽量, 并指定在必须续订该令牌之前可以使用身份验证令牌的时间长度。</span><span class="sxs-lookup"><span data-stu-id="bfeed-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="bfeed-107">A/V 边缘配置设置可应用于网站或单个 A/V 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="bfeed-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="bfeed-108">确定哪个设置集合优先时, 请使用以下指南:</span><span class="sxs-lookup"><span data-stu-id="bfeed-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="bfeed-109">在服务作用域 (即在单个服务器上) 中配置的设置优先于所有内容。</span><span class="sxs-lookup"><span data-stu-id="bfeed-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="bfeed-110">在网站范围内配置的设置优先于在全局范围内配置的设置。</span><span class="sxs-lookup"><span data-stu-id="bfeed-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="bfeed-111">但是, 服务范围设置还将取代网站范围的设置。</span><span class="sxs-lookup"><span data-stu-id="bfeed-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="bfeed-112">只有在单个服务器上没有配置任何服务设置且该服务器所在的网站没有网站设置的情况下, 才会使用全局范围内的设置。</span><span class="sxs-lookup"><span data-stu-id="bfeed-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="bfeed-113">只有使用 Lync Server PowerShell 和 CsAVEdgeConfiguration cmdlet 才能管理 A/V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="bfeed-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfeed-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="bfeed-114">In This Section</span></span>

  - [<span data-ttu-id="bfeed-115">返回 Lync Server 2013 中的 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="bfeed-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="bfeed-116">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="bfeed-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="bfeed-117">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="bfeed-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

