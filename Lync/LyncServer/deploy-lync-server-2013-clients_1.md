---
title: 部署 Lync Server 2013 客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="35d4a-102">部署 Lync Server 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="35d4a-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35d4a-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="35d4a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="35d4a-104">将用户迁移到 Lync Server 2013 后，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35d4a-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="35d4a-105">在新的 Lync Server 2013 服务器上使用客户端版本筛选器，仅允许已安装最新更新的客户端登录。</span><span class="sxs-lookup"><span data-stu-id="35d4a-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="35d4a-106">如有必要，请配置客户端引导所需的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="35d4a-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="35d4a-107">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="35d4a-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="35d4a-108">只有当你想要更改现有客户端引导策略或想要设置新的客户端引导策略时，才需要配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="35d4a-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="35d4a-109">如果您不打算配置客户端引导策略，或者希望旧的客户端引导策略保持有效，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="35d4a-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="35d4a-110">使用 Lync Server 2013 控制面板、Lync Server 2013 管理外壳程序或同时使用这两者，为特定用户或用户组配置其他用户和客户端策略。</span><span class="sxs-lookup"><span data-stu-id="35d4a-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="35d4a-111">有关详细信息，请参阅规划文档中[Lync 2013 的新增和更改设置](lync-server-2013-new-and-changed-settings-for-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="35d4a-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="35d4a-112">部署最新版本的 Lync Server 2013 客户端以及最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="35d4a-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="35d4a-113">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)"。</span><span class="sxs-lookup"><span data-stu-id="35d4a-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="35d4a-114">可选如果你的组织需要 Lync Server 2013 增强状态隐私模式，在迁移完成后，请定义客户端版本策略规则以防止较早版本的客户端版本登录。</span><span class="sxs-lookup"><span data-stu-id="35d4a-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="35d4a-115">然后，启用 "增强状态隐私模式"。</span><span class="sxs-lookup"><span data-stu-id="35d4a-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="35d4a-116">不要启用 Lync 2013 增强的状态隐私模式，直到给定服务器池中的每个用户都安装了最新的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="35d4a-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

