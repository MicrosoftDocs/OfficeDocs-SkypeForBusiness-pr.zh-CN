---
title: Lync Server 2013： Lync 2013 的组策略设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3023741b1b9e71d7789857c9b55fb195453ee5b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="8dee8-102">Lync 2013 的组策略设置</span><span class="sxs-lookup"><span data-stu-id="8dee8-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dee8-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8dee8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8dee8-104">在早期版本的 Lync 和 Office Communicator 中，有一个独立的 Communicator 管理模板可用于配置客户端组策略设置。</span><span class="sxs-lookup"><span data-stu-id="8dee8-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="8dee8-105">对于 Lync 2013，新的管理模板文件（admx 和 adml 文件）与 Office 组策略管理模板一起附带。</span><span class="sxs-lookup"><span data-stu-id="8dee8-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="8dee8-106">Lync 2013 admx 和 adml 文件的可用性使你可以下载模板并集中管理所有 Office 程序和语言包的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="8dee8-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="8dee8-107">有关详细信息，请参阅 Office 2013 文档中的 "Office 2013 管理模板文件（ADMX、ADML） <http://go.microsoft.com/fwlink/p/?linkid=267516>"。</span><span class="sxs-lookup"><span data-stu-id="8dee8-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="8dee8-108">客户端引导策略</span><span class="sxs-lookup"><span data-stu-id="8dee8-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="8dee8-109">在用户首次登录到服务器之前，应先配置几个客户端引导策略。</span><span class="sxs-lookup"><span data-stu-id="8dee8-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="8dee8-110">由于这些策略在客户端登录并开始从服务器接收带内预配设置后生效，因此你可以使用组策略来配置它们。</span><span class="sxs-lookup"><span data-stu-id="8dee8-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="8dee8-111">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="8dee8-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

