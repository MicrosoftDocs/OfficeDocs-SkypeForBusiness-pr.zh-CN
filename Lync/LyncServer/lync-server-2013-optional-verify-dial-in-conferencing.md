---
title: Lync Server 2013：（可选）验证电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1b5f078ccd5e95df708012b7be1527736133392
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="f40bb-102">（可选）在 Lync Server 2013 中验证电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="f40bb-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f40bb-103">_**主题上次修改时间：** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="f40bb-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="f40bb-104">要验证“电话拨入式会议设置”网页和拨入访问号码是否工作正常，您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f40bb-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="f40bb-105">通过登录简单 URL 来测试“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="f40bb-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="f40bb-p101">通过运行本主题后面的脚本来测试该访问号码在特定池中是否工作正常。此脚本模拟对访问号码的呼叫。要使用此脚本，需要提供该特定池承载的一个统一通信 (UC) 客户端的 SIP 地址和凭据。</span><span class="sxs-lookup"><span data-stu-id="f40bb-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="f40bb-109">此步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="f40bb-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="f40bb-110">测试特定池的访问号码</span><span class="sxs-lookup"><span data-stu-id="f40bb-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="f40bb-111">以 RTCUniversalServerAdmins 组成员的身份登录计算机，或者作为**Cs-ServerAdministrator**或**CsAdministrator**角色的成员登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="f40bb-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="f40bb-112">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="f40bb-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f40bb-113">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="f40bb-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="f40bb-p102">得出的报告将显示 Success 或 Failure，以及具体的诊断信息。–Verbose 标志提供有关查找到的访问号码数目及其详细信息的更多详情。</span><span class="sxs-lookup"><span data-stu-id="f40bb-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

