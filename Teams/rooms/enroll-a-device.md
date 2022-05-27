---
title: 将Teams会议室设备注册到托管服务
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 将Teams 会议室设备载入托管服务
f1keywords: ''
ms.openlocfilehash: d40daed54a04ca7d9949ecc63f57c379aee6b666
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675784"
---
# <a name="enroll-device-into-managed-service"></a>将设备注册到托管服务

部署需要将Microsoft Teams 会议室设备载入到Microsoft Teams 会议室托管服务。 监视服务代理用于经认证的Microsoft Teams会议室 (地铁) 系统和外围设备。

## <a name="prerequisites"></a>先决条件

在尝试注册过程之前，请按照以下过程设置硬件：

### <a name="adding-proxy-settings-optional"></a> (可选) 添加代理设置

1. 以管理员身份登录，将[执行操作作为 MTR 设备的管理员用户](#performing-operations-as-the-admin-user-of-the-mtr-device)进行操作。
1. 在屏幕)  (左下部分的Windows ***Search** _字段中，输入 _ *cmd** (长按屏幕或右键选择，然后选择 **_“以管理员身份运行_**) ”。
1. 在命令结束时运行以下命令 (双引号非常重要) ：

   - 如果使用单个 ***代理服务器***： `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *例子：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - 如果使用 ***pac*** 文件： `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *例子：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>启用 TPM 设置

> [!NOTE]
> 必须启用 TPM 才能注册托管服务。

如果禁用了 Intel NUC 设备上的 TPM，请在这些设备上启用 TPM，如下所示：

1. 将键盘插入 NUC 设备。
1. 重启设备。
1. 若要显示 BIOS 屏幕，请快速按 **F2**。
1. 选择 **“高级**”。
1. 选择 **“安全性**”。
1. 在安全功能下方的右侧，启用 **Intel 平台信任技术**。
1. 若要保存设置，请按 **F10**。
1. 在确认框中，选择 **“是**”。

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>作为 MTR 设备的管理员用户执行操作

某些配置/安装过程要求你以管理员身份登录到设备。

以管理员身份登录到设备 (本地管理员) ：

1. 确保挂起任何正在进行的呼叫并返回到主屏幕。
1. 在Microsoft Teams会议室用户界面中，选择 **“更多**”，然后选择 **设置**，系统会提示你在设备上输入本地管理员密码， (默认密码为 **_sfb_**) 。
1. 选择 **设置**，然后选择 **Windows 设置** 以本地管理员身份访问Windows。

1. 从Windows登录屏幕中显示的用户列表中，选择 **“管理员**” (或设备) 的相应本地管理员。

> [!NOTE]
> 如果计算机 *已加入域*，请选择 **“其他用户**”，然后使用 **.\admin** 或设备中配置为用户名的本地管理员的用户名。

执行必要的管理任务后返回到 Microsoft Teams Room 应用：

1. 从Windows ***"开始"菜单***，从管理员帐户注销。
1. 通过选择屏幕最左侧的用户帐户图标，然后选择Skype，返回到 **Microsoft Teams** 会议室。

> [!NOTE]
> 如果未列出Skype用户，请选择“其他用户”并输入 ***.\skype*** 作为用户名，然后登录。

## <a name="urls-required-for-communication"></a>通信所需的 URL

 > [!NOTE]
 > MTR 设备代理和 Microsoft Teams 会议室 - 托管服务门户之间的所有网络流量都是通过端口 443 的 SSL *。*  请参阅[Office 365 URL 和 IP 地址范围 - Microsoft 365 企业版 |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

如果在企业环境中启用了 **流量允许列表** ，则必须允许以下主机：

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>注册过程

注册过程涉及以下步骤：

1. 在 Microsoft Teams 会议室 - 托管服务门户的左侧导航栏上 [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)，展开 **设置** 并选择 **“常规**”。
1. 在 *“注册会议室*”下，选择 **“下载安装程序**  ”以下载监视代理软件。
1. **选：** 设置代理的代理设置;请参阅 [ (可选) 添加代理设置](#adding-proxy-settings-optional)。
1. 安装代理安装程序 (下载在地铁设备上的第 2 步) 中，方法是：在地铁设备上本地运行 MSI，或者通过将 MSI 应用程序大规模发布到环境中的设备的正常方式 (组策略等) 
1. 会议室在 5-10 分钟内显示在门户中。 如果没有，请联系 managedroomsupport@microsoft.com。

   ![设置和自注册密钥的屏幕截图。](../media/software-installation-005new.png)

> [!NOTE]
> 如果需要安装代理，而不使用 MTR 上的Teams应用登录到Teams，则可以使用我们的注册密钥作为可选过程。 转到“？” (门户右上角的“帮助) ”，然后选择“下载密钥 (可选) ”。 安装代理时，请将之前从门户下载的“自注册密钥” () 放在设备 **的 C：\Rigel** 目录上。

## <a name="installation"></a>安装

从门户或使用上述) 提供的 AKA.ms URL 从 Microsoft (下载安装程序后，解压缩其内容以访问文件 **ManagedRoomsInstaller.msi**。

有两种安装模式：1) 个本地计算机安装，2 个) 大规模部署模式通常通过类似方法) 的组策略 (。 建议对未加入域的计算机或无法远程运行 MSI 安装程序的计算机进行单独安装。

由于客户可以通过多种方式在大规模部署模式下运行 MSI 应用程序，本文档仅逐步讲解单个模式下的安装。

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>单个设备&mdash;已加入域的演练

1. 以管理员身份登录到设备。 确保 *按照设备步骤的管理员用户执行操作*。

1. 将文件 **ManagedRoomsInstaller.msi** 复制到 MTR 设备。

   运行 ***ManagedRoomsInstaller.msi*** 时，会显示“许可协议”屏幕。

1. 阅读协议后，检查***我接受许可协议中的条款**，然后按 _*Install**。

    这将开始Microsoft Teams 会议室 – 托管服务监视软件安装。 显示以管理员身份运行的提升 (提示) 。

1. 选择 **“是**”。

    安装将继续。 在安装过程中，将打开控制台窗口，并开始Microsoft Teams 会议室 - 托管服务监视软件安装的最后阶段。

    > [!NOTE]
    > 请勿关闭窗口。 安装完成后，向导将显示“完成”按钮。

## <a name="completing-enrollment"></a>完成注册

安装完成后，等待 5-10 分钟并刷新门户，设备将列出，报告为 *载入* 状态。

在 *载入* 状态下，会显示和更新会议室的状态，但不会引发任何警报或创建调查票证。

选择会议室，然后选择 **“注册**  ”以开始获取事件警报、调查票证或报告事件。

对于任何问题，请在门户中打开客户报告的事件，或联系 managedroomsupport@microsoft.com。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>取消注册和卸载监视软件

若要取消注册设备，请从 MTR 设备中删除监视代理，如下所示：

1. 在受监视的设备上，以管理员身份登录设备。 请务必按照 *作为设备管理员用户执行操作的* 步骤操作。
1. 从 [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding) 下载重置脚本。
1. 在设备上的某个位置提取脚本并复制路径。
1. 以管理员身份打开 PowerShell：在屏幕) 的Windows ***Search** _字段 (左下部分，输入“Powershell”，然后右键单击 “_*_Windows PowerShell_**”。
1. 选择 *“以管理员身份运行”* 并接受 UAC 提示。
1. 输入 *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* ，然后在下一个提示符下按 **Y** 。
1. 将解压缩的离载脚本的完整路径粘贴或键入到 PowerShell 窗口中，然后按 **Enter**。

   示例：

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   此命令将设备重置为用户标准 MTR 更新，并删除 MTRP 监视代理和文件。

1. 在Microsoft Teams 会议室 - 托管服务门户的左侧菜单中，选择 **“会议室**”。
1. 在提供的会议室列表中，选择要取消注册的房间，然后选择 **“取消注册”** 以停止获取事件警报或调查票证，或报告会议室的事件。

## <a name="troubleshooting-table"></a>故障排除表

> [!NOTE]
> 所有Microsoft Teams 会议室 – 托管服务监视错误记录在名为 **Microsoft 托管会议室** 的特定事件日志文件上。

***应用程序运行时日志文件位置*** =

C：\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log，其中 **x.x.x** 是应用版本号。

|症状|建议的过程|
|---|---|
|你会收到一条错误消息，指出： </p><p> ***错误：请使用_ 运行此应用程序** <br> _ *_elevated privileges_**|使用升级的权限运行应用程序，然后重试。|
|||
|你会收到一条错误消息，指出： </p><p> ***找不到 TPM 数据***|确保设备在其 BIOS 中启用了 TPM (受信任的平台模块) 。 这通常在设备 BIOS 的安全设置中找到。|
|||
|你会收到一条错误消息： </p><p> ***错误：找不到名为“管理员”或“Skype”的本地用户帐户***|确保用户帐户存在于经过认证的Microsoft Teams会议室系统设备上。|
|||
|你将收到上述未涵盖的任何错误状态消息。|请向Microsoft Teams系统支持代理提供安装日志的副本。|
