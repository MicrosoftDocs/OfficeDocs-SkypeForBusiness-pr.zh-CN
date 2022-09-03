---
title: 生成Microsoft Teams 会议室映像
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文介绍如何设置和配置Microsoft Teams 会议室控制台及其外围设备。
ms.openlocfilehash: 40d49597ab3354eeaacc8d7c562917fbf653e727
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590169"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>生成Microsoft Teams 会议室映像

本文介绍如何为大规模部署Teams 会议室生成Microsoft Teams 会议室映像。

> [!NOTE]
> 只有在为大规模部署创建 [基于 WIM 的映像](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) 时，才应使用以下步骤。 如果要恢复单个设备，请联系原始设备制造商 (OEM) 以获取支持。

仅当已创建和测试必要的 Microsoft Teams 或 Skype for Business 和 Exchange 帐户时，才应执行这些步骤，如[部署Microsoft Teams 会议室](rooms-deploy.md)中所述。 需要Microsoft Teams 会议室要求中所述[的](requirements.md)硬件和软件。 本主题包括以下部分：
  
- [准备安装媒体](console.md#Prep_Media)
- [在控制台上安装专用 CA 证书](console.md#Certs)
- [安装Windows 10和Microsoft Teams 会议室控制台应用](console.md#Reimage)
- [控制台的初始设置](console.md#Initial)
- [Microsoft Teams 会议室部署清单](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>准备安装媒体
<a name="Prep_Media"> </a>

安装Microsoft Teams 会议室控制台应用需要具有至少 32GB 容量的 USB 存储设备。 设备上不应有其他文件;USB 存储上的任何现有文件都将丢失。
  
> [!NOTE]
> 未能根据这些说明创建Microsoft Teams 会议室安装媒体可能会导致意外行为。

> [!NOTE]
> 下面的过程是创建安装介质以映像新Microsoft Teams 会议室设备。 默认情况下，现有设备会从 Windows 更新 和 Windows 应用商店自动更新。

> [!IMPORTANT]
> 用于创建Microsoft Teams 会议室安装介质的Windows 10计算机必须位于与目标安装介质相同的或更高版本的 Windows 上。
  
1. 下载 [CreateSrsMedia.ps1脚本](https://go.microsoft.com/fwlink/?linkid=867842)。
2. 在 Windows 10 计算机上，在提升的提示符下运行 CreateSrsMedia.ps1 脚本。
3. 按照脚本的说明创建Microsoft Teams 会议室 USB 安装磁盘。


> [!TIP]
> 每次启动CreateSrsMedia.ps1脚本时，屏幕输出将包括日志文件的名称或会话的脚本。 如果运行脚本时出现问题，请确保在请求支持时提供该脚本的副本。 

CreateSrsMedia.ps1脚本自动执行以下任务：

1. 下载适用于Microsoft Teams 会议室的最新 MSI 安装程序。
2. 确定用户必须提供的 Windows 的内部版本。 最近发布的版本可能或未经过测试，并且支持用于Microsoft Teams 会议室设备。
3. 下载必要的支持组件。
4. 在安装介质上组装所需的组件。

> [!NOTE]
需要特定版本的Windows 10，并且此版本仅适用于批量许可客户。  可以从 [批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/)获取副本。

完成后，从计算机中删除 USB 磁盘，然后继续[安装Windows 10和Microsoft Teams 会议室控制台应用](console.md#Reimage)。

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>安装Windows 10和Microsoft Teams 会议室控制台应用
<a name="Reimage"> </a>

现在需要应用已创建的安装媒体。 目标设备将作为设备运行，默认用户将设置为仅运行Microsoft Teams 会议室应用。

1. 如果目标设备将安装在停靠 (（例如Surface Pro) ）中，则将其与停靠台断开连接。

2. 确保目标设备未连接到网络。

3. 确保目标设备已连接到 AC 电源。

4. 将 USB 安装磁盘插入目标设备。

5. 启动到 USB 安装磁盘。 请参阅制造商说明。 如果目标设备是Surface Pro，请使用以下步骤启动到 USB 安装磁盘：

    a. 按住并继续按住卷 () 按钮。

    b. 按下并释放电源按钮。

    c. 启动 Windows 安装程序后，释放调低音量 (-) 按钮。

8. 安装完成后，系统将关闭。
    
系统关闭后，可以安全地删除 USB 设置磁盘。 此时，如果使用基于码头的产品) 、附加会议室所需的外围设备并连接到网络，则可以将目标设备放置在其停靠 (中。 请参阅制造商说明。

> [!NOTE]
> Microsoft Teams 会议室的软件更新会自动从适用于企业的 Microsoft Store下载。 请参阅[适用于企业的 Microsoft Store和教育的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)，验证会议室控制台是否能够访问商店和自我更新。  

### <a name="selecting-a-language"></a>选择语言 

在 Creator 的更新中，你需要在隐式语言选择不为用户提供所需的实际应用程序语言的情况下使用ApplyCurrentRegionAndLanguage.ps1脚本 (例如，他们希望控制台应用以法语出现，但它以英语) 出现。
  
> [!NOTE]
> 以下说明仅适用于使用 Windows Creator 的更新 (Windows 10 20H1) 或更高版本创建的控制台。
  
### <a name="to-apply-your-desired-language"></a>应用你需要的语言

1. 切换至管理模式。
    
2. 选择“开始”菜单。
    
3. 选择齿轮图标以启动“**设置**”应用。
    
4. 选择 **时间 &amp; 语言**。
    
5. 选择 **语言**。
    
6. 选择“**添加语言**”。
    
7. 选择要添加的语言。
    
8. 安装语言功能。
    
9. 请勿检查“设置为我的 Windows 显示语言”。
    
10. 选择 **“安装**”。
    
11. 选择刚添加到“语言”列表中的语言。
    
12. 设置为默认 - 向上移动箭头以设置默认值

13. 对于要删除的任何语言：
    
    a. 选择要删除的语言。
    
    b. 选择“删除”。

14. 启动提升的命令提示符。

15. 运行以下命令： 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. 重新启动系统。
    
所需语言现已应用于Microsoft Teams 会议室控制台。
## <a name="initial-set-up-of-the-console"></a>控制台的初始设置
<a name="Initial"> </a>

安装 Windows 后，Microsoft Teams 会议室应用将进入其初始安装过程。
  
1. 将显示“用户帐户”屏幕。 输入要与控制台一起使用的会议室帐户) user@domain格式的 Microsoft Exchange 资源帐户登录地址 (。
    
2. 输入会议室帐户的密码，再重新输入以进行确认。
   
3. 选择支持的会议模式 - 仅限 Microsoft Teams、仅Skype for Business或两个混合模式选项之一。 如有必要，请启用新式身份验证。

4. 选择 **“下一步**”。
    
5. 如果使用Skype for Business，并且Skype for Business SIP 域与用户的 Exchange 域不同，请在“高级”部分为Skype for Business Server设置 FQDN。 如果未使用Skype for Business或 SIP 域与 Exchange 域匹配，请将此部分留空。
6. 选择 **“下一步**”。
    
7. 选择 **“完成**”。
    
Microsoft Teams 会议室应用应使用上面输入的凭据登录到 Microsoft Teams 或Skype for Business Server，还应开始使用这些相同的凭据将其日历与 Exchange 同步。 有关使用Teams 会议室的详细信息，请参阅[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。
  
> [!IMPORTANT]
> Microsoft Teams 会议室依赖于已认证的控制台硬件。 即使包含Microsoft Teams 会议室控制台应用的正确创建映像也不会通过初始设置过程启动，除非检测到控制台硬件。 对于基于Surface Pro的解决方案，必须将Surface Pro连接到其随附的码头硬件才能通过此检查。 有关受支持的硬件的详细信息，请[参阅Microsoft Teams 会议室要求](requirements.md)。
  
> [!NOTE]
> 如果触摸键盘上不支持符号，某些非英语用户可能需要在初始设置期间连接到控制台的物理键盘。
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>在控制台上安装专用 CA 证书
<a name="Certs"> </a>
> [!NOTE]
> 仅当将Teams 会议室连接到Skype for Business时，才适用以下内容。

Microsoft Teams 会议室需要信任其连接到的服务器使用的证书。 如果证书颁发机构是专用的，例如使用 Active Directory 和 Windows 证书颁发机构进行本地部署，可以通过几种方式将证书添加到Microsoft Teams 会议室：
  
- 可以将控制台加入 Active Directory，并且会自动添加所需的证书，因为证书颁发机构已发布到 Active Directory (正常部署选项) 。
    
- 可以在映像过程后手动安装证书。 在执行此操作之前，必须完成 [控制台的初始设置](console.md#Initial)。
    
### <a name="to-manually-install-the-certificate"></a>手动安装证书 

1. 将 CA 证书下载到你的计算机，并将其保存到“C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer”。
    
2. 将控制台置于管理模式 (查看[管理员模式和设备管理](rooms-operations.md#AdminMode)) 。
    
3. 运行以下命令：
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>加入 Active Directory 域 (可选) 
<a name="Certs"> </a>

可以将Microsoft Teams 会议室加入域。 Microsoft Teams 会议室应放置在电脑工作站的单独 OU 中，因为许多工作站策略与Microsoft Teams 会议室不兼容。 常见示例是密码强制策略，可防止Microsoft Teams 会议室自动启动。 有关 GPO 设置管理的信息，请参阅[“管理Microsoft Teams 会议室](rooms-operations.md)”。
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>将Microsoft Teams 会议室加入域

1. 从管理员帐户登录控制台 (查看[管理员模式和设备管理](rooms-operations.md#AdminMode)) 。
    
2. 启动提升的 Powershell 命令提示符。
    
3. 在 Powershell 中输入以下命令：
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

例如，如果完全限定的域 redmond.corp.microsoft.com，并且希望Microsoft Teams 会议室控制台位于“Microsoft Teams 会议室”OU 中，而该 OU 是“Resources”OU 的子级，则命令将为：
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 如果要在将计算机加入域时重命名计算机，请使用 -NewName 标志，后跟计算机的新名称。
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 会议室部署清单
<a name="Checklist"> </a>

执行最终验证控制台及其所有外围设备是否已完全配置时，请使用以下清单：
  
**应用程序设置**

|完成 |检查 |
|:-----:|:-----|
|☐   |如果正确显示启用了 PSTN 的) ，则会议室帐户名称和电话 # (   |
|☐   |已正确设置 Windows 计算机名称（对于远程管理很有用）   |
|☐   |已设置并验证管理员帐户密码   |
|☐   |已应用所有固件更新   |
   
**音频/视频外围设备**

|完成 |检查 |
|:-----:|:-----|
|☐   |摄像头外围设备固件版本正确（如果适用）   |
|☐   |相机功能和定位最佳   |
|☐   |将用于播放默认设备和播放默认通信设备的设置设为预期的音频外围设备   |
|☐   |将用于录制默认通信设备的设置设为预期的音频外围设备   |
|☐   |音频外围设备固件版本正确（如果适用）   |
|☐   |音频输入设备工作正常且位置最佳   |
|☐   |音频输出设备工作正常且位置最佳   |

**控制台**

|完成 |检查 |
|:-----:|:-----|
|☐   |电缆是安全的且未收缩   |
|☐   |通过 HDMI 进行的音频采集工作正常   |
|☐   |通过 HDMI 进行的视频采集工作正常   |
|☐   |控制台可以自由旋转   |



   
## <a name="see-also"></a>另请参阅
<a name="Checklist"> </a>

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
