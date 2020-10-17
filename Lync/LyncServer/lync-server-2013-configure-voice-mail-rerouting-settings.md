---
title: Lync Server 2013：配置语音邮件重新路由设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b51a529ee7bc4fd1148413058ceaf1f1f6d61e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520179"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="ee6c9-102">在 Lync Server 2013 中配置语音邮件重新路由设置</span><span class="sxs-lookup"><span data-stu-id="ee6c9-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee6c9-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ee6c9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ee6c9-104">Survivable 分支机构和 Survivable 分支服务器可在 WAN 中断期间为分支用户提供语音邮件留存能力（如果 Exchange 统一消息 (UM) 安装在中央站点，并且部署了 Exchange UM 邮件自动助理 (AA) 。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="ee6c9-105">建议 Exchange 管理员将 AA 配置为仅接受消息，禁用其他常规功能，例如转接到用户或接线员的功能。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="ee6c9-106">此外，也可以使用常规 AA 或为路由呼叫而自定义的 AA。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="ee6c9-107">有关详细信息，请参阅规划文档中的 [Lync Server 2013 分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md) 一节中的 "准备语音邮件留存性" 一节。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="ee6c9-108">配置语音邮件生存能力</span><span class="sxs-lookup"><span data-stu-id="ee6c9-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="ee6c9-109">请求 Exchange 管理员将 AA 配置为仅接受 Exchange 命令行管理器中 (的以下 cmdlet 使用以下 cmdlet： **get-umautoattendant \<AA name\> -CallSomeoneEnabled $false**。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="ee6c9-110">默认情况下，指定允许留言的参数 (*SendVoiceMsgEnabled*) 为 true。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="ee6c9-111">在 Lync Server 命令行管理程序中，使用 **CSVoiceMailReroutingConfiguration** CMDLET 将 AA 电话号码设置为 Survivable 分支设备或 Survivable 分支服务器上的语音邮件重新路由配置中的 Exchange UM 自动助理电话号码。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ee6c9-112">如果以后需要修改语音邮件重新路由设置，请使用 <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet 执行相应的操作。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="ee6c9-113">有关 <STRONG>New-</STRONG> 和 <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> 的详细信息，请参阅相应的 Shell 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="ee6c9-114">将与分支用户的 Exchange UM 拨号计划对应的 Exchange UM 订阅者访问号码设置为 Survivable 分支设备或 Survivable 分支服务器上的语音邮件重新路由配置中的 Exchange UM 订阅者访问号码。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ee6c9-115">配置 Exchange UM 用户的拨号计划，以便在 WAN 中断期间需要访问 "获取语音邮件" 功能的所有分支用户都有一个与之关联的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="ee6c9-116">Survivable 分支装置或 Survivable 分支服务器的**下一步**：[在 Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ee6c9-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

