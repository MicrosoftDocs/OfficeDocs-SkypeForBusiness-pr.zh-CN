---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。
ms.openlocfilehash: b82343f98304b0607bb3525b508aecf81e80a031
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="configure-a-skype-room-systems-v2-console"></a>配置 Skype 会议室系统 v2 控制台
 
本文介绍如何设置 Skype 会议室系统 v2 控制台设备及其外围设备。
  
如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述，应仅执行这些步骤。 您将需要的硬件和软件[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。 本主题包括以下部分：
  
- [准备安装映像](console.md#Prep_Image)
    
- [在平板电脑设备上安装一个私有 CA 证书](console.md#Certs)
    
- [安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序](console.md#Reimage)
   
- [初始设置控制台](console.md#Initial)
    
- [Skype 会议室系统 v2 部署清单](console.md#Checklist)
    
> [!NOTE]
> Skype 会议室系统 v2 将其中的设备帐户正确设置[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述的业务环境正确配置 Skype 仅适用。 
  
## <a name="prepare-the-installation-image"></a>准备安装映像
<a name="Prep_Image"> </a>

Surface Pro 4 或 Surface Pro 上安装 Skype 会议室系统 v2 应用程序需要具有至少 32 GB 内存格式设置为 FAT32 磁盘上的 USB 存储设备。 不应在设备上的任何其他文件，在 USB 存储任何现有文件都将丢失。 
  
> [!NOTE]
> 如果未按照这些说明创建你的控制台映像，将很可能导致发生意外行为。 Skype 会议室系统 v2 图像创建不再支持 Windows 10 企业周年日 Update (版本 1607)。 
  
> [!NOTE]
> 与 Windows 10 企业周年日更新将移至通过 Windows 应用商店的 Skype 会议室系统 v2 更新 3 现有 Skype 会议室系统 v2，但应该执行全新安装，如下所述。 
  
1. 下载[为 KB4056892 MSU](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)。
2. 下载[CreateSrsMedia.ps1 脚本](room-systems-v2-scripts.md)。
3. 将为 KB4056892 MSU CreateSrsMedia.ps1 脚本相同的目录。
4. Windows 10 计算机上从提升提示符处运行 CreateSrsMedia.ps1 脚本。


按照脚本的说明创建 Skype 会议室系统 v2 USB 安装盘。 完成后，从计算机中删除 USB 磁盘，并继续[安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序](console.md#Reimage)。
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>安装 Windows 10 和 Skype 会议室系统 v2 控制台应用 
<a name="Reimage"> </a>

现在，你需要应用创建的映像。 平板电脑将运行作为一种设备，并将设置的默认用户仅运行 Skype 会议室系统 v2 应用程序。 
  
1. 应该将平板电脑连接到电源。 从完全断电的状态开始。 如有必要，请按下并按住电源按钮，直至平板电脑关闭。
    
2. 将 USB 安装磁盘插入平板电脑。
    
3. 按下并一直按住平板电脑上的调低音量 (-) 按钮。 
    
4. 按下并释放平板电脑上的电源按钮。
    
5. 启动 Windows 安装程序后，释放调低音量 (-) 按钮。
    
6. 安装完成后，系统将关闭。
    
系统已关闭后，它是安全地移除 USB 安装盘。 此时，可以将平板电脑置于扩展坞中，并连接会议室所需的外围设备。 请参阅制造商说明。
  
 
### <a name="selecting-a-language-in-creators-update"></a>在 Creator Update 中选择语言

在创建者的更新中，您将需要使用 ApplyCurrentRegionAndLanguage.ps1 脚本方案中隐式语言选择不提供所需的实际的应用程序语言的用户 （例如，所需应用程序采用法语，但它是在接下来英语） （英文）。
  
> [!NOTE]
> 以下说明仅适用于使用 Windows Creator Update 创建的设备。 尚未正确地重新映像至新设置系统的传统/已上市系统将无法使用这些说明，但应该不会受到需要手动干预的初始问题困扰（Anniversary Edition 允许你在设置中显式选择应用语言）。 
  
### <a name="to-apply-your-desired-language"></a>应用你需要的语言

1. 切换至管理模式。
    
2. 选择“开始”菜单。
    
3. 选择齿轮图标以启动“**设置**”应用。
    
4. 选中**时间&amp;语言**。
    
5. 选中**区域&amp;语言**。
    
6. 选择“**添加语言**”。
    
7. 选择要添加的语言。
    
8. 选择您刚刚添加到"语言"列表的语言。
    
9. 选择“**设置为默认值**”。
    
10. 对于要删除的任何语言：
    
    a. 选择要删除的语言。
    
    b. 选择“**删除**”。
    
11. 启动提升的命令提示符。
    
12. 运行以下命令： 
    
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. 重新启动系统。
    
所需的语言立即应用于 Skype 会议室系统 v2 设备。
## <a name="initial-set-up-of-the-console"></a>控制台的初始设置 
<a name="Initial"> </a>

安装 Windows 后，Skype 会议室系统 v2 应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。
  
1. 将显示“用户帐户”屏幕。输入要在该设备中使用的会议室帐户的 Skype 登录地址（格式为 user@domain）。
    
2. 输入会议室帐户的密码，再重新输入以进行确认。
    
3. 在"配置域"下的 FQDN 设置为 Skype 业务服务器。 如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。
    
4. 单击" **下一步**"。
    
5. 选择功能屏幕上的指定的设备，然后单击**下一步**。 默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。 要选择的设备为：
    
   - 用于会议的麦克风：此会议室的默认麦克风。
    
   - 用于会议的扬声器：用于此会议的默认扬声器。 
    
   - 默认扬声器：用于来自 HDMI 采集的音频的扬声器。
    
    每项都有供选择的选项下列菜单。你必须为每个设备做出选择。
    
6. 单击“**完成**”。
    
应用程序应立即启动登录到 Skype 的业务服务器 2015年上面，输入凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。 有关使用应用程序的详细信息，请参阅[Skype 会议室系统版本 2 帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Skype 会议室系统 v2 依赖于认证的控制台硬件 (Logitech SmartDock) 的状态。 除非检测到控制台硬件，即使包含 Skype 会议室系统 v2 应用程序 Surface Pro 4 或 Surface Pro 上加载的正确创建的图像将无法启动过去的初始安装过程。 
  
> [!NOTE]
> 在初始安装过程中，如果发生触摸键盘不支持某些符号的情况，一些非英语用户可能需要连接到控制台的物理键盘。 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>在平板电脑设备上安装私有 CA 证书
<a name="Certs"> </a>

Skype 会议室系统 v2 设备都需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。 对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。 在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Skype 会议室系统 v2 设备的证书：
  
- 如果证书颁发机构已发布至 Active Directory（标准部署选项），则可将设备加入 Active Directory，此操作会自动添加所需证书。
    
- 可以在映像过程后手动安装证书。在此之前，必须完成[控制台的初始设置](console.md#Initial)。 
    
### <a name="to-manually-install-the-certificate"></a>手动安装证书 

1. 将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。
    
2. 曲面 4 置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。
    
3. 运行以下命令：
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 域（可选）
<a name="Certs"> </a>

Skype 会议室系统 v2 设备可以加入您的域。 应将 Skype 会议室系统 v2 设备放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Skype 会议室系统 v2 兼容。 常见的示例是将阻止自动启动 Skype 会议室系统 v2 的密码实施策略。 有关管理 GPO 设置的信息，请参阅[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>将 Skype 会议室系统 v2 加入域

1. 登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。
    
2. 启动提升的 Powershell 命令提示符。
    
3. 在 Powershell 中输入以下命令：
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 且您希望 Skype 会议室系统 v2 设备处于"Skype 会议室系统 v2"是"Resources"OU 的子级的 OU，则可该命令：
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Skype 会议室系统 v2 部署清单
<a name="Checklist"> </a>

在最终验证控制台设备及其所有外围设备是否已进行完全配置时，请使用下面的清单：
  
**应用程序设置**

|||
|:-----|:-----|
|☐  <br/> |在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）  <br/> |
|☐  <br/> |已正确设置 Windows 计算机名称（对于远程管理很有用）  <br/> |
|☐  <br/> |已设置并验证管理员帐户密码  <br/> |
|☐  <br/> |已应用所有 Surface Pro 4 或 Surface Pro 系统更新  <br/> |
   
**音频/视频外围设备**

|||
|:-----|:-----|
|☐  <br/> |摄像头外围设备固件版本正确（如果适用）  <br/> |
|☐  <br/> |摄像机功能和定位以最佳方式  <br/> |
|☐  <br/> |将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备  <br/> |
|☐  <br/> |将用于录制默认通信设备的设置设为预期的音频外围设备  <br/> |
|☐  <br/> |音频外围设备固件版本正确（如果适用）  <br/> |
|☐  <br/> |音频输入设备工作正常且位置最佳  <br/> |
|☐  <br/> |音频输出设备工作正常且位置最佳  <br/> |
   
**停靠**

|||
|:-----|:-----|
|☐  <br/> |电缆是安全的且未收缩  <br/> |
|☐  <br/> |通过 HDMI 进行的音频采集工作正常  <br/> |
|☐  <br/> |通过 HDMI 进行的视频采集工作正常  <br/> |
|☐  <br/> |扩展坞可以自由旋转  <br/> |
|☐  <br/> |显示亮度对于环境而言可接受  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="Checklist"> </a>

#### 

[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

