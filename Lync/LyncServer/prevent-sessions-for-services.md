---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f85595acd38e69af9fb8108cab44f4839904799a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="b45e8-102">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="b45e8-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b45e8-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b45e8-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b45e8-104">您可以使用 Microsoft Lync Server 2010 控制面板阻止在特定计算机上运行的所有 Lync Server 2010 服务的新会话或阻止特定 Lync Server 2010 服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="b45e8-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="b45e8-105">阻止计算机上所有 Lync Server 服务的新会话</span><span class="sxs-lookup"><span data-stu-id="b45e8-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="b45e8-106">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b45e8-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b45e8-107">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b45e8-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b45e8-108">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b45e8-109">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="b45e8-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="b45e8-110">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-110">Click **Action**.</span></span>

6.  <span data-ttu-id="b45e8-111">单击“阻止所有服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="b45e8-112">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="b45e8-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="b45e8-113">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b45e8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b45e8-114">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b45e8-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b45e8-115">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b45e8-116">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="b45e8-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="b45e8-117">单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="b45e8-118">如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="b45e8-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="b45e8-119">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-119">Click **Action**.</span></span>

8.  <span data-ttu-id="b45e8-120">单击“阻止服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="b45e8-121">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b45e8-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

