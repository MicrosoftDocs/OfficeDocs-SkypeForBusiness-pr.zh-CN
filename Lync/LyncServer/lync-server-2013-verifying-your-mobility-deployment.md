---
title: Lync Server 2013：验证您的移动功能部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6c82478fffe2815e9d69b870b3b434eadb3cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="04628-102">在 Lync Server 2013 中验证您的移动功能部署</span><span class="sxs-lookup"><span data-stu-id="04628-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04628-103">_**主题上次修改时间：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="04628-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="04628-104">部署 Lync Server 移动服务和 Lync Server 自动发现服务之后，运行测试事务以验证你的部署是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="04628-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="04628-105">你可以运行**Test CsUcwaConference**来测试两个正在使用 Lync 2013 移动客户端的用户在会议中创建、加入和沟通的能力。</span><span class="sxs-lookup"><span data-stu-id="04628-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="04628-106">若要使用此测试事务，需要两个实际用户或测试用户及其完整凭据。</span><span class="sxs-lookup"><span data-stu-id="04628-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="04628-107">使用**CsMcxP2PIM**测试在两个使用 Lync 2010 Mobile 的用户之间发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="04628-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="04628-108">与**CsUcwaConference 测试**类似，你可以使用两个实际用户或两个预定义的测试用户。</span><span class="sxs-lookup"><span data-stu-id="04628-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="04628-109">为 Lync 2013 移动客户端测试会议</span><span class="sxs-lookup"><span data-stu-id="04628-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="04628-110">以 CsAdministrator 角色的成员身份登录任何安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。</span><span class="sxs-lookup"><span data-stu-id="04628-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="04628-111">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="04628-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04628-112">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="04628-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="04628-113">你可以在脚本中设置凭据并将其传递给测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04628-113">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="04628-114">例如：</span><span class="sxs-lookup"><span data-stu-id="04628-114">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="04628-115">要测试 Lync 2010 Mobile 的人至个人即时消息（IM）</span><span class="sxs-lookup"><span data-stu-id="04628-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="04628-116">以 CsAdministrator 角色的成员身份登录任何安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。</span><span class="sxs-lookup"><span data-stu-id="04628-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="04628-117">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="04628-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04628-118">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="04628-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="04628-119">你可以在脚本中设置凭据并将其传递给测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04628-119">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="04628-120">例如：</span><span class="sxs-lookup"><span data-stu-id="04628-120">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04628-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04628-121">See Also</span></span>


[<span data-ttu-id="04628-122">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="04628-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="04628-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="04628-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

