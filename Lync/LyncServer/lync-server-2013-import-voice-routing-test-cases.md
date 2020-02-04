---
title: Lync Server 2013：导入语音路由测试用例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013860ea52773f4109c56bd71d37a9f4b8938225
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="67fd1-102">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="67fd1-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67fd1-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="67fd1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="67fd1-104">测试用例为你提供了一种测试你的组织中的语音路由的方法：定义要拨打的号码以及要使用的拨号计划和语音策略等内容，并且 Lync Server 2013 可以验证所提供的号码是否可以 successfully 将路由到 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="67fd1-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="67fd1-105">可以使用 Lync Server "控制面板" 创建的测试用例通常仅保存在最初创建和运行该事例的服务器上。</span><span class="sxs-lookup"><span data-stu-id="67fd1-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="67fd1-106">但是，这些测试用例可以导出为 XML 文件（扩展名为 vtest），然后在其他服务器上导入这些测试用例。</span><span class="sxs-lookup"><span data-stu-id="67fd1-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="67fd1-107">这使你能够在位于拓扑中不同点的不同计算机上运行相同的测试。</span><span class="sxs-lookup"><span data-stu-id="67fd1-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="67fd1-108">导入语音路由测试案例</span><span class="sxs-lookup"><span data-stu-id="67fd1-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="67fd1-109">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="67fd1-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="67fd1-110">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="67fd1-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="67fd1-111">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="67fd1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67fd1-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="67fd1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67fd1-113">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67fd1-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="67fd1-114">在 "**操作**" 菜单上，单击 "**导入测试用例**"。</span><span class="sxs-lookup"><span data-stu-id="67fd1-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="67fd1-115">找到要导入的测试用例文件（vtest），然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="67fd1-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="67fd1-116">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67fd1-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67fd1-117">在导入 vtest 文件时，必须运行 "<STRONG>全部提交</STRONG>" 命令以发布测试用例。</span><span class="sxs-lookup"><span data-stu-id="67fd1-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="67fd1-118">有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="67fd1-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67fd1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67fd1-119">See Also</span></span>


[<span data-ttu-id="67fd1-120">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="67fd1-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

