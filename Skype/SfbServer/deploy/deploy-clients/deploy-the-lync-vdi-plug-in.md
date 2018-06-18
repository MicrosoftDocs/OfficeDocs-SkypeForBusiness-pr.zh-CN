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
ms.openlocfilehash: 4e4193998a9374c1aa0160999ad53a9ec3d8aab7
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927850"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署 Lync VDI 插件
 
本主题讨论 for Business 连接到远程虚拟桌面时使用 Skype 的部署过程。 [规划在 VDI 环境中的业务的 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)位于规划注意事项。
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户驻留在本地 Windows 计算机上并使用虚拟桌面上的客户端。 使用 Skype for Business 连接这样需要其他 VDI 插件软件。
  
有两个解决方案一个提供 Microsoft 和 Citrix 提供一个可用于 VDI 插件组件-。 Microsoft 建议在新部署中使用新的 HDX 实时 Optimization Pack 解决方案，但将继续支持生命周期的其余部分的原始 Lync VDI 插件。 
  
本主题提供有关部署 Microsoft Lync VDI 插件，它在 Windows 7 和 Windows 8 或 Windows Server 2008，才支持并仅支持业务 2015年客户端的 Lync 2013 或 Skype 的详细信息。 没有计划更新此插件，但根据需要将会更新 for Business 的 Skype [Citrix HDX 实时 Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) 。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>针对 Lync VDI 插件准备你的环境
<a name="Prepare_vdi"> </a>

1. 中的业务服务器 2015 Skype，确保针对所有 Lync VDI 插件用户将 EnableMediaRedirection 设置为 TRUE。 有关详细信息，请参阅[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。
    
2. 在数据中心服务器上，安装在所有虚拟机上的业务 2015年客户端 Skype。
    
3. 在本地计算机上安装 Lync VDI 插件。
    
    现在，用户应将诸如耳机或网络摄像机等设备连接到其本地计算机。
    
## <a name="configure-remote-desktop-connection-settings"></a>配置远程桌面连接设置
<a name="Prepare_vdi"> </a>

要为 Lync VDI 插件准备远程桌面连接，请在本地计算机上执行以下步骤：
  
1. 如果本地计算机正在运行 Windows 8，跳过此步骤。 如果本地计算机运行的 Windows 7 SP1，安装[远程桌面服务客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)的最新 Windows 8 版本。
    
2. 通过单击“**开始**”，然后单击“**远程桌面连接**”，启动远程桌面服务客户端。
    
3. 单击“**选项**”。
    
4. 单击“**本地资源**”选项卡。在“**远程音频**”下，单击“**设置**”，然后执行以下操作：
    
  - 在“**远程音频播放**”下，选择“**在此计算机上播放**”。
    
  - 在“**远程音频录制**”下，选择“**不录制**”。
    
  - 单击“**确定**”。
    
5. 单击“**体验**”选项卡。在“**性能**”下，清除“**持久位图缓存**”复选框。
    
6. 单击“**常规**”选项卡。在“**计算机**”中，键入虚拟桌面的名称，然后单击“**连接**”。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>登录到和使用虚拟桌面上的 Skype for Business
<a name="SfB_signin"> </a>

启用 Lync VDI 插件后，用户在虚拟桌面上登录到业务 2015年的 Skype 时遵循这些步骤。
  
1. 在用户键入他/她凭据在虚拟机上运行的业务 2015年客户端 Skype。
    
2. Skype 的业务 2015年检测 Lync VDI 插件之后，业务 2015年的 Skype 提示用户重新输入凭据。 在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。
    
3. Skype 的业务 2015年开始使用 Lync VDI 插件配对。 时出现这种情况，客户端中的业务 2015年状态栏 Skype 显示两个图标。 左下角的图标指示没有可用的音频设备，而右下角的闪烁图标指示 VDI 配对正在进行：
    4. VDI 配对成功后，这两个图标将更改为分别指示用于呼叫的音频设备和 VDI 配对成功：
    5. 用户现在可以看到他/她状态 Skype 上的业务 2015年兼容设备的连接到本地计算机，并进行呼叫和应答像往常一样。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 插件故障排除
<a name="tshoot_VDI"> </a>

如果在安装 Lync VDI 插件后遇到问题，请参阅以下各节。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安装 Lync VDI 插件时出现问题 

如果安装 Lync VDI 插件的问题，检查以下项目：
  
- 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。
    
- 确保已关闭写保护。 请参阅设备制造商的文档的说明。
    
### <a name="troubleshooting-issues-with-pairing"></a>排除在配对时出现的问题

当 Lync VDI 插件配对失败时，较低的右侧显示为红色"X"，显示的配对图标： 
  
以下是可能的失败原因以及可以采取的更正措施。 
  
- **用户在登录期间输入的凭据不正确。**
    
    用户应注销 for Business 的 Skype 并重新登录与正确的凭据。 配对对话框将重新出现，并显示配对是否成功。
    
- **远程桌面客户端的另一个实例正在运行。**
    
    如果他们在 Windows 中使用远程桌面连接，用户应执行以下操作：
    
1. 启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。
    
2. 单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。
    
3. 突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。 
    
4. 启动新的远程桌面会话并再次尝试连接。 
    
- **未正确安装必要的文件。**
    
    在本地计算机上安装插件后，请进行检查，确保 C:\Program Files\Microsoft Office\Office15（或相应的驱动器号）下应存在以下文件：
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **业务 2015年客户端 Skype 本地计算机上运行。**
    
    若要使用 Lync VDI 插件，不能在本地计算机上运行业务 2015年客户端 Skype，否则配对将失败。 作为最佳实践，用户不应安装业务 2015年客户端 Skype 本地计算机上。
    
## <a name="see-also"></a>另请参阅
<a name="tshoot_VDI"> </a>

[在 VDI 环境中规划 Skype for Business](../../plan-your-deployment/clients-and-devices/vdi-environments.md)