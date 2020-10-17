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
ms.openlocfilehash: 0643c0d7da4dbed734bfd098cc2a585e018bf0cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532939"
---
# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="61f43-102">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="61f43-102">Test voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f43-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="61f43-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="61f43-104">您可以使用 Lync Server 控制面板 " **测试语音路由** " 选项卡配置测试用例方案。</span><span class="sxs-lookup"><span data-stu-id="61f43-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="61f43-105">要定义测试用例，请指定拨号计划、语音策略、PSTN 用法和语音路由，据此测试指定的电话号码。</span><span class="sxs-lookup"><span data-stu-id="61f43-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="61f43-106">在实际部署语音路由配置之前，我们建议您在各种电话号码上进行测试，以确保结果正是您所期望的。</span><span class="sxs-lookup"><span data-stu-id="61f43-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="61f43-107">可以使用“导出测试用例”<STRONG></STRONG>和“导入测试用例”<STRONG></STRONG>命令保存语音路由测试用例，并在其他计算机中导入这些用例供使用。</span><span class="sxs-lookup"><span data-stu-id="61f43-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="61f43-108">如果删除语音路由配置中的部分内容，如拨号计划、语音策略、语音路由或电话用法，应检查并更新语音路由测试用例。</span><span class="sxs-lookup"><span data-stu-id="61f43-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="61f43-109">Lync Server 控制面板不会提醒你由于配置发生变化而不再有效的测试用例。</span><span class="sxs-lookup"><span data-stu-id="61f43-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61f43-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="61f43-110">In This Section</span></span>

  - [<span data-ttu-id="61f43-111">在 Lync Server 2013 中创建语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61f43-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="61f43-112">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61f43-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="61f43-113">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61f43-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="61f43-114">在 Lync Server 2013 中运行语音路由测试</span><span class="sxs-lookup"><span data-stu-id="61f43-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

