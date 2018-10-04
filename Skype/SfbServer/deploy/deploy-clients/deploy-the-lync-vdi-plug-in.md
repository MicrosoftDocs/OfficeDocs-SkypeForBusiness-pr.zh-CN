---
title: 部署 Lync VDI 插件与 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主题讨论 for Business 连接到远程虚拟桌面时使用 Skype 的部署过程。
ms.openlocfilehash: 08f676632e11c4bf95beee9b97be03703978a4a6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373342"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="f9c1c-103">部署 Lync VDI 插件与 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f9c1c-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="f9c1c-104">本主题讨论 for Business 连接到远程虚拟桌面时使用 Skype 的部署过程。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="f9c1c-105">[规划在 VDI 环境中的业务的 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)位于规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="f9c1c-106">某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f9c1c-107">这些组织的用户驻留在本地 Windows 计算机上并使用虚拟桌面上的客户端。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f9c1c-108">使用 Skype for Business 连接这样需要其他 VDI 插件软件。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f9c1c-109">有两个解决方案一个提供 Microsoft 和 Citrix 提供一个可用于 VDI 插件组件-。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f9c1c-110">Microsoft 建议在新部署中使用新的 HDX 实时 Optimization Pack 解决方案，但将继续支持生命周期的其余部分的原始 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f9c1c-111">本主题提供有关部署 Microsoft Lync VDI 插件，它在 Windows 7 和 Windows 8 或 Windows Server 2008，才支持并仅支持业务客户端的 Lync 2013 或 Skype 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="f9c1c-112">没有计划更新此插件，但根据需要将会更新 for Business 的 Skype [Citrix HDX 实时 Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f9c1c-113">针对 Lync VDI 插件准备你的环境</span><span class="sxs-lookup"><span data-stu-id="f9c1c-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f9c1c-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c1c-114"></span></span>

1. <span data-ttu-id="f9c1c-115">中的 Business Server Skype，确保针对所有 Lync VDI 插件用户将 EnableMediaRedirection 设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f9c1c-116">有关详细信息，请参阅[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f9c1c-117">在数据中心服务器上，安装在所有虚拟机上的业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f9c1c-118">在本地计算机上安装 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f9c1c-119">现在，用户应将诸如耳机或网络摄像机等设备连接到其本地计算机。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f9c1c-120">配置远程桌面连接设置</span><span class="sxs-lookup"><span data-stu-id="f9c1c-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f9c1c-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c1c-121"></span></span>

<span data-ttu-id="f9c1c-122">要为 Lync VDI 插件准备远程桌面连接，请在本地计算机上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f9c1c-123">如果本地计算机正在运行 Windows 8，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f9c1c-124">如果本地计算机运行的 Windows 7 SP1，安装[远程桌面服务客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)的最新 Windows 8 版本。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f9c1c-125">通过单击“**开始**”，然后单击“**远程桌面连接**”，启动远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f9c1c-126">单击“**选项**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="f9c1c-127">单击“**本地资源**”选项卡。在“**远程音频**”下，单击“**设置**”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="f9c1c-128">在“**远程音频播放**”下，选择“**在此计算机上播放**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="f9c1c-129">在“**远程音频录制**”下，选择“**不录制**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="f9c1c-130">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="f9c1c-131">单击“**体验**”选项卡。在“**性能**”下，清除“**持久位图缓存**”复选框。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f9c1c-132">单击“**常规**”选项卡。在“**计算机**”中，键入虚拟桌面的名称，然后单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f9c1c-133">登录到和使用虚拟桌面上的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f9c1c-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f9c1c-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c1c-134"></span></span>

<span data-ttu-id="f9c1c-135">启用 Lync VDI 插件后，用户在虚拟桌面上登录到 for Business 的 Skype 时遵循这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f9c1c-136">在用户键入他/她凭据在虚拟机上运行的业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f9c1c-137">Skype for Business 检测 Lync VDI 插件后，for Business 的 Skype 提示用户重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f9c1c-138">在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f9c1c-139">Skype for Business 开始使用 Lync VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f9c1c-140">时出现这种情况，客户端中的业务状态栏 Skype 显示两个图标。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="f9c1c-141">左下角的图标指示有无音频设备，并且的右下角的闪烁图标指示 VDI 配对正在：。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="f9c1c-142">VDI 配对成功后，图标更改为分别指示将用于呼叫和 VDI 配对成功的音频设备： b。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="f9c1c-143">用户现在可以看到他/她状态 Skype 上的业务兼容设备的连接到本地计算机，并进行呼叫和应答像往常一样。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f9c1c-144">Lync VDI 插件故障排除</span><span class="sxs-lookup"><span data-stu-id="f9c1c-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f9c1c-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c1c-145"></span></span>

<span data-ttu-id="f9c1c-146">如果在安装 Lync VDI 插件后遇到问题，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f9c1c-147">安装 Lync VDI 插件时出现问题 </span><span class="sxs-lookup"><span data-stu-id="f9c1c-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f9c1c-148">如果安装 Lync VDI 插件的问题，检查以下项目：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f9c1c-149">确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f9c1c-150">确保已关闭写保护。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f9c1c-151">请参阅设备制造商的文档的说明。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f9c1c-152">排除在配对时出现的问题</span><span class="sxs-lookup"><span data-stu-id="f9c1c-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f9c1c-153">当 Lync VDI 插件配对失败时，较低的右侧显示为红色"X"，显示的配对图标：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f9c1c-154">以下是可能的失败原因以及可以采取的更正措施。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f9c1c-155">**用户在登录期间输入的凭据不正确。**</span><span class="sxs-lookup"><span data-stu-id="f9c1c-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f9c1c-156">用户应注销 for Business 的 Skype 并重新登录与正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f9c1c-157">配对对话框将重新出现，并显示配对是否成功。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f9c1c-158">**远程桌面客户端的另一个实例正在运行。**</span><span class="sxs-lookup"><span data-stu-id="f9c1c-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f9c1c-159">如果他们在 Windows 中使用远程桌面连接，用户应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f9c1c-160">启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f9c1c-161">单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f9c1c-162">突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f9c1c-163">启动新的远程桌面会话并再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f9c1c-164">**未正确安装必要的文件。**</span><span class="sxs-lookup"><span data-stu-id="f9c1c-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f9c1c-165">在本地计算机上安装插件后，请进行检查，确保 C:\Program Files\Microsoft Office\Office15（或相应的驱动器号）下应存在以下文件：</span><span class="sxs-lookup"><span data-stu-id="f9c1c-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f9c1c-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f9c1c-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f9c1c-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f9c1c-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="f9c1c-168">**业务客户端 Skype 本地计算机上运行。**</span><span class="sxs-lookup"><span data-stu-id="f9c1c-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f9c1c-169">若要使用 Lync VDI 插件，不能在本地计算机上运行业务客户端 Skype，否则配对将失败。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f9c1c-170">作为最佳实践，用户不应安装业务客户端 Skype 本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="f9c1c-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f9c1c-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9c1c-171">See also</span></span>
<span data-ttu-id="f9c1c-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f9c1c-172"></span></span>

[<span data-ttu-id="f9c1c-173">在 VDI 环境中规划 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f9c1c-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)