---
title: Lync Server 2013：音频/视频 (A/V) 边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a83aa6c21be0a1055be091ab7195f3c03c4c6e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508269"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="c3731-102">Lync Server 2013 中的音频/视频 (A/V) 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c3731-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3731-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3731-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3731-p101">A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。除了音频和视频以外，A/V 边缘服务还提供对诸如桌面共享和文件传输等内容的支持。</span><span class="sxs-lookup"><span data-stu-id="c3731-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="c3731-p102">A/V 边缘服务主要通过使用 A/V 边缘配置进行管理；通过这些设置，您可以管理针对每个端口和每个用户要分配的最大带宽量，并指定在必须续订身份验证令牌之前可以使用该令牌的时间长度。A/V 边缘配置设置可以应用到站点或个别 A/V 边缘服务器。在确定哪个设置集合将取得优先权时，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="c3731-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="c3731-109">在服务范围（也就是，在个别服务器上）配置的设置的优先于一切。</span><span class="sxs-lookup"><span data-stu-id="c3731-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="c3731-p103">在站点范围配置的设置的优先于在全局范围配置的设置。然而，服务范围设置还将取代站点范围设置。</span><span class="sxs-lookup"><span data-stu-id="c3731-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="c3731-112">只有未在个别服务器上配置任何服务设置，并且在服务器所在的站点没有站点设置时，才会使用全局范围的设置。</span><span class="sxs-lookup"><span data-stu-id="c3731-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="c3731-113">只能使用 Lync Server PowerShell 和 CsAVEdgeConfiguration cmdlet 来管理 A/V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="c3731-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3731-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c3731-114">In This Section</span></span>

  - [<span data-ttu-id="c3731-115">在 Lync Server 2013 中返回 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="c3731-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="c3731-116">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="c3731-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="c3731-117">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="c3731-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

