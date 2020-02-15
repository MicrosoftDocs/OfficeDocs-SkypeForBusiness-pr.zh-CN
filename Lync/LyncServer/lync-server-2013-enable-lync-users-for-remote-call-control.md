---
title: Lync Server 2013：为 Lync 用户启用远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baa6f18e92eb284cce8610ba576b30dd6d2f320
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="c2e85-102">在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="c2e85-102">Enable Lync users for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2e85-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c2e85-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c2e85-104">您可以使用基于服务器的带内设置策略为 Lync 用户配置远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="c2e85-104">You can configure Lync users for remote call control by using in-band provisioning policies that are server-based.</span></span> <span data-ttu-id="c2e85-105">您可以通过使用 Lync Server 控制面板或 Lync Server Management Shell 命令行界面来管理带内配置设置。</span><span class="sxs-lookup"><span data-stu-id="c2e85-105">You can manage in-band provisioning settings by using Lync Server Control Panel or the Lync Server Management Shell command-line interface.</span></span> <span data-ttu-id="c2e85-106">这些工具将替换用于在早期版本中管理组策略设置的 Windows Management Instrumentation （WMI）管理单元。</span><span class="sxs-lookup"><span data-stu-id="c2e85-106">These tools replace the Windows Management Instrumentation (WMI) snap-in that was used to manage Group Policy settings in earlier releases.</span></span>

<span data-ttu-id="c2e85-107">如果你想让用户在 Lync 中配置其自己的远程呼叫控制设置，可以在不指定**行服务器 URI**和**线路 URI**值的情况下为服务器上的用户配置远程呼叫控制设置。</span><span class="sxs-lookup"><span data-stu-id="c2e85-107">If you prefer to let users to configure their own remote call control settings in Lync, you can configure remote call control settings for users on the server without specifying **Line Server URI** and **Line URI** values.</span></span> <span data-ttu-id="c2e85-108">确保将适当的**行服务器 URI**和**行 URI**值传递给用户，并向用户提供有关配置这些设置的说明。</span><span class="sxs-lookup"><span data-stu-id="c2e85-108">Be sure that you communicate the appropriate **Line Server URI** and **Line URI** values to your users, and provide your users with the instructions to configure these settings.</span></span> <span data-ttu-id="c2e85-109">有关在 Lync Server 中手动配置远程呼叫控制的过程，请参阅 Microsoft Office 网站上的 Lync 客户<http://go.microsoft.com/fwlink/p/?linkid=210132>端文档中的 "设置电话选项和号码"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-109">For the procedure to manually configure remote call control in Lync Server, see "Set Phones options and numbers" at <http://go.microsoft.com/fwlink/p/?linkid=210132> in the Lync client documentation on the Microsoft Office website.</span></span>

<span data-ttu-id="c2e85-110">如果您有一个现有的通信服务器 2007 R2 或通信服务器2007部署，Communicator 2007 R2 和 Communicator 2007 客户端将继续在并行迁移过程中使用组策略。</span><span class="sxs-lookup"><span data-stu-id="c2e85-110">If you have an existing Communications Server 2007 R2 or Communications Server 2007 deployment, Communicator 2007 R2 and Communicator 2007 clients will continue to use Group Policy during side-by-side migration.</span></span> <span data-ttu-id="c2e85-111">但是，如果您希望将策略设置传输到 Lync 客户端，则需要配置等效的 Lync Server 带内设置设置。</span><span class="sxs-lookup"><span data-stu-id="c2e85-111">However, if you want policy settings to carry over to Lync clients, you need to configure the equivalent Lync Server in-band provisioning settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2e85-112">若要为用户启用远程呼叫控制，您需要为用户提供线路 URI 和行服务器 URI。</span><span class="sxs-lookup"><span data-stu-id="c2e85-112">To enable a user for remote call control, you need to provide the user with both a Line URI and a Line Server URI.</span></span> <span data-ttu-id="c2e85-113">如<A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 中的远程呼叫控制的部署任务</A>中所述，您需要确保使用网关对这些设置所需的语法。</span><span class="sxs-lookup"><span data-stu-id="c2e85-113">As described in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Deployment tasks for remote call control in Lync Server 2013</A>, you need to be sure to use the syntax that is required by the gateway for these settings.</span></span><BR><span data-ttu-id="c2e85-114">在将静态路由配置为网关时，请确保行服务器 URI 中的域与您在 MatchUri 参数中指定的目标域相同。</span><span class="sxs-lookup"><span data-stu-id="c2e85-114">Be sure that the domain in the Line Server URI is the same as the destination domain that you specified in the MatchUri parameter when you configured the static route to the gateway.</span></span><BR><span data-ttu-id="c2e85-115">线路 URI 以 e.164 格式指定分配给用户的电话号码，带有 "电话：" 前缀（例如电话： + 14255550150）。</span><span class="sxs-lookup"><span data-stu-id="c2e85-115">The Line URI specifies the phone number assigned to the user in E.164 format, with the "TEL:" prefix (for example, tel:+14255550150).</span></span> <span data-ttu-id="c2e85-116">如果要配置分机号，则格式为 tel:+14255550150;ext=111。</span><span class="sxs-lookup"><span data-stu-id="c2e85-116">If you want to configure an extension number, then the format is tel:+14255550150;ext=111.</span></span> <span data-ttu-id="c2e85-117">如果您之前已配置用户的“线路 URI”，且未更改其值，则在为用户启用远程呼叫控制时，不需要指定“线路 URI”。</span><span class="sxs-lookup"><span data-stu-id="c2e85-117">If you previously configured the user’s Line URI and the value has not changed, you do not need to specify the Line URI when you enable the user for remote call control.</span></span>



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a><span data-ttu-id="c2e85-118">使用命令行管理程序为启用了 Lync 的用户启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="c2e85-118">To enable remote call control for Lync-enabled users by using Management Shell</span></span>

1.  <span data-ttu-id="c2e85-119">登录到安装了 Lync Server 命令行管理程序的计算机上作为 RTCUniversalServerAdmins 组的成员，或者作为已为其分配**get-csuser** cmdlet 的基于角色的访问控制角色。</span><span class="sxs-lookup"><span data-stu-id="c2e85-119">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or as a role-based access control role to which you have assigned the **Set-CsUser** cmdlet.</span></span>

2.  <span data-ttu-id="c2e85-120">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2e85-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c2e85-121">要使用 **Set-CsUser** cmdlet 为已启用 Lync 的现有用户配置远程呼叫控制，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c2e85-121">To use the **Set-CsUser** cmdlet to configure remote call control for an existing Lync-enabled user, do the following:</span></span>
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    <span data-ttu-id="c2e85-122">例如：</span><span class="sxs-lookup"><span data-stu-id="c2e85-122">For example:</span></span>
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a><span data-ttu-id="c2e85-123">使用 Lync Server 控制面板为用户配置远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="c2e85-123">To configure users for remote call control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c2e85-124">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c2e85-124">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2e85-125">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2e85-126">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2e85-127">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2e85-127">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c2e85-128">在 "**搜索用户**" 框中，键入所需用户帐户的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名、SIP 地址或线路统一资源标识符（URI）的全部（或第一部分），然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-128">In the **Search users** box, type all (or the first portion) of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="c2e85-129">在表中，单击要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c2e85-129">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="c2e85-130">在 **“编辑”** 菜单上，单击 **“修改”**。</span><span class="sxs-lookup"><span data-stu-id="c2e85-130">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="c2e85-131">在 **“电话”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c2e85-131">In **Telephony**, do one of the following:</span></span>
    
      - <span data-ttu-id="c2e85-132">若要启用远程呼叫控制以使用户能够通过 Lync 2013 控制其专用交换机（PBX）电话，以进行 PC 到 PC 的音频呼叫和 PC 到电话呼叫，请单击 "**远程呼叫控制**"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-132">To enable remote call control to enable the user to control their private branch exchange (PBX) phone from Lync 2013 to make PC-to-PC audio calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="c2e85-133">在 **“线路 URI”** 中，指定用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c2e85-133">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="c2e85-134">在 **“线路服务器 URI”** 中，指定 SIP/CSTA 网关的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c2e85-134">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>
    
      - <span data-ttu-id="c2e85-135">若要启用远程呼叫控制，但禁用 PC 到 PC 音频呼叫，并且仅允许用户从 Lync 2013 控制其 PBX 电话以进行 PC 到电话呼叫，请单击 "**仅远程呼叫控制**"。</span><span class="sxs-lookup"><span data-stu-id="c2e85-135">To enable remote call control, but disable PC-to-PC audio calls, and to enable only the user to control their PBX phone from Lync 2013 to make PC-to-phone calls, click **Remote call control only**.</span></span> <span data-ttu-id="c2e85-136">在 **“线路 URI”** 中，指定用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c2e85-136">In **Line URI**, specify the telephone number of the user.</span></span> <span data-ttu-id="c2e85-137">在 **“线路服务器 URI”** 中，指定 SIP/CSTA 网关的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c2e85-137">In **Line Server URI**, specify the SIP URI of the SIP/CSTA gateway.</span></span>

8.  <span data-ttu-id="c2e85-138">完成后，单击 **“提交”**。</span><span class="sxs-lookup"><span data-stu-id="c2e85-138">When you are finished, click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

