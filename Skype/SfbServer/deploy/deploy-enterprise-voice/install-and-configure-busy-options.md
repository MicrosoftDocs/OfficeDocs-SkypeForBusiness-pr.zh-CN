---
title: 为 Skype for Business Server 安装和配置忙碌选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 阅读有关如何在 Skype for Business Server 中安装和配置忙碌选项的信息。
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604209"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="4942b-103">为 Skype for Business Server 安装和配置忙碌选项</span><span class="sxs-lookup"><span data-stu-id="4942b-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="4942b-104">阅读有关如何在 Skype for Business Server 中安装和配置忙碌选项的信息。</span><span class="sxs-lookup"><span data-stu-id="4942b-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="4942b-105">"忙碌选项" 是在2016累积更新中引入的新语音策略，允许您配置当用户已在通话或会议中，或具有处于保留状态的呼叫时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4942b-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="4942b-106">可以使用占线信号拒绝新的或传入的呼叫，或将其转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="4942b-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="4942b-107">如果为组织启用忙碌选项，企业中的所有用户（企业语音用户和非企业语音用户）都可以使用以下配置选项：</span><span class="sxs-lookup"><span data-stu-id="4942b-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="4942b-108">占线-如果用户忙碌，将使用占线信号拒绝新的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4942b-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="4942b-109">占线中的语音邮件-如果用户忙碌，将向语音邮件转发新的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4942b-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="4942b-110">无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或呼叫处于保留状态的用户发起新呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="4942b-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="4942b-111">有关忙碌选项功能的详细信息，请参阅[Plan For Busy options For Skype For Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4942b-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="4942b-112">安装</span><span class="sxs-lookup"><span data-stu-id="4942b-112">Install</span></span>

<span data-ttu-id="4942b-113">请确保已安装最新版本的 Skype for Business Server，并且已安装最新的修补程序。</span><span class="sxs-lookup"><span data-stu-id="4942b-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="4942b-114">若要执行此操作，请先停止所有服务，然后运行 Skype for Business Server 更新安装程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="4942b-115">运行 Start-cswindowsservice 命令。</span><span class="sxs-lookup"><span data-stu-id="4942b-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="4942b-116">在池中的每台前端服务器上运行 Skypeserverupdateinstaller.exe 安装程序。</span><span class="sxs-lookup"><span data-stu-id="4942b-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="4942b-117">如果要确保在 SBS 上支持故障转移，请在每个 Survivable 分支服务器（SBS）上运行 Skypeserverupdateinstaller.exe 安装程序。</span><span class="sxs-lookup"><span data-stu-id="4942b-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="4942b-118">安装程序将部署最新版本的 Busy Options 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4942b-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="4942b-119">但是，默认情况下不会启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="4942b-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="4942b-120">若要启用该应用程序，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4942b-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="4942b-121">运行[set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 以全局启用忙碌选项，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="4942b-122">接下来，如果网站有语音策略，则必须为语音策略启用忙碌选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="4942b-123">首先，运行[get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)以检索网站的名称：</span><span class="sxs-lookup"><span data-stu-id="4942b-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="4942b-124">使用从 Get-cssite 检索到的标识值（例如： Site： Redmond1）来检索网站的语音策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="4942b-125">如果网站存在语音策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4942b-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="4942b-126">接下来，运行[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 以将忙碌选项添加到服务器应用程序列表中，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="4942b-127">您必须将% FQDN% 替换为特定池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="4942b-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="4942b-128">接下来，运行[CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 以更新 "忙碌选项" cmdlet 的基于角色的访问控制（RBAC）角色，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="4942b-129">最后，在通过运行[start-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)命令安装和启用忙碌选项的所有池的所有前端服务器上启动 Skype For Business Server Windows 服务：</span><span class="sxs-lookup"><span data-stu-id="4942b-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="4942b-130">配置</span><span class="sxs-lookup"><span data-stu-id="4942b-130">Configure</span></span>

<span data-ttu-id="4942b-131">若要配置忙碌选项，请使用[set-csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4942b-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="4942b-132">例如，以下命令配置用户 "Ken Myer" 的忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="4942b-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="4942b-133">在此配置中，对 "Ken Myer" 的任何调用将在他已处于呼叫中时返回一个占线信号：</span><span class="sxs-lookup"><span data-stu-id="4942b-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="4942b-134">在下一个示例中，该命令将为用户 "Chrystal Velasquez" 配置忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="4942b-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="4942b-135">在此配置中，当她已经在呼叫中时，会将对 "Chrystal Velasquez" 的新传入呼叫转发到语音邮件：</span><span class="sxs-lookup"><span data-stu-id="4942b-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="4942b-136">您可以使用[set-csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙碌选项的配置信息。</span><span class="sxs-lookup"><span data-stu-id="4942b-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="4942b-137">下面的示例返回 "KenMyer@Contoso.com" 的 "忙碌选项" 设置：</span><span class="sxs-lookup"><span data-stu-id="4942b-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="4942b-138">您可以使用[set-csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Cmdlet 删除忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="4942b-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="4942b-139">以下命令将删除 "Ken Myer" 的忙碌选项：</span><span class="sxs-lookup"><span data-stu-id="4942b-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="4942b-140">有关用于配置忙碌选项的 cmdlet 的详细信息，请参阅 " [set-csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)"、" [set-csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" 和 " [set-csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)" 的技术参考内容。</span><span class="sxs-lookup"><span data-stu-id="4942b-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="4942b-141">启用日志记录</span><span class="sxs-lookup"><span data-stu-id="4942b-141">Enable logging</span></span>

<span data-ttu-id="4942b-142">若要使用集中日志记录服务启用忙碌选项的日志记录，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="4942b-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="4942b-143">验证和故障排除</span><span class="sxs-lookup"><span data-stu-id="4942b-143">Verify and troubleshoot</span></span>

<span data-ttu-id="4942b-144">安装忙碌选项后，可以使用[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序的列表，以验证安装是否成功。</span><span class="sxs-lookup"><span data-stu-id="4942b-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="4942b-145">如果忙选项安装正确，则 cmdlet 的输出应显示 "忙碌选项" 配置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4942b-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="4942b-146">您还可以使用 Windows 事件查看器来验证 "忙碌" 选项安装是否成功，以及 Skype for Business Server 是否已成功加载 "忙碌" 选项。</span><span class="sxs-lookup"><span data-stu-id="4942b-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="4942b-147">若要验证忙碌选项，请打开 "**事件查看器-\>应用\>程序和服务日志-Skype （或 Lync）服务器**"，然后搜索事件 ID = 30253。</span><span class="sxs-lookup"><span data-stu-id="4942b-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
