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
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="da88f-102">导入策略和设置</span><span class="sxs-lookup"><span data-stu-id="da88f-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da88f-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="da88f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="da88f-104">将 Office 通信服务器 2007 R2 拓扑信息与 Lync Server 2013 试验池合并后，您需要运行 Lync Server 2013 Management Shell cmdlet 来迁移 Office 通信服务器 2007 R2 策略和配置设置您的 Lync Server 2013 试验池。</span><span class="sxs-lookup"><span data-stu-id="da88f-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="da88f-105">**CsLegacyConfiguration** cmdlet 将策略、语音路由、拨号计划、Communicator Web Access url 和电话拨入访问号码导入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="da88f-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="da88f-106">迁移策略和设置</span><span class="sxs-lookup"><span data-stu-id="da88f-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="da88f-107">在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="da88f-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="da88f-108">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="da88f-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="da88f-109">导入策略后，请使用下面的过程在 Lync Server 控制面板中查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="da88f-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="da88f-110">查看导入的策略</span><span class="sxs-lookup"><span data-stu-id="da88f-110">To view imported policies</span></span>

1.  <span data-ttu-id="da88f-111">打开 "Lync Server 2013 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="da88f-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="da88f-112">单击 "**语音路由**"，然后查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="da88f-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="da88f-113">单击 "**会议**" 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="da88f-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="da88f-114">单击 "**联盟和外部访问**" 并查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="da88f-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="da88f-115">单击 "**监视和存档**"，然后查看导入的策略。</span><span class="sxs-lookup"><span data-stu-id="da88f-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

