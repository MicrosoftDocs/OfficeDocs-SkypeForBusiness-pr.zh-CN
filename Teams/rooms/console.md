---
title: 配置 Microsoft Teams 会议室控制台
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置和配置主机Microsoft Teams 会议室及其外围设备。
ms.openlocfilehash: 81da06df24dc98e0cde2bc18c081ff46b54e07b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629304"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>配置 Microsoft Teams 会议室控制台

本文介绍如何设置主机Microsoft Teams 会议室及其外围设备。
  
只有在已根据部署 Microsoft Teams 中所述创建Skype for Business Exchange帐户并测试帐户时，才应[执行Microsoft Teams 会议室。](rooms-deploy.md) 需要满足以下要求中所述的[Microsoft Teams 会议室软件](requirements.md)。 本主题包括以下部分：
  
- [准备安装媒体](console.md#Prep_Media)
- [在主机上安装专用 CA 证书](console.md#Certs)
- [安装 Windows 10 和 Microsoft Teams 会议室 控制台应用](console.md#Reimage)
- [主机的初始设置](console.md#Initial)
- [Microsoft Teams 会议室部署清单](console.md#Checklist)

> [!NOTE]
> Microsoft Teams 会议室仅在正确配置的 Microsoft Teams 或 Skype for Business 环境中工作，其中正确设置了设备帐户，如部署[Microsoft Teams 会议室。](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>准备安装媒体
<a name="Prep_Media"> </a>

安装 Microsoft Teams 会议室 主机应用需要至少具有 32GB 容量的 USB 存储设备。 设备上不应存在任何其他文件;USB 存储上的任何现有文件都将丢失。
  
> [!NOTE]
> 根据这些说明Microsoft Teams 会议室安装媒体可能会导致意外行为。

> [!NOTE]
> 下面的过程用于创建安装媒体，以在设备上Microsoft Teams 会议室映像。 默认情况下，现有设备会从应用商店Windows更新Windows更新。

> [!IMPORTANT]
> 用于创建Windows 10安装媒体Microsoft Teams 会议室计算机必须位于目标安装媒体Windows或更高版本的安装媒体上。
  
1. 下载 [CreateSrsMedia.ps1 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。
3. 按照脚本的说明创建 U 盘Microsoft Teams 会议室 U 盘。


> [!TIP]
> 每次启动CreateSrsMedia.ps1时，屏幕输出将包含会话日志文件脚本的名称。 如果运行脚本时发生问题，请确保在请求支持时提供该脚本的副本。 

脚本CreateSrsMedia.ps1自动执行以下任务：

1. 下载适用于 Microsoft Teams 会议室 的最新 MSI 安装程序。
2. 确定用户Windows的生成。 最近发布的版本可能受测试，也可能不会受支持用于Microsoft Teams 会议室设备。
3. 下载必要的支持组件。
4. 在安装媒体上组装所需的组件。

需要特定版本的 Windows 10，并且此版本仅适用于批量许可客户。  可以从批量许可 [服务中心获取副本](https://www.microsoft.com/Licensing/servicecenter/)。

完成后，从计算机中删除 USB 磁盘，并继续执行安装 Windows 10[和Microsoft Teams 会议室控制台应用](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安装 Windows 10 和 Microsoft Teams 会议室 控制台应用
<a name="Reimage"> </a>

现在需要应用已创建的设置媒体。 目标设备将作为设备运行，默认用户将设置为仅运行Microsoft Teams 会议室应用。

1. 如果目标设备将安装在扩展坞 (例如，Surface Pro) ，请将其与扩展坞断开连接。

2. 确保目标设备未连接到网络。

3. 确保目标设备已连接到交流电源。

4. 将 USB 安装磁盘插入目标设备。

5. 启动到 USB 安装磁盘。 请参阅制造商说明。 如果目标设备是Surface Pro，请使用以下步骤启动到 USB 安装磁盘：

    a. 按并继续按下" ("按钮) 音量。

    b. 按下并松开电源按钮。

    c. 启动 Windows 安装程序后，释放调低音量 (-) 按钮。

8. 安装完成后，系统将关闭。
    
系统关闭后，可以安全地移除 USB 安装磁盘。 此时，如果使用基于扩展坞的产品 (，可以将目标设备放在其扩展坞中) 附加会议室所需的外围设备，并连接到网络。 请参阅制造商说明。

> [!NOTE]
> 系统会自动Microsoft Teams 会议室下载适用于 适用于企业的 Microsoft Store 的软件更新。 请参阅[适用于企业的 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business)和教育的先决条件，验证会议室主机是否能够访问应用商店和自我更新。  

### <a name="selecting-a-language"></a>选择语言 

在创意者的更新中，你需要在隐式语言选择未为用户提供他们想要的实际应用程序语言的情况下使用 ApplyCurrentRegionAndLanguage.ps1 脚本 (例如，他们希望控制台应用以法语显示，但它以英语) 提供。
  
> [!NOTE]
> 以下说明仅适用于使用创建者更新Windows创建的主机。 尚未将媒体与新预配系统一起设置的旧式/市场内系统将不能使用这些说明，但不应受到需要此手动干预的初始问题的影响 (周年版允许作为设置) 的一部分显式选择应用语言。
  
### <a name="to-apply-your-desired-language"></a>应用你需要的语言

1. 切换至管理模式。
    
2. 选择“开始”菜单。
    
3. 选择齿轮图标以启动“**设置**”应用。
    
4. 选择 **"时间 &amp; 语言"。**
    
5. 选择 **"区域 &amp; 语言"。**
    
6. 选择“**添加语言**”。
    
7. 选择要添加的语言。
    
8. 选择刚刚添加到"语言"列表的语言。
    
9. 选择“**设置为默认值**”。
    
10. 对于要删除的任何语言：
    
    a. 选择要删除的语言。
    
    b. 选择“**删除**”。
    
11. 启动提升的命令提示符。
    
12. 运行以下命令： 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 重新启动系统。
    
现在，所需语言将应用到 Microsoft Teams 会议室 控制台。
## <a name="initial-set-up-of-the-console"></a>主机的初始设置
<a name="Initial"> </a>

安装Windows后，Microsoft Teams 会议室应用将在下一次启动时或选择 /reboot 选项时进入其初始安装过程。
  
1. 将显示“用户帐户”屏幕。 输入Skype主机 (的user@domain) 帐户的登录地址。
    
2. 输入会议室帐户的密码，再重新输入以进行确认。
    
3. 在"配置域"下，设置域的 FQDN Skype for Business Server。 如果Skype for Business SIP 域与用户Exchange域不同，请在此字段中Exchange域。
    
4. 单击" **下一步**"。
    
5. 在"功能"屏幕上选择指示的设备，然后单击"下一 **步"。** 默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。 要选择的设备为：
    
   - 用于会议的麦克风：此会议室的默认麦克风。
    
   - 用于会议的扬声器：用于此会议的默认扬声器。 
    
   - 默认扬声器：用于来自 HDMI 采集的音频的扬声器。
    
     每项都有供选择的选项下列菜单。你必须为每个设备做出选择。
    
6. 单击“**完成**”。
    
Microsoft Teams 会议室控制台应用应该立即开始使用上面输入的Skype for Business Server登录 Skype for Business Server，并且还应使用这些相同的凭据开始将日历与 Exchange同步。 有关使用控制台应用的详细信息，请参阅 Microsoft Teams 会议室[帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft Teams 会议室取决于是否存在经过认证的主机硬件。 即使正确创建的映像包含主机Microsoft Teams 会议室，除非检测到主机硬件，否则不会启动初始设置过程。 对于Surface Pro的解决方案，Surface Pro必须连接到其随附的扩展坞硬件，以通过此检查。
  
> [!NOTE]
> 如果触摸键盘不支持符号，某些非英语用户可能需要在初始设置期间连接到主机的物理键盘。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在主机上安装专用 CA 证书
<a name="Certs"> </a>

Microsoft Teams 会议室主机需要信任它所连接到的服务器使用的证书。 对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。 如果证书颁发机构是私有的，例如使用 Active Directory 和 Windows 证书颁发机构进行本地部署，可以通过多种方式将证书添加到 Microsoft Teams 会议室 控制台：
  
- 可以将主机加入 Active Directory，在证书颁发机构发布到 Active Directory 后，这会自动添加所需的证书， (常规部署) 。
    
- 可以在映像过程后手动安装证书。 在这样做之前，必须完成主机 [的初始设置](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手动安装证书 

1. 将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。
    
2. 将主机放在管理模式下， ([管理模式和设备管理) 。](rooms-operations.md#AdminMode)
    
3. 运行以下命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 域 (可选) 
<a name="Certs"> </a>

你可以将Microsoft Teams 会议室加入你的域。 Microsoft Teams 会议室主机应放置在与电脑工作站不同的 OU 中，因为许多工作站策略与 Microsoft Teams 会议室。 一个常见示例是密码强制策略，Microsoft Teams 会议室自动启动。 有关管理 GPO 设置的信息，请参阅管理[Microsoft Teams 会议室。](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>将Microsoft Teams 会议室加入域

1. 从管理员帐户登录主机， ([管理模式和设备管理) 。](rooms-operations.md#AdminMode)
    
2. 启动提升的 Powershell 命令提示符。
    
3. 在 Powershell 中输入以下命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果完全限定的域 redmond.corp.microsoft.com 并且希望 Microsoft Teams 会议室 主机位于"Microsoft Teams 会议室"OU 中，该 OU 是"Resources"OU 的子级，则命令将是：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果要在将计算机加入域时重命名计算机，请使用 -NewName 标志，后跟计算机的新名称。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 会议室部署清单
<a name="Checklist"> </a>

在最终验证主机及其所有外围设备是否完全配置时，请使用以下清单：
  
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
|☐  <br/> |以最佳方式定位相机的功能和位置  <br/> |
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

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)