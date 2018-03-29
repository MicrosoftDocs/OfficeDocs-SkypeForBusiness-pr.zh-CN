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
description: 本主题讨论用于 Skype 业务同时连接到远程虚拟桌面部署过程。
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署 Lync VDI 插件
 
本主题讨论用于 Skype 业务同时连接到远程虚拟桌面部署过程。 
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户驻留在本地 Windows 计算机上并使用虚拟桌面上的客户端。 使用 Skype 业务连接上这样需要其他 VDI 插件软件。
  
有两种解决方案一提供的 Microsoft 和一个提供 Citrix VDI 插件组件的可用。 Microsoft 建议在新部署中使用的新的 HDX 实时优化包解决方案，但将继续支持原始 Lync VDI 插件生命周期的其余部分。 
  
本主题提供了有关部署 Microsoft Lync VDI 插件，它只支持 Windows 7 和 Windows 8 上 Windows Server 2008 中，并仅支持 Lync 2013 或 Skype 业务 2015年客户端的详细信息。 没有计划来更新此插件，但需要时，将更新为业务 Skype [Citrix HDX 实时优化包](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>针对 Lync VDI 插件准备你的环境
<a name="Prepare_vdi"> </a>

1. 在业务服务器 2015年的 Skype，确保为所有 Lync VDI 插件用户 EnableMediaRedirection 设置为 TRUE。 有关详细信息，请参阅[新建 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet 和[集 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。
    
2. 在数据中心服务器上，安装 Skype 业务 2015年上所有虚拟机的客户机。
    
3. 在本地计算机上安装 Lync VDI 插件。
    
    现在，用户应将诸如耳机或网络摄像机等设备连接到其本地计算机。
    
## <a name="configure-remote-desktop-connection-settings"></a>配置远程桌面连接设置
<a name="Prepare_vdi"> </a>

若要准备 Lync VDI 插件的远程桌面连接，请在本地计算机上执行以下步骤：
  
1. 如果本地计算机运行的 Windows 8，请跳过此步骤。 如果本地计算机运行的 Windows 7 sp1，请安装最新的 Windows 8 版本的[远程桌面服务客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。
    
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

Lync VDI 插件启用后，用户将执行下列步骤，在虚拟桌面登录 Skype 业务 2015年个。
  
1. 用户键入他或她在到凭据业务 2015年客户端运行在虚拟机上的 Skype。
    
2. Skype 的业务 2015年检测 Lync VDI 插件后，业务 2015年的 Skype 将提示用户重新输入凭据。 在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。
    
3. Skype 的业务 2015年开始配对使用 Lync VDI 插件。 虽然发生这种情况，客户端将 Skype 业务 2015年状态栏中显示两个图标。 左下角的图标指示没有可用的音频设备，而右下角的闪烁图标指示 VDI 配对正在进行：
    4. VDI 配对成功后，这两个图标将更改为分别指示用于呼叫的音频设备和 VDI 配对成功：
    5. 用户现在可以看到他或她的存在在 Skype 上的业务 2015年兼容设备，连接到本地计算机，并将照常接听电话。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 插件故障排除
<a name="tshoot_VDI"> </a>

如果在安装 Lync VDI 插件后遇到问题，请参阅以下各节。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安装 Lync VDI 插件时出现问题 

如果有问题的安装 Lync VDI 插件，请进行以下检查：
  
- 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。
    
- 确保已关闭写保护。 请参阅设备制造商的说明文档。
    
### <a name="troubleshooting-issues-with-pairing"></a>排除在配对时出现的问题

Lync VDI 插件配对失败时，在较低的右侧显示为红色"X"作为显示的配对图标： 
  
以下是可能的失败原因以及可以采取的更正措施。 
  
- **用户在登录期间输入的凭据不正确。**
    
    用户应注销业务的 Skype，并使用正确的凭据登录。 配对对话框将重新出现，并显示配对是否成功。
    
- **远程桌面客户端的另一个实例正在运行。**
    
    如果他们在 Windows 中使用远程桌面连接，用户应该执行下列操作：
    
1. 启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。
    
2. 单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。
    
3. 突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。 
    
4. 启动新的远程桌面会话并再次尝试连接。 
    
- **未正确安装必要的文件。**
    
    在本地计算机上安装插件后，请进行检查，确保 C:\Program Files\Microsoft Office\Office15（或相应的驱动器号）下应存在以下文件：
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Skype 业务 2015年客户端的本地计算机上运行。**
    
    若要使用 Lync VDI 插件，Skype 业务 2015年客户机不能运行在本地计算机上，否则配对将失败。 作为最佳操作，用户不应安装 Skype 业务 2015年客户端的本地计算机上。
    
## <a name="see-also"></a>另请参阅
<a name="tshoot_VDI"> </a>

#### 

[在 VDI 环境规划业务的 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

