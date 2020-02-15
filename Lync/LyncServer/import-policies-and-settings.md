---
title: 导入策略和设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12a47ffde7d09fa7e216312211b6f0118b89233
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="ec9d3-102">导入策略和设置</span><span class="sxs-lookup"><span data-stu-id="ec9d3-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec9d3-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ec9d3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ec9d3-104">将 Office 通信服务器 2007 R2 拓扑信息与 Lync Server 2013 引导池合并后，您需要运行 Lync Server 2013 命令行管理程序 cmdlet 以迁移 Office 通信服务器 2007 R2 策略和配置设置到你的 Lync Server 2013 试点池。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="ec9d3-105">**CsLegacyConfiguration** cmdlet 可将策略、语音路由、拨号计划、Communicator Web 访问 url 和电话拨入访问号码导入到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="ec9d3-106">迁移策略和设置</span><span class="sxs-lookup"><span data-stu-id="ec9d3-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="ec9d3-107">在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ec9d3-108">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ec9d3-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="ec9d3-109">导入策略后，请按照下面的过程操作，在 Lync Server 控制面板中查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="ec9d3-110">查看导入的策略</span><span class="sxs-lookup"><span data-stu-id="ec9d3-110">To view imported policies</span></span>

1.  <span data-ttu-id="ec9d3-111">打开 "Lync Server 2013 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="ec9d3-112">单击“语音路由”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="ec9d3-113">单击“会议”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="ec9d3-114">单击“联盟和外部访问”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="ec9d3-115">单击“监控和存档”\*\*\*\* 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="ec9d3-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

