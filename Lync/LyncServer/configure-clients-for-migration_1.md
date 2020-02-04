---
title: 配置客户端以进行迁移
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="8df60-102">配置客户端以进行迁移</span><span class="sxs-lookup"><span data-stu-id="8df60-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8df60-103">_**主题上次修改时间：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="8df60-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="8df60-104">本主题包含在迁移到 Lync Server 2013 之前应执行的推荐的客户端部署步骤。</span><span class="sxs-lookup"><span data-stu-id="8df60-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="8df60-105">应在 Office 通信服务器 2007 R2 上进行这些配置更改。</span><span class="sxs-lookup"><span data-stu-id="8df60-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="8df60-106">在迁移之前执行这些步骤非常重要。</span><span class="sxs-lookup"><span data-stu-id="8df60-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="8df60-107">有关详细信息，请参阅[在 Lync Server 2013 中规划客户端和设备](lync-server-2013-planning-for-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="8df60-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="8df60-108">在迁移之前配置客户端</span><span class="sxs-lookup"><span data-stu-id="8df60-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="8df60-109">部署最新的 Office 通信服务器 2007 R2 服务器、客户端和设备更新（修补程序）：</span><span class="sxs-lookup"><span data-stu-id="8df60-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="8df60-110">应用 Office 通信服务器 2007 R2 更新</span><span class="sxs-lookup"><span data-stu-id="8df60-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="8df60-111">有关 Communicator 2007 R2 的累积更新包的说明</span><span class="sxs-lookup"><span data-stu-id="8df60-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="8df60-112">获取设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="8df60-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="8df60-113">在 Office 通信服务器 2007 R2 上，使用客户端版本筛选仅允许具有已安装最新更新的 Office 通信服务器 2007 R2 客户端登录。</span><span class="sxs-lookup"><span data-stu-id="8df60-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="8df60-114">在 Office 通信服务器 2007 R2 上，使用客户端版本筛选阻止 Lync Server 2013 客户端登录。</span><span class="sxs-lookup"><span data-stu-id="8df60-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="8df60-115">按照**配置客户端版本筛选** [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488)中介绍的步骤添加下表中列出的版本筛选器。</span><span class="sxs-lookup"><span data-stu-id="8df60-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="8df60-116">对于每个版本筛选器，分配操作**块**。</span><span class="sxs-lookup"><span data-stu-id="8df60-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8df60-117">客户端</span><span class="sxs-lookup"><span data-stu-id="8df60-117">Client</span></span></th>
    <th><span data-ttu-id="8df60-118">用户代理标题</span><span class="sxs-lookup"><span data-stu-id="8df60-118">User agent header</span></span></th>
    <th><span data-ttu-id="8df60-119">版本</span><span class="sxs-lookup"><span data-stu-id="8df60-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8df60-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8df60-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="8df60-121">OC</span><span class="sxs-lookup"><span data-stu-id="8df60-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="8df60-122">15 ...\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8df60-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8df60-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8df60-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="8df60-124">CWA</span><span class="sxs-lookup"><span data-stu-id="8df60-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="8df60-125">5 ...\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8df60-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8df60-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8df60-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="8df60-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="8df60-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="8df60-128">4 ...\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8df60-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

