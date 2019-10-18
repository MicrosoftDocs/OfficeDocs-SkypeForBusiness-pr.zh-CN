---
title: 配置 Microsoft 团队聊天室控制台
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置 Microsoft 团队聊天室控制台及其外围设备。
ms.openlocfilehash: f42f89d25a58ce96308318cc732e85f7080b86e5
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569903"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>配置 Microsoft 团队聊天室控制台

本文介绍如何设置 Microsoft 团队聊天室控制台及其外围设备。
  
仅当已创建和测试必要的 Microsoft 团队或 Skype for business 和 Exchange 帐户时，才应执行这些步骤，如[部署 Microsoft 团队聊天室](room-systems-v2.md)中所述。 你将需要[Microsoft 团队会议室要求](requirements.md)中所述的硬件和软件。 本主题包括以下部分：
  
- [准备安装媒体](console.md#Prep_Media)
- [在控制台上安装专用 CA 证书](console.md#Certs)
- [安装 Windows 10 和 Microsoft 团队聊天室控制台应用](console.md#Reimage)
- [控制台的初始设置](console.md#Initial)
- [Microsoft 团队会议室部署清单](console.md#Checklist)

> [!NOTE]
> Microsoft 团队聊天室仅适用于正确配置的 Microsoft 团队或 Skype for business 环境，在此环境中，设备帐户按照[部署 Microsoft 团队聊天室](room-systems-v2.md)中的说明正确设置。
  
## <a name="prepare-the-installation-media"></a>准备安装媒体
<a name="Prep_Media"> </a>

安装 Microsoft 团队聊天室控制台应用需要至少具有32GB 容量的 USB 存储设备。 设备上不应有任何其他文件;USB 存储上的任何现有文件都将丢失。
  
> [!NOTE]
> 未能根据这些说明创建 Microsoft 团队聊天室安装媒体可能会导致意外行为。

> [!NOTE]
> 下面的过程用于将安装媒体创建为映像新的 Microsoft 团队聊天室设备。 默认情况下，现有设备将从 Windows 更新和 Windows 应用商店自动更新。
  
1. 下载[CreateSrsMedia 脚本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。
3. 按照脚本说明创建 Microsoft 团队聊天室 USB 安装盘。


> [!TIP]
> 每次 CreateSrsMedia 脚本启动时，屏幕输出将包含该会话的日志文件或脚本的名称。 如果运行脚本时出现问题，请确保在请求支持时提供该脚本的副本。 

CreateSrsMedia 脚本自动执行以下任务：

1. 下载适用于 Microsoft 团队聊天室的最新 MSI 安装程序。
2. 确定用户必须提供的 Windows 的内部版本。 最新发布的版本可能会也可能不会经过测试，并且支持与 Microsoft 团队聊天室设备配合使用。
3. 下载必要的支持组件。
4. 在安装媒体上组装所需的组件。

需要特定版本的 Windows 10，并且此版本仅适用于批量许可客户。  您可以从[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/)获取副本。

完成后，从计算机中删除 USB 磁盘并继续[安装 Windows 10 和 Microsoft 团队聊天室控制台应用](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安装 Windows 10 和 Microsoft 团队聊天室控制台应用
<a name="Reimage"> </a>

您现在需要应用您创建的安装媒体。 目标设备将作为装置运行，并且默认用户将设置为仅运行 Microsoft 团队聊天室控制台应用。

1. 如果目标设备将安装在插接设备（如 Surface Pro）中，请断开其与坞站的连接。

2. 确保目标设备未连接到网络。

3. 确保目标设备已连接到交流电源。

4. 将您的 USB 安装盘插入到目标设备中。

5. 启动到 USB 安装盘。 请参阅制造商说明。 如果目标设备是 Surface Pro，请使用以下步骤启动到 USB 安装盘：

    a. 按下并继续按住音量（-）按钮。

    b. 按下并释放 "电源" 按钮。

    c. 启动 Windows 安装程序后，释放调低音量 (-) 按钮。

8. 安装完成后，系统将关闭。
    
系统关闭后，可以安全地删除 USB 安装盘。 此时，你可以将目标设备放置在其 dock 中（如果使用基于插接的产品），附加会议室所需的外围设备，并连接到网络。 请参阅制造商说明。

> [!NOTE]
> Microsoft 团队聊天室的软件更新会自动从 Microsoft Store for Business 下载。 请参阅[Microsoft Store For Business 和教育](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)版的先决条件，以验证聊天室控制台是否能够访问应用商店和自我更新。  

### <a name="selecting-a-language"></a>选择语言 

在创建者的更新中，你需要使用 ApplyCurrentRegionAndLanguage 脚本，其中隐式语言选择不向用户提供所需的实际应用程序语言（例如，他们希望控制台应用使用法语，但它将以英语提供。
  
> [!NOTE]
> 以下说明仅适用于使用 Windows 创建者更新创建的控制台。 未使用新预配系统的媒体设置的旧/市场系统将无法使用这些说明，但也不会受到需要此手动干预的初始问题（周年纪念版本允许你选择在安装程序中显式应用语言。
  
### <a name="to-apply-your-desired-language"></a>应用你需要的语言

1. 切换至管理模式。
    
2. 选择“开始”菜单。
    
3. 选择齿轮图标以启动“**设置**”应用。
    
4. 选择 **" &amp;时间语言**"。
    
5. 选择 **" &amp;地区语言**"。
    
6. 选择“**添加语言**”。
    
7. 选择要添加的语言。
    
8. 选择您刚刚添加到 "语言" 列表的语言。
    
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
    
您所需的语言现已应用于 Microsoft 团队聊天室控制台。
## <a name="initial-set-up-of-the-console"></a>控制台的初始设置
<a name="Initial"> </a>

安装 Windows 后，Microsoft 团队聊天室控制台应用将在下一次启动时转到其初始设置过程或选择了/reboot 选项。
  
1. 将显示“用户帐户”屏幕。 输入要与控制台一起使用的房间帐户的 Skype 登录地址（用户 @ 域格式）。
    
2. 输入会议室帐户的密码，再重新输入以进行确认。
    
3. 在 "配置域" 下，设置 Skype for business 服务器的 FQDN。 如果 Skype for Business SIP 域不同于用户的 Exchange 域，请在此字段中输入 Exchange 域。
    
4. 单击" **下一步**"。
    
5. 在 "功能" 屏幕上选择指示的设备，然后单击 "**下一步**"。 默认设置是“自动屏幕共享”设置为“开启”，“隐藏会议名称”设置为“关闭”。 要选择的设备为：
    
   - 用于会议的麦克风：此会议室的默认麦克风。
    
   - 用于会议的扬声器：用于此会议的默认扬声器。 
    
   - 默认扬声器：用于来自 HDMI 采集的音频的扬声器。
    
     每项都有供选择的选项下列菜单。你必须为每个设备做出选择。
    
6. 单击“**完成**”。
    
Microsoft 团队聊天室控制台应用应立即开始使用上面输入的凭据登录到 Skype for Business 服务器，还应开始使用这些相同的凭据与 Exchange 同步其日历。 有关使用控制台应用的详细信息，请参阅[Microsoft 团队聊天室帮助](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft 团队聊天室依赖于已验证的控制台硬件的存在。 即使在未检测到控制台硬件的情况中，即使创建了包含 Microsoft 团队聊天室控制台应用的正确创建的图像，也不会超过初始设置过程启动。 对于基于 Surface Pro 的解决方案，Surface Pro 必须连接到其随附的 dock 硬件才能传递此检查。
  
> [!NOTE]
> 某些非英语语言用户可能需要在初始设置过程中连接到控制台的物理键盘在触摸键盘上不支持符号的情况中。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在控制台上安装专用 CA 证书
<a name="Certs"> </a>

Microsoft 团队聊天室控制台需要信任其连接的服务器所使用的证书。 对于 O365 而言，会自动完成此操作，因为这些服务器使用的是公用证书颁发机构，Windows 10 自动信任这些证书颁发机构。 在证书颁发机构专用的情况下（例如，对于具有 Active Directory 和 Windows 证书颁发机构的内部部署），你可以通过以下几种方式将证书添加到 Microsoft 团队聊天室控制台：
  
- 你可以将控制台加入 Active Directory，并且将自动添加给定证书颁发机构的所需证书已发布到 Active Directory （常规部署选项）。
    
- 可以在映像过程后手动安装证书。 在执行此操作之前，必须完成[控制台的初始设置](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手动安装证书 

1. 将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。
    
2. 将控制台置于管理员模式下（请参阅[管理员模式和设备管理](room-systems-v2-operations.md#AdminMode)）。
    
3. 运行以下命令：
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 域（可选）
<a name="Certs"> </a>

你可以将 Microsoft 团队聊天室控制台加入到你的域。 Microsoft 团队聊天室控制台应放置在电脑工作站的单独 OU 中，因为许多工作站策略与 Microsoft 团队聊天室不兼容。 常见的示例是密码强制策略，可防止 Microsoft 团队聊天室自动启动。 有关 GPO 设置管理的信息，请参阅[管理 Microsoft 团队聊天室](room-systems-v2-operations.md)。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>将 Microsoft 团队会议室加入域

1. 从管理员帐户登录到控制台（请参阅[管理员模式和设备管理](room-systems-v2-operations.md#AdminMode)）。
    
2. 启动提升的 Powershell 命令提示符。
    
3. 在 Powershell 中输入以下命令：
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

例如，如果你的完全限定的域是 redmond.corp.microsoft.com，而你希望 Microsoft 团队聊天室控制台位于 "Microsoft 团队聊天室" OU 中，而该 OU 是 "Resources" OU 的子 ou，则该命令将是：
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果想要在将计算机加入到域时重命名该计算机，请使用-NewName 标志，后跟计算机的新名称。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft 团队会议室部署清单
<a name="Checklist"> </a>

在最终验证是否已完全配置了控制台及其所有外围设备时，请使用以下清单：
  
**应用程序设置**

|||
|:-----|:-----|
|☐  <br/> |在控制台屏幕的右上方正确显示会议室帐户名称和电话号码（如果已启用 PSTN）  <br/> |
|☐  <br/> |已正确设置 Windows 计算机名称（对于远程管理很有用）  <br/> |
|☐  <br/> |已设置并验证管理员帐户密码  <br/> |
|☐  <br/> |已应用所有固件更新  <br/> |
   
**音频/视频外设**

|||
|:-----|:-----|
|☐  <br/> |摄像头外围设备固件版本正确（如果适用）  <br/> |
|☐  <br/> |相机功能和定位最佳  <br/> |
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

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 团队聊天室](room-systems-v2.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
