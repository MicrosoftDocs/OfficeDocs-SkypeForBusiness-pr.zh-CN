---
title: 将 Lync VDI 插件与 Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主题讨论在连接到远程虚拟桌面Skype for Business部署过程。
---

# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>将 Lync VDI 插件与 Skype for Business Server
 
本主题讨论在连接到远程虚拟桌面Skype for Business部署过程。 规划注意事项位于 [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。
  
VDI (环境) 虚拟桌面基础结构用于一些安全与合规性问题特别敏感的组织。 他们的用户位于本地Windows计算机上，并且使用虚拟桌面上的客户端。 在Skype for Business这样的连接上使用 VDI 插件软件。
  
有两个解决方案可用于 VDI 插件组件 - 一个由 Microsoft 提供，另一个由 Citrix 提供。 Microsoft 建议在新的部署中使用新的 HDX RealTime Optimization Pack 解决方案，但在其剩余的生命周期内将继续支持原始 Lync VDI 插件。 
  
本主题提供有关部署 Microsoft Lync VDI 插件的详细信息，该插件仅在 Windows 7 和 Windows 8 或 Windows Server 2008 上受支持，并且仅支持 Lync 2013 或 Skype for Business 客户端。 没有计划更新此插件，但适用于 Skype for Business 的 [Citrix HDX RealTime Optimization](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) Pack 将根据需要进行更新。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>为 Lync VDI 插件准备环境
<a name="Prepare_vdi"> </a>

1. 在Skype for Business Server中，请确保所有 Lync VDI 插件用户的 EnableMediaRedirection 都设置为 TRUE。 有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 和 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。
    
2. 在数据中心服务器上，在所有虚拟Skype for Business安装客户端。
    
3. 在本地计算机上，安装 Lync VDI 插件。
    
    用户现在应该将耳机或网络摄像机等设备连接到其本地计算机。
    
## <a name="configure-remote-desktop-connection-settings"></a>配置远程桌面连接设置
<a name="Prepare_vdi"> </a>

若要为 Lync VDI 插件准备远程桌面连接，请在本地计算机上执行以下步骤：
  
1. 如果本地计算机正在运行Windows 8，请跳过此步骤。 如果本地计算机在 sp1 Windows 7 上运行，请安装Windows 8桌面服务客户端[的最新版本](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。
    
2. 通过单击"开始"，然后单击 **"远程桌面** 连接"启动 **远程桌面服务客户端**。
    
3. 单击 **"选项"**。
    
4. 单击"**本地资源"** 选项卡。在 **"远程音频**"下，**设置**"语音"，然后执行以下操作：
    
   - 在 **"远程音频播放"下**， **选择"在此计算机上播放"**。
    
   - 在 **"远程音频录制"** 下，选择 **"不录制"**。
    
   - 单击“**确定**”。
    
5. 单击" **体验"** 选项卡。在 **"性能**"下， **清除"持久位图缓存** "复选框。
    
6. 单击"**常规"** 选项卡。在 **"计算机**"中，键入虚拟桌面的名称，然后单击"连接 **"**。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>登录并使用虚拟Skype for Business上的客户端
<a name="SfB_signin"> </a>

启用 Lync VDI 插件后，用户在登录虚拟桌面时Skype for Business以下步骤。
  
1. 用户在虚拟桌面上运行的 Skype for Business 客户端中输入其凭据。
    
2. 在Skype for Business Lync VDI 插件后，Skype for Business提示用户重新输入凭据。 在此对话框中，建议用户选中“保存我的密码”复选框以在后续登录期间不需要输入凭据。
    
3. Skype for Business开始与 Lync VDI 插件配对。 发生这种情况时，客户端会在状态栏中Skype for Business图标。 左下角的图标表示没有可用的音频设备，右下角的闪烁图标表示 VDI 配对正在进行：a. VDI 配对成功后，图标将更改为指示将用于呼叫的音频设备和 VDI 配对成功：b. 现在，用户可以在连接到本地Skype for Business的兼容设备上查看其状态，并像往常一样拨打和应答呼叫。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 插件疑难解答
<a name="tshoot_VDI"> </a>

如果在安装 Lync VDI 插件后遇到问题，请参阅以下部分。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安装 Lync VDI 插件时的问题

如果安装 Lync VDI 插件时存在问题，请检查以下内容：
  
- 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。
    
- 确保已关闭写保护。 有关说明，请参阅设备制造商的文档。
    
### <a name="troubleshooting-issues-with-pairing"></a>排除配对问题

当 Lync VDI 插件配对失败时，右下角的配对图标显示为红色的"X"，如下所示： 
  
以下是失败的可能原因以及您可以采取的操作来纠正问题。 
  
- **用户在登录期间输入错误凭据。**
    
    用户应注销Skype for Business正确的凭据重新登录。 配对对话框将重新出现，并显示配对是否成功。
    
- **另一个远程桌面客户端的实例正在运行。**
    
    如果用户在远程桌面连接Windows，则用户应执行以下操作：
    
1. 启动任务管理器：按“Alt+Ctrl+Delete”，然后单击“启动任务管理器”。
    
2. 单击“进程”选项卡并在列表中查找名为“mstsc.exe”的所有进程。
    
3. 突出显示每个“mstsc.exe”进程，然后单击“结束进程”。 
    
4. 启动新远程桌面会话并尝试再次连接。 
    
- **必要的文件未正确安装。**
    
    在本地计算机上安装插件后，请检查以确保这些文件位于 C：\Program Files\Microsoft Office\Office15 (或相应的驱动器号下) ：
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **客户端Skype for Business本地计算机上运行。**
    
    若要使用 Lync VDI 插件，Skype for Business客户端不得在本地计算机上运行，否则配对将失败。 作为最佳实践，用户不应在本地计算机上安装Skype for Business客户端。
    
## <a name="see-also"></a>另请参阅
<a name="tshoot_VDI"> </a>

[规划Skype for Business VDI 环境中使用](../../plan-your-deployment/clients-and-devices/vdi-environments.md)