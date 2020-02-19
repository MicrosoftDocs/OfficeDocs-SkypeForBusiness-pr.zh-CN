---
title: Lync Server 2013：导出语音路由测试用例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcca6e09be8c3a5607e7888a35c14f125f3475fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="7d0af-102">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="7d0af-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d0af-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7d0af-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7d0af-104">测试用例为您在组织中测试语音路由提供了一种方法：定义要拨打的号码以及要使用的拨号计划和语音策略等事项，并且 Lync Server 可以验证是否在给定这些条件的情况下，提供的号码可以已成功路由到 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="7d0af-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="7d0af-105">可以使用 Lync Server 控制面板创建的测试用例通常仅保存在最初创建和运行事例的服务器上。</span><span class="sxs-lookup"><span data-stu-id="7d0af-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="7d0af-106">但是，这些测试用例可导出为 XML 文件（使用 .vtest 扩展名），然后在其他服务器上导入。</span><span class="sxs-lookup"><span data-stu-id="7d0af-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="7d0af-107">这使您可在位于拓扑中的不同点上的不同计算机上运行相同的测试。</span><span class="sxs-lookup"><span data-stu-id="7d0af-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="7d0af-108">导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="7d0af-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="7d0af-109">在 "Lync Server 控制面板" 中，单击 "**语音路由**"，然后单击 "**测试语音路由**"。</span><span class="sxs-lookup"><span data-stu-id="7d0af-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="7d0af-p102">在“测试语音路由”\*\*\*\* 选项卡上，选择要导出的一个或多个测试用例。若要选择多个测试用例，请单击要导出的第一个用例，然后在按住 Ctrl 键的同时选择要导出的其他用例。</span><span class="sxs-lookup"><span data-stu-id="7d0af-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="7d0af-112">在“操作”\*\*\*\* 菜单上，单击“导出测试用例”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7d0af-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="7d0af-p103">在“另存为”\*\*\*\* 对话框中，选择要存储已导出测试用例的文件夹，并在“文件名”\*\*\*\* 框中为生成的 XML 文件键入一个名称。请注意，如果要导出多个测试用例，则所有这些测试用例都将保存到单个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="7d0af-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="7d0af-115">若要保存测试用例，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7d0af-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d0af-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d0af-116">See Also</span></span>


[<span data-ttu-id="7d0af-117">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="7d0af-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

