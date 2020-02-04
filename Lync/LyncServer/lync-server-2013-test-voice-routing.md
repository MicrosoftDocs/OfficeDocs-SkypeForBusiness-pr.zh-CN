---
title: Lync Server 2013：测试语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27fc4f3dfc42e9187ea0aee801b3c2115d83ff0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="9690f-102">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="9690f-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9690f-103">_**主题上次修改时间：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9690f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9690f-104">你可以使用 Lync Server 控制面板 "**测试语音路由**" 选项卡来配置测试用例方案。</span><span class="sxs-lookup"><span data-stu-id="9690f-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="9690f-105">若要定义测试用例，请指定用于测试指定电话号码的拨号计划、语音策略、PSTN 使用和语音路由。</span><span class="sxs-lookup"><span data-stu-id="9690f-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="9690f-106">在实际部署你的语音路由配置之前，我们建议你在不同的电话号码上测试它，以确保结果是你所期望的。</span><span class="sxs-lookup"><span data-stu-id="9690f-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9690f-107">你可以使用 "<STRONG>导出测试用例</STRONG>" 和 "<STRONG>导入测试用</STRONG>例" 命令来保存语音路由测试案例并将其导入以在另一台计算机上使用。</span><span class="sxs-lookup"><span data-stu-id="9690f-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="9690f-108">如果您删除了 "语音路由" 配置的任何部分，如拨号计划、语音策略、语音路由或电话使用，您应该查看和更新您的语音路由测试案例。</span><span class="sxs-lookup"><span data-stu-id="9690f-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="9690f-109">Lync Server 控制面板将不会向你提示由于配置发生更改而不再有效的测试案例。</span><span class="sxs-lookup"><span data-stu-id="9690f-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9690f-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="9690f-110">In This Section</span></span>

  - [<span data-ttu-id="9690f-111">在 Lync Server 2013 中创建语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="9690f-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="9690f-112">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="9690f-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="9690f-113">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="9690f-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="9690f-114">在 Lync Server 2013 中运行语音路由测试</span><span class="sxs-lookup"><span data-stu-id="9690f-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

