---
title: 通过 Skype for Business 服务器部署 Lync VDI 插件
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主题介绍了在连接到远程虚拟桌面时使用 Skype for Business 的部署过程。
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288752"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>通过 Skype for Business 服务器部署 Lync VDI 插件
 
本主题介绍了在连接到远程虚拟桌面时使用 Skype for Business 的部署过程。 规划[在 VDI 环境中规划 Skype for](../../plan-your-deployment/clients-and-devices/vdi-environments.md)business 时的注意事项。
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户驻留在本地 Windows 计算机上并使用虚拟桌面上的客户端。 在类似的连接上使用 Skype for Business 需要其他 VDI 插件软件。
  
有两个可用于 VDI 插件组件的解决方案 (由 Microsoft 提供) 和 Citrix 提供的解决方案之一。 Microsoft 建议在新部署中使用新的 HDX 实时优化包解决方案, 但将继续支持其生命周期其余部分的原始 Lync VDI 插件。 
  
本主题提供有关部署 Microsoft Lync VDI 插件的详细信息, 该插件仅在 Windows 7 和 Windows 8 或 Windows Server 2008 上受支持, 并且仅支持 Lync 2013 或 Skype for business 客户端。 没有计划更新此插件, 但 Skype for Business 的[CITRIX HDX 实时优化包](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)将根据需要进行更新。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>针对 Lync VDI 插件准备你的环境
<a name="Prepare_vdi"> </a>

1. 在 Skype for Business 服务器中, 确保所有 Lync VDI 插件用户的 EnableMediaRedirection 设置为 TRUE。 有关详细信息, 请参阅[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 的帮助主题。
    
2. 在数据中心服务器上, 在所有虚拟机上安装 Skype for Business 客户端。
    
3. 在本地计算机上, 安装 Lync VDI 插件。
    
    现在，用户应将诸如耳机或网络摄像机等设备连接到其本地计算机。
    
## <a name="configure-remote-desktop-connection-settings"></a>配置远程桌面连接设置
<a name="Prepare_vdi"> </a>

若要为 Lync VDI 插件准备远程桌面连接, 请在本地计算机上执行以下步骤:
  
1. 如果本地计算机运行的是 Windows 8, 请跳过此步骤。 如果本地计算机运行的是带有 SP1 的 Windows 7, 请安装最新的 Windows 8 版本的[远程桌面服务客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。
    
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

启用 Lync VDI 插件后, 当登录到虚拟机上的 Skype for Business 时, 用户请按照以下步骤操作。
  
1. 用户在虚拟机上运行的 Skype for business 客户端中键入他或她的凭据。
    
2. Skype for business 检测到 Lync VDI 插件后, Skype for business 将提示用户重新输入凭据。 在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。
    
3. Skype for Business 开始与 Lync VDI 插件配对。 在这种情况下, 客户端在 Skype for Business 状态栏中显示两个图标。 左下角的图标指示没有可用的音频设备, 右下角的闪烁图标指示正在进行 VDI 配对: a。 在 VDI 配对成功后, 图标将更改, 以指示将用于呼叫和 VDI 配对成功的音频设备: b。 用户现在可以在连接到本地计算机的 Skype for business 兼容设备上查看其状态, 并照常拨打和接听电话。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI 插件故障排除
<a name="tshoot_VDI"> </a>

如果在安装 Lync VDI 插件后遇到问题，请参阅以下各节。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>安装 Lync VDI 插件时出现问题 

如果安装 Lync VDI 插件时出现问题, 请检查以下事项:
  
- 确保在 TEMP 和 TMP 系统变量中指定的文件夹内有足够空间。
    
- 确保已关闭写保护。 有关说明, 请参阅设备制造商的文档。
    
### <a name="troubleshooting-issues-with-pairing"></a>排除在配对时出现的问题

当 Lync VDI 插件配对失败时, 右下角的配对图标将显示为红色的 "X", 如下所示: 
  
以下是可能的失败原因以及可以采取的更正措施。 
  
- **用户在登录期间输入的凭据不正确。**
    
    用户应注销 Skype for Business, 然后使用正确的凭据再次登录。 配对对话框将重新出现，并显示配对是否成功。
    
- **远程桌面客户端的另一个实例正在运行。**
    
    如果他们使用的是 Windows 中的远程桌面连接, 则用户应该执行以下操作:
    
1. 启动任务管理器：按 **Alt+Ctrl+Delete**，然后单击“**启动任务管理器**”。
    
2. 单击“**进程**”选项卡并在列表中查找名为“**mstsc.exe**”的所有进程。
    
3. 突出显示每个“**mstsc.exe**”进程，然后单击“**结束进程**”。 
    
4. 启动新的远程桌面会话并再次尝试连接。 
    
- **未正确安装必要的文件。**
    
    在本地计算机上安装插件后，请进行检查，确保 C:\Program Files\Microsoft Office\Office15（或相应的驱动器号）下应存在以下文件：
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Skype for Business 客户端正在本地计算机上运行。**
    
    若要使用 Lync VDI 插件, 则不能在本地计算机上运行 Skype for business 客户端, 否则配对将失败。 最佳做法是, 用户不应在本地计算机上安装 Skype for Business 客户端。
    
## <a name="see-also"></a>另请参阅
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
