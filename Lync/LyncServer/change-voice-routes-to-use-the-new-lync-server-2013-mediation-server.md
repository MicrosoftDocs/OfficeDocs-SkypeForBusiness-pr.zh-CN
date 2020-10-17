---
title: 将语音路由更改为使用新的 Lync Server 2013 中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c4ea975225eb685acaa1843e324ffa720a93e9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499659"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="3b8e2-102">将语音路由更改为使用新的 Lync Server 2013 中介服务器</span><span class="sxs-lookup"><span data-stu-id="3b8e2-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b8e2-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3b8e2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3b8e2-104">此过程将语音路由更改为使用 Lync Server 2013 中介服务器，而不是旧版 Office 通信服务器 2007 R2 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="3b8e2-105">将语音路由更改为使用新中介服务器</span><span class="sxs-lookup"><span data-stu-id="3b8e2-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="3b8e2-106">Lync Server 2013 控制面板</span><span class="sxs-lookup"><span data-stu-id="3b8e2-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="3b8e2-107">在左窗格中，选择“语音路由”\*\*\*\*，然后选择“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="3b8e2-108">单击“新建”\*\*\*\* 以创建新语音路由。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="3b8e2-109">填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b8e2-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="3b8e2-p101">**名称**：键入语音路由的描述性名称。在本文档中，我们使用 **W15PSTNRoute**。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="3b8e2-112">**说明**：键入语音路由的简要说明。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="3b8e2-p102">跳过所有其余部分，直到到达“关联网关”\*\*\*\*。单击“添加”\*\*\*\*。选择新默认网关，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="3b8e2-116">在“关联的 PSTN 用法”\*\*\*\* 下，单击“选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="3b8e2-117">从“选择 PSTN 用法记录”\*\*\*\* 页中，选择一个记录名称，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="3b8e2-118">从“新建语音路由”\*\*\*\* 页中，单击“确定”\*\*\*\* 以创建“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="3b8e2-119">从“语音路由”\*\*\*\* 页中，选择“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="3b8e2-120">将新创建的路由移至列表的顶部，然后选择“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b8e2-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

