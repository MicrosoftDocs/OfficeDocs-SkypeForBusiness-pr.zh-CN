---
title: 在 Skype for Business Server 2015 中部署 Lync VDI 插件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主题讨论 for Business 连接到远程虚拟桌面时使用 Skype 的部署过程。
ms.openlocfilehash: 47491b4409f21386cf28f811b6c2c3cbffe1e69b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501669"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="d3898-103">在 Skype for Business Server 2015 中部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="d3898-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3898-104">本主题讨论 for Business 连接到远程虚拟桌面时使用 Skype 的部署过程。</span><span class="sxs-lookup"><span data-stu-id="d3898-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="d3898-105">某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="d3898-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="d3898-106">这些组织的用户驻留在本地 Windows 计算机上并使用虚拟桌面上的客户端。</span><span class="sxs-lookup"><span data-stu-id="d3898-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="d3898-107">使用 Skype for Business 连接这样需要其他 VDI 插件软件。</span><span class="sxs-lookup"><span data-stu-id="d3898-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="d3898-108">有两个解决方案一个提供 Microsoft 和 Citrix 提供一个可用于 VDI 插件组件-。</span><span class="sxs-lookup"><span data-stu-id="d3898-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="d3898-109">Microsoft 建议在新部署中使用新的 HDX 实时 Optimization Pack 解决方案，但将继续支持生命周期的其余部分的原始 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="d3898-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="d3898-110">本主题提供有关部署 Microsoft Lync VDI 插件，它在 Windows 7 和 Windows 8 或 Windows Server 2008，才支持并仅支持业务 2015年客户端的 Lync 2013 或 Skype 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d3898-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="d3898-111">没有计划更新此插件，但根据需要将会更新 for Business 的 Skype [Citrix HDX 实时 Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 。</span><span class="sxs-lookup"><span data-stu-id="d3898-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="d3898-112">针对 Lync VDI 插件准备你的环境</span><span class="sxs-lookup"><span data-stu-id="d3898-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="d3898-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="d3898-113"></span></span>

1. <span data-ttu-id="d3898-114">中的业务服务器 2015 Skype，确保针对所有 Lync VDI 插件用户将 EnableMediaRedirection 设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d3898-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="d3898-115">有关详细信息，请参阅[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d3898-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="d3898-116">在数据中心服务器上，安装在所有虚拟机上的业务 2015年客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="d3898-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="d3898-117">在本地计算机上安装 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="d3898-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="d3898-118">现在，用户应将诸如耳机或网络摄像机等设备连接到其本地计算机。</span><span class="sxs-lookup"><span data-stu-id="d3898-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="d3898-119">配置远程桌面连接设置</span><span class="sxs-lookup"><span data-stu-id="d3898-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="d3898-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="d3898-120"></span></span>

<span data-ttu-id="d3898-121">要为 Lync VDI 插件准备远程桌面连接，请在本地计算机上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d3898-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="d3898-122">如果本地计算机正在运行 Windows 8，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d3898-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="d3898-123">如果本地计算机运行的 Windows 7 SP1，安装[远程桌面服务客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)的最新 Windows 8 版本。</span><span class="sxs-lookup"><span data-stu-id="d3898-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="d3898-124">通过单击“**开始**”，然后单击“**远程桌面连接**”，启动远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="d3898-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="d3898-125">单击“**选项**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="d3898-126">单击“**本地资源**”选项卡。在“**远程音频**”下，单击“**设置**”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3898-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="d3898-127">在“**远程音频播放**”下，选择“**在此计算机上播放**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="d3898-128">在“**远程音频录制**”下，选择“**不录制**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="d3898-129">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="d3898-130">单击“**体验**”选项卡。在“**性能**”下，清除“**持久位图缓存**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d3898-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="d3898-131">单击“**常规**”选项卡。在“**计算机**”中，键入虚拟桌面的名称，然后单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="d3898-132">登录到和使用虚拟桌面上的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d3898-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="d3898-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="d3898-133"></span></span>

<span data-ttu-id="d3898-134">启用 Lync VDI 插件后，用户在虚拟桌面上登录到业务 2015年的 Skype 时遵循这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d3898-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="d3898-135">在用户键入他/她凭据在虚拟机上运行的业务 2015年客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="d3898-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="d3898-136">Skype 的业务 2015年检测 Lync VDI 插件之后，业务 2015年的 Skype 提示用户重新输入凭据。</span><span class="sxs-lookup"><span data-stu-id="d3898-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="d3898-137">在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。</span><span class="sxs-lookup"><span data-stu-id="d3898-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="d3898-138">Skype 的业务 2015年开始使用 Lync VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="d3898-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="d3898-139">时出现这种情况，客户端中的业务 2015年状态栏 Skype 显示两个图标。</span><span class="sxs-lookup"><span data-stu-id="d3898-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="d3898-140">左下角的图标指示没有可用的音频设备，而右下角的闪烁图标指示 VDI 配对正在进行：</span><span class="sxs-lookup"><span data-stu-id="d3898-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="d3898-141">VDI 配对成功后，这两个图标将更改为分别指示用于呼叫的音频设备和 VDI 配对成功：</span><span class="sxs-lookup"><span data-stu-id="d3898-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="d3898-142">用户现在可以看到他/她状态 Skype 上的业务 2015年兼容设备的连接到本地计算机，并进行呼叫和应答像往常一样。</span><span class="sxs-lookup"><span data-stu-id="d3898-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="d3898-143">Lync VDI 插件故障排除</span><span class="sxs-lookup"><span data-stu-id="d3898-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="d3898-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="d3898-144"></span></span>

<span data-ttu-id="d3898-145">如果在安装 Lync VDI 插件后遇到问题，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="d3898-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="d3898-146">安装 Lync VDI 插件时出现问题 </span><span class="sxs-lookup"><span data-stu-id="d3898-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="d3898-147">如果安装 Lync VDI 插件的问题，检查以下项目：</span><span class="sxs-lookup"><span data-stu-id="d3898-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="d3898-148">确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。</span><span class="sxs-lookup"><span data-stu-id="d3898-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="d3898-149">确保已关闭写保护。</span><span class="sxs-lookup"><span data-stu-id="d3898-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="d3898-150">请参阅设备制造商的文档的说明。</span><span class="sxs-lookup"><span data-stu-id="d3898-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="d3898-151">排除在配对时出现的问题</span><span class="sxs-lookup"><span data-stu-id="d3898-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="d3898-152">当 Lync VDI 插件配对失败时，较低的右侧显示为红色"X"，显示的配对图标：</span><span class="sxs-lookup"><span data-stu-id="d3898-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="d3898-153">以下是可能的失败原因以及可以采取的更正措施。</span><span class="sxs-lookup"><span data-stu-id="d3898-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="d3898-154">**用户在登录期间输入的凭据不正确。**</span><span class="sxs-lookup"><span data-stu-id="d3898-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="d3898-155">用户应注销 for Business 的 Skype 并重新登录与正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="d3898-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="d3898-156">配对对话框将重新出现，并显示配对是否成功。</span><span class="sxs-lookup"><span data-stu-id="d3898-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="d3898-157">**远程桌面客户端的另一个实例正在运行。**</span><span class="sxs-lookup"><span data-stu-id="d3898-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="d3898-158">如果他们在 Windows 中使用远程桌面连接，用户应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3898-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="d3898-159">启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="d3898-160">单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。</span><span class="sxs-lookup"><span data-stu-id="d3898-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="d3898-161">突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。</span><span class="sxs-lookup"><span data-stu-id="d3898-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="d3898-162">启动新的远程桌面会话并再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="d3898-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="d3898-163">**未正确安装必要的文件。**</span><span class="sxs-lookup"><span data-stu-id="d3898-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="d3898-164">在本地计算机上安装插件后，请进行检查，确保 C:\Program Files\Microsoft Office\Office15（或相应的驱动器号）下应存在以下文件：</span><span class="sxs-lookup"><span data-stu-id="d3898-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="d3898-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="d3898-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="d3898-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="d3898-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="d3898-167">**业务 2015年客户端 Skype 本地计算机上运行。**</span><span class="sxs-lookup"><span data-stu-id="d3898-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="d3898-168">若要使用 Lync VDI 插件，不能在本地计算机上运行业务 2015年客户端 Skype，否则配对将失败。</span><span class="sxs-lookup"><span data-stu-id="d3898-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="d3898-169">作为最佳实践，用户不应安装业务 2015年客户端 Skype 本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="d3898-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3898-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3898-170">See also</span></span>
<span data-ttu-id="d3898-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="d3898-171"></span></span>

[<span data-ttu-id="d3898-172">在 VDI 环境中规划 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d3898-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)