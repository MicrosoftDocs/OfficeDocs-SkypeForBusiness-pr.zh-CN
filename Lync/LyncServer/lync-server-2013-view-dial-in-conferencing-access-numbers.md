---
title: Lync Server 2013：查看电话拨入式会议访问号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e86127c2a945bcd9154df0456545f5783fd1a34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="7e01e-102">在 Lync Server 2013 中查看电话拨入式会议接入号码</span><span class="sxs-lookup"><span data-stu-id="7e01e-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e01e-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7e01e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7e01e-104">在 Lync Server 2013 控制面板中，为用户提供电话拨入访问号码，以便他们可以在外部加入会议。</span><span class="sxs-lookup"><span data-stu-id="7e01e-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="7e01e-105">查看拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="7e01e-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="7e01e-106">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7e01e-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e01e-107">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7e01e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7e01e-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7e01e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7e01e-109">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7e01e-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="7e01e-110">在“**拨入访问号码**”页上，单击要查看的访问号码。</span><span class="sxs-lookup"><span data-stu-id="7e01e-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="7e01e-111">在 "**编辑**" 中，选择 "**显示详细信息 ...** "</span><span class="sxs-lookup"><span data-stu-id="7e01e-111">In **Edit**, select the **Show Details…**</span></span> <span data-ttu-id="7e01e-112">复选框。</span><span class="sxs-lookup"><span data-stu-id="7e01e-112">check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7e01e-113">使用 Windows PowerShell Cmdlet 查看电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="7e01e-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7e01e-114">可以使用 Windows PowerShell 和 CsDialInConferencingAccessNumber cmdlet 查看电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="7e01e-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="7e01e-115">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="7e01e-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7e01e-116">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="7e01e-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="7e01e-117">查看电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="7e01e-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="7e01e-118">若要查看有关所有电话拨入式会议访问号码的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="7e01e-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="7e01e-119">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="7e01e-119">That will return information similar to this:</span></span>
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

<span data-ttu-id="7e01e-120">有关详细信息，请参阅[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7e01e-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

