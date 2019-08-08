---
title: 将语音路由更改为使用新的 Lync Server 2013 中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba933ec7c51b62e7f5008ad9f767a0695c88ebb2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="ed3b8-102">将语音路由更改为使用新的 Lync Server 2013 中介服务器</span><span class="sxs-lookup"><span data-stu-id="ed3b8-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed3b8-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ed3b8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ed3b8-104">此过程会将语音路由更改为使用 Lync Server 2013 中介服务器, 而不是旧版 Office 通信服务器 2007 R2 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="ed3b8-105">将语音路由更改为使用新的中介服务器</span><span class="sxs-lookup"><span data-stu-id="ed3b8-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="ed3b8-106">Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="ed3b8-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="ed3b8-107">在左窗格中, 选择 "**语音路由**", 然后选择 "**路由**"。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="ed3b8-108">单击 "**新建**" 以创建新的语音路由。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="ed3b8-109">填写以下字段:</span><span class="sxs-lookup"><span data-stu-id="ed3b8-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="ed3b8-110">**名称**: 键入语音路线的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="ed3b8-111">对于本文档, 我们将使用**W15PSTNRoute**。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="ed3b8-112">**说明**: 键入语音路线的简短说明。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="ed3b8-113">跳过其余所有分区, 直到您到达**相关网关**。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="ed3b8-114">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-114">Click **Add**.</span></span> <span data-ttu-id="ed3b8-115">选择新的默认网关, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="ed3b8-116">在 "**关联的 PSTN 用法**" 下, 单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="ed3b8-117">在 "**选择 PSTN 使用记录**" 页面上, 选择一个记录名称, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="ed3b8-118">从新的 "**语音路由**" 页面上, 单击 **"确定"** 以创建**语音路由**。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="ed3b8-119">从 "**语音路由**" 页面上, 选择 "**传送**"。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="ed3b8-120">将新创建的路由移动到列表顶部, 然后选择 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="ed3b8-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

