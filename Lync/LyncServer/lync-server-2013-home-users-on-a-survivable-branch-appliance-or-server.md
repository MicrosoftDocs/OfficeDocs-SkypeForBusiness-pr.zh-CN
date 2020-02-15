---
title: Lync Server 2013： Survivable 分支设备或服务器上的家庭用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="8e24b-102">Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户</span><span class="sxs-lookup"><span data-stu-id="8e24b-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e24b-103">_**上次修改的主题：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="8e24b-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="8e24b-104">在 Survivable 分支机构或 Survivable 分支服务器上托管用户的过程与在前端池上托管用户的过程类似。</span><span class="sxs-lookup"><span data-stu-id="8e24b-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="8e24b-105">在中央站点执行 Survivable Branch 设备或 Survivable Branch Server 过程。</span><span class="sxs-lookup"><span data-stu-id="8e24b-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="8e24b-106">在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户</span><span class="sxs-lookup"><span data-stu-id="8e24b-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="8e24b-107">在将用户移动到 Survivable 分支服务器或 Survivable 分支服务器之前，请打开 Lync Server 命令行管理程序，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e24b-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="8e24b-108">运行 cmdlet **CsPstnOutboundCall**以验证 Survivable 分支服务器是否正在运行，以及是否配置了公共交换电话网络（PSTN）连接。</span><span class="sxs-lookup"><span data-stu-id="8e24b-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="8e24b-109">如果需要修改 PSTN 网关属性，请使用 cmdlet **Set-CsPstnGateway**。</span><span class="sxs-lookup"><span data-stu-id="8e24b-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="8e24b-110">运行 cmdlet **set-csvoicepolicy**以验证将托管在 Survivable 分支服务器上的用户是否具有相应的 VoIP 路由策略。</span><span class="sxs-lookup"><span data-stu-id="8e24b-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="8e24b-111">如果需要修改 VoIP 策略，请使用 cmdlet **Set-CsVoicePolicy**。</span><span class="sxs-lookup"><span data-stu-id="8e24b-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="8e24b-112">运行 cmdlet **Get-CsVoicemailReroutingConfiguration** 来验证是否已配置语音邮件重新路由设置。</span><span class="sxs-lookup"><span data-stu-id="8e24b-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="8e24b-113">如果需要修改语音邮件重新路由设置，请使用 cmdlet **Set-CsVoicemailReroutingConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="8e24b-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="8e24b-114">在 Lync Server 命令行管理程序中，运行 cmdlet **get-csuser**移动家庭用户。</span><span class="sxs-lookup"><span data-stu-id="8e24b-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e24b-115">您还可以使用 Lync Server 控制面板验证先决条件和家庭用户。</span><span class="sxs-lookup"><span data-stu-id="8e24b-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8e24b-116">驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。</span><span class="sxs-lookup"><span data-stu-id="8e24b-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e24b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e24b-117">See Also</span></span>


[<span data-ttu-id="8e24b-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="8e24b-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="8e24b-119">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="8e24b-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="8e24b-120">CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8e24b-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="8e24b-121">移动-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="8e24b-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

