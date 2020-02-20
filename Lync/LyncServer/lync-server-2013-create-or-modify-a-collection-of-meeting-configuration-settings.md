---
title: 创建或修改会议配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7aa5b-102">在 Lync Server 2013 中创建或修改会议配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="7aa5b-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa5b-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7aa5b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7aa5b-104">您可以使用 "会议配置" 页上的设置来定义会议加入体验的各种特征。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="7aa5b-105">默认情况下，全局设置定义加入体验。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="7aa5b-106">还可以创建站点级别和池级别的与会设置。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="7aa5b-107">如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="7aa5b-108">如果未创建池级别的设置，则应用站点级别的设置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="7aa5b-109">如果未定义站点级别的设置，则全局设置将应用于所有会议。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="7aa5b-110">创建新的与会设置</span><span class="sxs-lookup"><span data-stu-id="7aa5b-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="7aa5b-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7aa5b-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7aa5b-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7aa5b-114">在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="7aa5b-115">在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7aa5b-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7aa5b-p103">要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7aa5b-p104">要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="7aa5b-p105">要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除 **“PSTN 呼叫者绕过会议厅”** 复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="7aa5b-124">要配置会议的演示者，请在 **“指定为演示者”** 中执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7aa5b-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="7aa5b-125">要禁止组织者以外的任何人成为演示者，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="7aa5b-p106">要只允许组织成员参与者成为演示者，请单击 **“公司”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="7aa5b-128">要允许任何参与者成为演示者，请单击 **“所有人”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="7aa5b-p107">要让组织者在安排会议时选择会议类型，请清除 **“默认分配的会议类型”** 复选框。默认情况下，会自动分配会议类型。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="7aa5b-p108">要阻止自动允许匿名（未经身份验证）用户参加会议，请清除 **“默认允许匿名用户”** 复选框。默认情况下，自动允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="7aa5b-133">若要自定义发送给参与者的会议邀请，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="7aa5b-134">请注意，Url 和自定义页脚文本的最大长度为1KB。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="7aa5b-135">除 "**帮助 URL**" 外，如果不指定自定义项的值，则不会将其包含在会议中。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="7aa5b-136">如果不包含自定义帮助 URL，则会在邀请中显示 Lync 的默认帮助 URL。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="7aa5b-137">若要自定义会议邀请中显示的徽标，请在 "**徽标 URL**" 中输入徽标的位置。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="7aa5b-138">徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="7aa5b-139">若要自定义会议邀请中显示的帮助文本，请在 "**帮助 URL**" 中输入帮助文本的位置。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="7aa5b-140">若要自定义会议邀请中显示的法律文本，请在 "**合法文本 URL**" 中输入法律文本的位置。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="7aa5b-141">若要自定义会议邀请中显示的页脚文本，请在 "**自定义页脚文本**" 中，输入文本。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="7aa5b-142">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="7aa5b-143">修改现有会议配置集合</span><span class="sxs-lookup"><span data-stu-id="7aa5b-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="7aa5b-144">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7aa5b-145">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7aa5b-146">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7aa5b-147">在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="7aa5b-148">在会议配置列表中，单击要更改的配置，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7aa5b-149">在 "**编辑会议配置**" 中，修改任何配置设置（无法修改的配置名称除外）。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="7aa5b-150">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7aa5b-151">使用 Windows PowerShell Cmdlet 创建新的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="7aa5b-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7aa5b-152">可以使用 Windows PowerShell 和 Get-csmeetingconfiguration cmdlet 创建会议配置设置（仅限在网站范围内）。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="7aa5b-153">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7aa5b-154">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="7aa5b-155">创建使用默认值的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="7aa5b-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="7aa5b-156">此命令将为 Redmond 站点创建一组新的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="7aa5b-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="7aa5b-157">由于前面的命令中未指定任何参数（必需的 Identity 参数），因此新的会议配置设置将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="7aa5b-158">在创建会议配置设置时更改属性值</span><span class="sxs-lookup"><span data-stu-id="7aa5b-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="7aa5b-159">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-159">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="7aa5b-160">例如，若要创建会议配置设置的集合，默认情况下，默认情况下，允许每个人都将会议作为演示者使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="7aa5b-160">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="7aa5b-161">创建会议配置设置时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="7aa5b-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="7aa5b-162">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="7aa5b-163">例如，此命令 admits 每个人作为演示者加入会议，同时还强制 PSTN 用户在大厅中等待，直到他们正式获准参加会议：</span><span class="sxs-lookup"><span data-stu-id="7aa5b-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="7aa5b-164">有关详细信息，请参阅[get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

