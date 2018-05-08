---
title: 安装和配置适用于 Skype for Business Server 的忙碌选项
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/6/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 阅读有关如何安装和配置忙选项中 Skype 业务服务器 2015年。
ms.openlocfilehash: ff0f9a892d0882adcc2af0c4c41c1177b3488520
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="d1ba5-103">安装和配置适用于 Skype for Business Server 的忙碌选项</span><span class="sxs-lookup"><span data-stu-id="d1ba5-103">Install and configure Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="d1ba5-104">阅读有关如何安装和配置忙选项中 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-104">Read about how to install and configure Busy Options in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d1ba5-105">忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="d1ba5-106">可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="d1ba5-107">如果已为组织启用忙碌选项，则企业中的所有用户（企业语音用户和非企业语音用户）都可以使用以下配置选项：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>
  
- <span data-ttu-id="d1ba5-108">Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="d1ba5-109">Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="d1ba5-110">无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。  </span><span class="sxs-lookup"><span data-stu-id="d1ba5-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="d1ba5-111">有关的忙选项功能的详细信息，请参阅[Plan for Business Server 的 Skype 忙选项](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>
  
## <a name="install"></a><span data-ttu-id="d1ba5-112">安装 </span><span class="sxs-lookup"><span data-stu-id="d1ba5-112">Install</span></span>

<span data-ttu-id="d1ba5-113">确保已安装的业务服务器 Skype 的最新版本，并且您已安装最新的修补程序。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="d1ba5-114">若要执行此操作，先停止所有服务，然后运行 Skype 的业务服务器更新安装程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>
  
1. <span data-ttu-id="d1ba5-115">运行 Stop-CsWindowsService 命令。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-115">Run the Stop-CsWindowsService command.</span></span>
    
2. <span data-ttu-id="d1ba5-116">在池中的每台前端服务器上运行 SkypeServerUpdateInstaller.exe 安装程序。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>
    
3. <span data-ttu-id="d1ba5-117">在每个 Survivable Branch Server (SBS) 上运行 SkypeServerUpdateInstaller.exe 安装程序（如果要确保支持在 SBS 上进行故障转移）。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>
    
<span data-ttu-id="d1ba5-p103">安装程序将部署最新版本的忙碌选项应用程序。但是，该应用程序默认情况下不启用。要启用该应用程序，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>
  
1. <span data-ttu-id="d1ba5-121">运行[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 来全局启用忙选项，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>
    
  ```
  Set-CsVoicePolicy -EnableBusyOptions $true
  ```

2. <span data-ttu-id="d1ba5-122">接下来，如果站点具备语音策略，则必须按如下所示为该语音策略启用忙碌选项：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>
    
    <span data-ttu-id="d1ba5-123">首先，运行[Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)检索网站的名称：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>
    
   ```
   Get-CsSite
   ```

    <span data-ttu-id="d1ba5-124">使用 Identity 值 (例如： 网站： Redmond1) 检索从 Get-cssite 检索网站的语音策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>
    
   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="d1ba5-125">如果站点存在语音策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-125">If a voice policy exists for the site, run the following command:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="d1ba5-126">接下来，运行[新建 CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 将忙选项添加到下面的示例中所示的服务器应用程序的列表：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="d1ba5-127">您必须使用特定池的完全限定域名替换 %FQDN%。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span> 
  
4. <span data-ttu-id="d1ba5-128">接下来，运行[Update-csadminrole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 更新下面的示例中所示的忙选项 cmdlet 的基于角色的访问控制 (RBAC) 角色：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>
    
   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="d1ba5-129">最后，其中忙选项已安装并启用通过运行[Start-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)命令的所有池的所有前端服务器上启动业务 Windows 服务器服务的 Skype:</span><span class="sxs-lookup"><span data-stu-id="d1ba5-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>
    
   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="d1ba5-130">配置</span><span class="sxs-lookup"><span data-stu-id="d1ba5-130">Configure</span></span>

<span data-ttu-id="d1ba5-131">若要配置忙选项，请使用[集 CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-131">To configure Busy Options, use the [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>
  
<span data-ttu-id="d1ba5-p104">例如，以下命令可配置用户“Ken Myer”的忙碌选项。在此配置中，当“Ken Myer”已接听电话时，向其发起的任何呼叫都将返回忙音：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>
  
```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy

```

<span data-ttu-id="d1ba5-134">在下一个示例中，该命令可配置用户“Chrystal Velasquez”的忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="d1ba5-135">在此配置中，当“Chrystal Velasquez”已接听电话时，向其发起的新传入呼叫都将转接到语言邮件。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>
  
```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy 

```

<span data-ttu-id="d1ba5-136">您可以通过使用[Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙选项的配置信息。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="d1ba5-137">以下示例返回"KenMyer@Contoso.com"的忙选项设置：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>
  
```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="d1ba5-138">您可以通过使用[删除 CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet 删除忙选项。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-138">You can remove Busy Options by using the [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="d1ba5-139">以下命令将删除“Ken Myer”的忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-139">The following command removes Busy Options for "Ken Myer":</span></span>
  
```
Remove-CsBusyOptions -Identity "Ken Myer"

```

<span data-ttu-id="d1ba5-140">有关 cmdlet 用于配置忙选项的详细信息，请参阅[设置 CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [Get CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)，和[删除 CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技术参考内容。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>
  
## <a name="enable-logging"></a><span data-ttu-id="d1ba5-141">启用日志记录</span><span class="sxs-lookup"><span data-stu-id="d1ba5-141">Enable logging</span></span>

<span data-ttu-id="d1ba5-142">要通过使用集中日志记录服务对忙碌选项启用日志记录，请指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>
  
```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3} 

```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="d1ba5-143">验证和故障排除</span><span class="sxs-lookup"><span data-stu-id="d1ba5-143">Verify and troubleshoot</span></span>

<span data-ttu-id="d1ba5-144">安装后忙选项，可以验证已成功安装使用[Get-csserverapplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="d1ba5-145">如果忙碌选项已正确安装，该 cmdlet 的输出应显示忙碌选项配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1ba5-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1ba5-146">Identity </span><span class="sxs-lookup"><span data-stu-id="d1ba5-146">Identity</span></span>  <br/> | <span data-ttu-id="d1ba5-147"> ：Service:Registrar:pool0.vdomain.com/BusyOptions</span><span class="sxs-lookup"><span data-stu-id="d1ba5-147">: Service:Registrar:pool0.vdomain.com/BusyOptions</span></span> <br/> |
|<span data-ttu-id="d1ba5-148">优先级</span><span class="sxs-lookup"><span data-stu-id="d1ba5-148">Priority</span></span>  <br/> | <span data-ttu-id="d1ba5-149">: 5</span><span class="sxs-lookup"><span data-stu-id="d1ba5-149">: 5</span></span> <br/> |
|<span data-ttu-id="d1ba5-150">Uri </span><span class="sxs-lookup"><span data-stu-id="d1ba5-150">Uri</span></span>  <br/> |<span data-ttu-id="d1ba5-151">: http://www.microsoft.com/LCS/BusyOptions</span><span class="sxs-lookup"><span data-stu-id="d1ba5-151"></span></span>  <br/> |
|<span data-ttu-id="d1ba5-152">名称</span><span class="sxs-lookup"><span data-stu-id="d1ba5-152">Name</span></span>  <br/> | <span data-ttu-id="d1ba5-153"> ：BusyOptions</span><span class="sxs-lookup"><span data-stu-id="d1ba5-153">: BusyOptions</span></span> <br/> |
|<span data-ttu-id="d1ba5-154">已启用</span><span class="sxs-lookup"><span data-stu-id="d1ba5-154">Enabled</span></span>  <br/> |<span data-ttu-id="d1ba5-155">：True</span><span class="sxs-lookup"><span data-stu-id="d1ba5-155">: True</span></span>  <br/> |
|<span data-ttu-id="d1ba5-156">严重</span><span class="sxs-lookup"><span data-stu-id="d1ba5-156">Critical</span></span>  <br/> |<span data-ttu-id="d1ba5-157">：False</span><span class="sxs-lookup"><span data-stu-id="d1ba5-157">: False</span></span>  <br/> |
|<span data-ttu-id="d1ba5-158">ScriptName</span><span class="sxs-lookup"><span data-stu-id="d1ba5-158">ScriptName</span></span>  <br/> | <span data-ttu-id="d1ba5-159">:</span><span class="sxs-lookup"><span data-stu-id="d1ba5-159"></span></span> <br/> |
|<span data-ttu-id="d1ba5-160">脚本 </span><span class="sxs-lookup"><span data-stu-id="d1ba5-160">Script</span></span>  <br/> | <span data-ttu-id="d1ba5-161">:</span><span class="sxs-lookup"><span data-stu-id="d1ba5-161"></span></span> <br/> |
   
<span data-ttu-id="d1ba5-162">您还可以使用 Windows 事件查看器验证忙选项安装成功和 Skype 业务服务器成功加载忙选项。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-162">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="d1ba5-163">若要验证忙选项，请打开**事件查看器-\>应用程序和服务日志-\> Skype （或 Lync） Server** ，然后搜索事件 ID = 30253。</span><span class="sxs-lookup"><span data-stu-id="d1ba5-163">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
  

