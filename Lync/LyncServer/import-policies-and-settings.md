---
title: 导入策略和设置
description: 导入策略和设置。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569028"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="b77e7-103">导入策略和设置</span><span class="sxs-lookup"><span data-stu-id="b77e7-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b77e7-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b77e7-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b77e7-105">将 Office 通信服务器 2007 R2 拓扑信息与 Lync Server 2013 试验池合并后，您需要运行 Lync Server 2013 命令行管理程序 cmdlet，将 Office 通信服务器 2007 R2 策略和配置设置迁移到 Lync Server 2013 引导池。</span><span class="sxs-lookup"><span data-stu-id="b77e7-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="b77e7-106">**CsLegacyConfiguration** cmdlet 可将策略、语音路由、拨号计划、Communicator Web 访问 url 和电话拨入访问号码导入到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b77e7-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="b77e7-107">迁移策略和设置</span><span class="sxs-lookup"><span data-stu-id="b77e7-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="b77e7-108">在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b77e7-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b77e7-109">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="b77e7-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="b77e7-110">导入策略后，请按照下面的过程操作，在 Lync Server 控制面板中查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="b77e7-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="b77e7-111">查看导入的策略</span><span class="sxs-lookup"><span data-stu-id="b77e7-111">To view imported policies</span></span>

1.  <span data-ttu-id="b77e7-112">打开 "Lync Server 2013 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b77e7-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="b77e7-113">单击“语音路由”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="b77e7-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="b77e7-114">单击“会议”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="b77e7-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="b77e7-115">单击“联盟和外部访问”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="b77e7-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="b77e7-116">单击“监控和存档”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="b77e7-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

