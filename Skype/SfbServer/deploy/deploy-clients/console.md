---
title: 配置 Skype 会议室系统 v2 控制台
ms.author: jambirk
author: jambirk
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。
ms.openlocfilehash: 162aaaed5472fefc3c23cc11800b166ed4b26bc2
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326714"
---
# <a name="configure-a-skype-room-systems-v2-console"></a>配置 Skype 会议室系统 v2 控制台
 
本文介绍如何设置 Skype 会议室系统 v2 控制台和其外围设备。
  
如果业务和 Exchange 帐户所需的 Skype 已经创建并测试[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述，应仅执行这些步骤。 您将需要的硬件和软件[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)中所述。 本主题包括以下部分：
  
- [准备安装媒体](console.md#Prep_Media)
    
- [在控制台上安装一个私有 CA 证书](console.md#Certs)
    
- [安装 Windows 10 和 Skype 会议室系统 v2 控制台应用](console.md#Reimage)
   
- [初始设置控制台](console.md#Initial)
    
- [Skype 会议室系统 v2 部署清单](console.md#Checklist)
    
> [!NOTE]
> Skype 会议室系统 v2 将其中的设备帐户正确设置[部署 Skype 会议室系统 v2](room-systems-v2.md)中所述的业务环境正确配置 Skype 仅适用。
  
## <a name="prepare-the-installation-media"></a>准备安装媒体
<a name="Prep_Media"> </a>

安装 Skype 会议室系统 v2 控制台应用程序需要 USB 存储设备具有至少 32 GB 的容量。 应在设备; 上的没有其他文件在 USB 存储任何现有文件都将丢失。
  
> [!NOTE]
> 未能创建 Skype 会议室系统 v2 安装媒体根据这些说明可能会导致意外的行为。

> [!NOTE]
> 下面的过程是用于创建到图像新 Skype 会议室系统 v2 设备的安装介质中。 现有的设备，默认情况下自动更新从 Windows Update 和 Windows 应用商店。
  
1. 下载 [CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。 
2. 在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。
3. 按照脚本的说明创建 Skype 会议室系统 v2 USB 安装盘。

> [!CAUTION]
> 运行媒体创建脚本从文件夹的名称不能包含空格。 如果没有为文件夹名称中的空格，脚本将失败。

完成后，从计算机中删除 USB 磁盘，并继续[安装 Windows 10 和 Skype 会议室系统 v2 控制台应用程序](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>安装 Windows 10 和 Skype 会议室系统 v2 控制台应用
<a name="Reimage"> </a>

您现在需要应用您已创建的安装媒体。 目标设备将作为一种设备运行，并将设置的默认用户仅运行 Skype 会议室系统 v2 控制台应用程序。

1. 如果目标设备将安装中停靠 (如 Surface Pro)，断开与停靠连接。

2. 确保目标设备未连接到网络。

3. 确保目标设备连接到 AC 电源。

4. 将插入目标设备在 USB 安装盘。

5. 引导到 USB 安装盘。 请参阅制造商说明。 如果 Surface Pro 目标设备，使用以下步骤引导到 USB 安装磁盘：

    1. 按并继续按住下 （-） 按钮的卷。

    2. 按下并释放高级按钮。

    3. 启动 Windows 安装程序后，释放调低音量 (-) 按钮。

8. 安装完成后，系统将关闭。
    
系统已关闭后，它是安全地移除 USB 安装盘。 此时，可以将目标设备放置在其停靠 （如果使用基于停靠的产品）、 附加外围设备所需的会议室中，并连接到网络。 请参阅制造商说明。
  
### <a name="selecting-a-language"></a>选择语言 

创建者的更新，您需要在方案中使用 ApplyCurrentRegionAndLanguage.ps1 脚本隐式语言选择不提供所需的实际的应用程序语言的用户 (例如，需控制台应用程序采用法语，但它在接下来英语） （英文）。
  
> [!NOTE]
> 以下说明仅工时控制台创建使用 Windows 创建者的更新。 不使用媒体与新设置系统已设置的旧/市场系统不能使用这些说明，但应也不会受到影响从初始问题需要此手动干预 (周年日 Edition 让您选取您应用程序语言显式作为安装的一部分）。
  
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
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 重新启动系统。
    
Skype 会议室系统 v2 控制台现在应用所需的语言。
## <a name="initial-set-up-of-the-console"></a>初始设置控制台
<a name="Initial"> </a>

安装 Windows 后，Skype 会议室系统 v2 控制台应用程序将转到其初始安装过程中，启动下一步时，或者如果已选择 /reboot 选项。
  
1. 将显示“用户帐户”屏幕。 输入的 Skype 登录地址 （以 user@domain 格式） 的会议室帐户将与控制台一起使用。
    
2. 输入会议室帐户的密码，再重新输入以进行确认。
    
3. 在"配置域"下的 FQDN 设置为 Skype 业务服务器。 如果业务 SIP 域 Skype 不同的用户的 Exchange 域，请在此字段中输入的 Exchange 域。
    
4. 单击" **下一步**"。
    
5. 选择功能屏幕上的指定的设备，然后单击**下一步**。 默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。 要选择的设备为：
    
   - 用于会议的麦克风：此会议室的默认麦克风。
    
   - 用于会议的扬声器：用于此会议的默认扬声器。 
    
   - 默认扬声器：用于来自 HDMI 采集的音频的扬声器。
    
     每项都有供选择的选项下列菜单。你必须为每个设备做出选择。
    
6. 单击“**完成**”。
    
Skype 会议室系统 v2 控制台应用程序应立即启动登录到 Skype 业务服务器与上面，输入的凭据，并应开始与使用这些相同的凭据的 Exchange 同步其日历。 有关使用控制台应用程序的详细信息，请参阅[Skype 会议室系统版本 2 帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Skype 会议室系统 v2 依赖于认证的控制台硬件的状态。 除非检测到控制台硬件，即使包含 Skype 会议室系统 v2 控制台应用程序的正确创建的图像将无法启动过去的初始安装过程。 对于 Surface Pro 基于解决方案，Surface Pro 必须连接到其相应的停靠硬件，传递此检查。
  
> [!NOTE]
> 某些非英语用户可能需要物理键盘初始安装过程中连接到控制台，在的触摸键盘上不支持符号。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在控制台上安装一个私有 CA 证书
<a name="Certs"> </a>

Skype 会议室系统 v2 控制台需要信任由 Skype 用于连接到的业务和 Exchange 服务器的证书。 对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。 在情况下证书颁发机构专用，例如内部部署 Active Directory 与 Windows 证书颁发机构，您可以添加到几种方式中的 Skype 会议室系统 v2 控制台证书：
  
- 可将控制台加入 Active Directory 和，将自动添加给定证书颁发机构所需的证书发布到 Active Directory （正常的部署选项）。
    
- 可以在映像过程后手动安装证书。 执行此操作之前，您必须完成[初始设置的控制台](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手动安装证书 

1. 将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。
    
2. 控制台置于管理员模式 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。
    
3. 运行以下命令：
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 域 （可选）
<a name="Certs"> </a>

Skype 会议室系统 v2 控制台可以加入您的域。 应将 Skype 会议室系统 v2 控制台放入从 PC 工作站单独的 OU，因为多个工作站策略不与 Skype 会议室系统 v2 兼容。 常见的示例是将阻止自动启动 Skype 会议室系统 v2 的密码实施策略。 有关 GPO 设置管理的信息，请参阅[Manage Skype Room Systems v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md)。
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>将 Skype 会议室系统 v2 加入域

1. 登录到控制台从管理员帐户 （请参阅[管理模式和设备管理](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)）。
    
2. 启动提升的 Powershell 命令提示符。
    
3. 在 Powershell 中输入以下命令：
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果您的完全限定的域名为 redmond.corp.microsoft.com 且您希望您 Skype 会议室系统 v2 控制台中"Skype 会议室系统 v2"是"Resources"OU 的子级的 OU，则可该命令：
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果您想要重命名的计算机加入到域时，，使用计算机的新名称后跟-NewName 标志。
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Skype 会议室系统 v2 部署清单
<a name="Checklist"> </a>

执行操作完全配置了控制台和所有外围设备最终验证时，使用以下清单：
  
**应用程序设置**

|||
|:-----|:-----|
|☐  <br/> |在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）  <br/> |
|☐  <br/> |已正确设置 Windows 计算机名称（对于远程管理很有用）  <br/> |
|☐  <br/> |已设置并验证管理员帐户密码  <br/> |
|☐  <br/> |已应用所有固件更新  <br/> |
   
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
   
**扩展坞**

|||
|:-----|:-----|
|☐  <br/> |电缆是安全的且未收缩  <br/> |
|☐  <br/> |通过 HDMI 进行的音频采集工作正常  <br/> |
|☐  <br/> |通过 HDMI 进行的视频采集工作正常  <br/> |
|☐  <br/> |扩展坞可以自由旋转  <br/> |
|☐  <br/> |显示亮度对于环境而言可接受  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="Checklist"> </a>

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)