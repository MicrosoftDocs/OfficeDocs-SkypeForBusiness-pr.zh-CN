---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="b251f-102">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="b251f-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b251f-103">_**主题上次修改时间：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b251f-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b251f-104">你可以使用 Microsoft Lync Server 2010 控制面板阻止在特定计算机上运行的所有 Lync Server 2010 服务的新会话或阻止特定 Lync Server 2010 服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="b251f-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="b251f-105">阻止计算机上所有 Lync Server 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="b251f-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="b251f-106">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b251f-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b251f-107">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b251f-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b251f-108">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b251f-109">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="b251f-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="b251f-110">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-110">Click **Action**.</span></span>

6.  <span data-ttu-id="b251f-111">单击 "**阻止所有服务的新会话**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="b251f-112">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="b251f-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="b251f-113">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b251f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b251f-114">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b251f-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b251f-115">在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b251f-116">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="b251f-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="b251f-117">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="b251f-118">对服务列表进行排序（如有必要），然后单击要阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="b251f-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="b251f-119">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-119">Click **Action**.</span></span>

8.  <span data-ttu-id="b251f-120">单击 "**阻止新的服务会话**"。</span><span class="sxs-lookup"><span data-stu-id="b251f-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="b251f-121">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b251f-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

