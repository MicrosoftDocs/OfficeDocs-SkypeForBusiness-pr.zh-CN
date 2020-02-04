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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ff082-102">在 Lync Server 2013 中创建或修改会议配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="ff082-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff082-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ff082-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ff082-104">你可以使用会议配置页面上的设置来定义会议加入体验的各种特征。</span><span class="sxs-lookup"><span data-stu-id="ff082-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="ff082-105">默认情况下，全局设置定义连接体验。</span><span class="sxs-lookup"><span data-stu-id="ff082-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="ff082-106">您还可以创建网站级和池级会议联接设置。</span><span class="sxs-lookup"><span data-stu-id="ff082-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="ff082-107">如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。</span><span class="sxs-lookup"><span data-stu-id="ff082-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="ff082-108">如果未创建池级别的设置，则应用站点级别的设置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="ff082-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="ff082-109">如果未定义站点级别的设置，则全局设置将应用于所有会议。</span><span class="sxs-lookup"><span data-stu-id="ff082-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="ff082-110">创建新的会议加入设置</span><span class="sxs-lookup"><span data-stu-id="ff082-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="ff082-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ff082-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff082-112">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ff082-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff082-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ff082-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff082-114">在左侧导航栏中，单击 "**会议**"，然后单击 "**会议配置**"。</span><span class="sxs-lookup"><span data-stu-id="ff082-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="ff082-115">在“**会议配置**”页上，单击“**新建**”，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ff082-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ff082-p103">若要创建站点级别的策略，请单击“**站点配置**”。在“**选择站点**”搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ff082-p104">若要创建池级别的策略，请单击“**池配置**”。在“**选择服务**”搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="ff082-p105">若要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除“**PSTN 呼叫者绕过休息室**”复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。</span><span class="sxs-lookup"><span data-stu-id="ff082-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="ff082-124">若要配置会议的演示者，请在“**指定为演示者**”中执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ff082-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="ff082-125">若要禁止组织者以外的任何人成为演示者，请单击“**无**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="ff082-p106">若要只允许属于组织成员的参与者成为演示者，请单击“**公司**”。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ff082-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="ff082-128">若要允许任何参与者成为演示者，请单击“**所有人**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="ff082-p107">若要让组织者在安排会议时选择会议类型，请清除“**默认分配的会议类型**”复选框。默认情况下，会自动分配会议类型。</span><span class="sxs-lookup"><span data-stu-id="ff082-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="ff082-p108">若要阻止自动允许匿名（未经身份验证）用户参加会议，请清除“**默认允许匿名用户**”复选框。默认情况下，自动允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="ff082-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="ff082-133">若要自定义发送给参与者的会议邀请，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="ff082-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="ff082-134">请注意，URL 和自定义页脚文本的最大长度为 1KB。</span><span class="sxs-lookup"><span data-stu-id="ff082-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="ff082-135">除了“**帮助 URL**”外，如果不指定自定义的值，则它们不会包括在会议中。</span><span class="sxs-lookup"><span data-stu-id="ff082-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="ff082-136">如果不包含自定义帮助 URL，则会在邀请中显示 Lync 的默认帮助 URL。</span><span class="sxs-lookup"><span data-stu-id="ff082-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="ff082-137">若要自定义会议邀请中显示的徽标，请在“**徽标 URL**”中输入徽标的位置。</span><span class="sxs-lookup"><span data-stu-id="ff082-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="ff082-138">徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。</span><span class="sxs-lookup"><span data-stu-id="ff082-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="ff082-139">若要自定义会议邀请中显示的帮助文本，请在“**帮助 URL**”中输入帮助文本的位置。</span><span class="sxs-lookup"><span data-stu-id="ff082-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="ff082-140">若要自定义会议邀请中显示的法律文本，请在“**法律文本 URL**”中输入法律文本的位置。</span><span class="sxs-lookup"><span data-stu-id="ff082-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="ff082-141">若要自定义会议邀请中显示的页脚文本，请在“**自定义页脚文本**”中输入文本。</span><span class="sxs-lookup"><span data-stu-id="ff082-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="ff082-142">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="ff082-143">修改现有会议配置集合</span><span class="sxs-lookup"><span data-stu-id="ff082-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="ff082-144">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ff082-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff082-145">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ff082-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff082-146">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ff082-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff082-147">在左侧导航栏中，单击 "**会议**"，然后单击 "**会议配置**"。</span><span class="sxs-lookup"><span data-stu-id="ff082-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="ff082-148">在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ff082-149">在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。</span><span class="sxs-lookup"><span data-stu-id="ff082-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="ff082-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ff082-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff082-151">使用 Windows PowerShell Cmdlet 创建新会议配置设置</span><span class="sxs-lookup"><span data-stu-id="ff082-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff082-152">可以使用 Windows PowerShell 和 CsMeetingConfiguration cmdlet 创建会议配置设置（仅限在网站范围内）。</span><span class="sxs-lookup"><span data-stu-id="ff082-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="ff082-153">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="ff082-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ff082-154">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="ff082-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="ff082-155">创建使用默认值的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="ff082-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="ff082-156">此命令为 Redmond 网站创建一组新的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="ff082-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="ff082-157">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的会议配置设置的所有属性将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="ff082-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="ff082-158">在创建会议配置设置时更改属性值</span><span class="sxs-lookup"><span data-stu-id="ff082-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="ff082-p112">要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建在默认情况下允许所有人以演示者身份加入会议的会议配置设置集合，请使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="ff082-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="ff082-161">创建会议配置设置时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="ff082-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="ff082-162">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="ff082-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="ff082-163">例如，此命令将准许每个人作为演示者加入会议，并且还强制 PSTN 用户在大厅中等待，直到他们正式获准参加会议：</span><span class="sxs-lookup"><span data-stu-id="ff082-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="ff082-164">有关详细信息，请参阅[CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="ff082-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

