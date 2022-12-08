---
title: 将 Teams 会议室设备注册到专业管理
author: altsou
ms.author: altsou
manager: serdars
ms.date: 09/28/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 将Teams 会议室设备加入 Pro Management 门户
f1keywords: ''
ms.openlocfilehash: f5994c5ced6097104ee74044ee2441bc8388f5c3
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307957"
---
# <a name="enroll-device-into-pro-management"></a>将设备注册到 Pro Management

部署需要将Microsoft Teams 会议室设备载入到Microsoft Teams 会议室专业版管理门户。 监视服务代理与经认证的Microsoft Teams 会议室 (MTR) 系统和外围设备一起使用。

## <a name="prerequisites"></a>先决条件

在尝试注册过程之前，请按照以下过程设置硬件：

### <a name="adding-proxy-settings-optional"></a> (可选) 添加代理设置

1. 以 [MTR 设备的管理员用户身份执行操作，以管理员身份](#performing-operations-as-the-admin-user-of-the-mtr-device)登录。
1. 在屏幕) 左下角 (“Windows **搜索** _”字段中，输入_ *cmd** (长按屏幕或右键单击，然后选择“ **_以管理员身份运行_** ”) 。
1. 运行以下命令， (命令末尾的双引号) 很重要：

   - 如果使用单 ***一代理服务器***： `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *例子：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - 如果使用 ***pac*** 文件： `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *例子：*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT http://contosoproxy.corp.net/proxy.pac
     ```

### <a name="enabling-tpm-settings"></a>启用 TPM 设置

> [!NOTE]
> 必须启用 TPM 才能在 Pro Management 中注册。

如果禁用了 Intel NUC 设备上的 TPM，请在这些设备上启用 TPM，如下所示：

1. 将键盘插入 NUC 设备。
1. 重启设备。
1. 若要显示 BIOS 屏幕，请快速按 **F2**。
1. 选择“ **高级**”。
1. 选择“ **安全性**”。
1. 在右侧的“安全功能”下，启用 **“Intel 平台信任技术**”。
1. 若要保存设置，请按 **F10**。
1. 在确认框中，选择“ **是**”。

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>以 MTR 设备的管理员用户身份执行操作

某些配置/安装过程要求以管理员身份登录到设备。

若要以管理员身份登录到设备， (本地管理员) ：

1. 确保挂起任何正在进行的呼叫并返回到主屏幕。
1. 在Microsoft Teams 会议室用户界面中，选择“**更多**”，然后选择 **“设置”**，系统会提示你在设备上输入本地管理员密码， (默认密码为 **_sfb_**) 。
1. 选择 **“设置”**，然后选择“  **Windows 设置”**  以本地管理员身份访问 Windows。

1. 从 Windows 登录屏幕中显示的用户列表中，选择  **“管理员** (”或设备) 的相应本地管理员。

> [!NOTE]
> 如果计算机 *已加入域*，请选择“ **其他用户**”，然后使用 **.\admin** 或设备中配置的本地管理员的用户名作为用户名。

若要在执行必要的管理任务后返回到 Microsoft Teams 会议室 应用，请执行以下操作：

1. 在 Windows ***“开始”菜单中***，从 管理员 帐户注销。
1. 通过选择屏幕最左侧的用户帐户图标，然后选择 **Skype**，返回到Microsoft Teams 会议室。

> [!NOTE]
> 如果未列出 Skype 用户，请选择“其他用户”并输入 ***.\skype*** 作为用户名，然后登录。

## <a name="urls-required-for-communication"></a>通信所需的 URL

 > [!NOTE]
 > MTR 设备代理与Microsoft Teams 会议室专业版管理门户之间的所有网络流量都是通过端口 443 的 SSL *。*  请参阅[Office 365 URL 和 IP 地址范围 - Microsoft 365 企业版 |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

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

1. 在Microsoft Teams 会议室专业版管理门户 [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)的左侧导航栏上，展开 **“设置”**，然后选择“**常规**”。
1. 在 *“注册会议室*”下，选择“ **下载安装程序**  ”以下载监视代理软件。
1. **选：** 设置代理的代理设置;请参阅 [ (可选) 添加代理设置](#adding-proxy-settings-optional)。
1. 在 MTR 设备上安装步骤 2) 中下载的代理安装程序 (，方法是在 MTR 设备上本地运行 MSI，或者通过将 MSI 应用程序大规模发布到环境中的设备 (组策略等) 
1. 会议室将在 5-10 分钟内显示在门户中。

   ![设置和自注册密钥的屏幕截图。](../media/software-installation-005new.png)

> [!NOTE]
> 如果需要在 MTR 上的 Teams 应用无法登录 Teams 的情况下安装代理，可以使用我们的注册密钥作为可选过程。 转到“？” (门户右上角的“帮助”) ，然后选择“下载密钥 (可选) ”。 安装代理时，请将以前从门户) 下载的“自注册密钥” (放在设备的 **C：\Rigel** 目录中。

## <a name="installation"></a>安装

从门户或使用上述) 提供的 AKA.ms URL 从 Microsoft (下载安装程序后，解压缩其内容以 **访问ManagedRoomsInstaller.msi** 文件。

有两种安装模式：1) 单个本地计算机安装，2 种) 大规模部署模式 (通常通过Intune类似的方法) 。 建议为未加入域的计算机或无法远程运行 MSI 安装程序的计算机单独安装。

由于客户可以通过多种不同的方式在大规模部署模式下运行 MSI 应用程序，本文档将介绍仅在单个模式下以及批量安装Intune注册的设备。

### <a name="individual-device-installation"></a>单个设备安装

1. 以管理员身份登录到设备。 确保遵循 *以设备管理员用户身份执行操作* 的步骤。

1. 将文件 **ManagedRoomsInstaller.msi** 复制到 MTR 设备。

   运行 ***ManagedRoomsInstaller.msi*** 时是“许可协议”屏幕。

1. 阅读协议后，选中“**我接受许可协议中的条款**”，然后按 _*Install**。

    这将开始Microsoft Teams 会议室专业版监视软件安装。 将显示提升 (以管理员身份运行的提示) 。

1. 选择“ **是**”。

    安装将继续。 在安装过程中，将打开一个控制台窗口，并开始Microsoft Teams 会议室专业版监视软件安装的最后阶段。

    > [!NOTE]
    > 不要关闭窗口。 安装完成后，向导会显示“完成”按钮。

### <a name="intune-enrolled-device-bulk-deployment"></a>Intune注册的设备批量部署

以下组件是成功安装的先决条件： 

- **Intune注册**：Windows 设备上的Teams 会议室必须已在 Intune 中注册。
  有关如何在 Intune 中的 Windows 设备上注册Teams 会议室的详细信息，请参阅[使用 Microsoft Endpoint Manager 在 Windows 设备上注册Microsoft Teams 会议室 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **将 Windows 设备上的所有Teams 会议室作为成员的 Azure AD 组** - 在 Azure AD 中创建的组，该组包括 Windows 设备上应属于Microsoft Teams 会议室高级版服务的所有Teams 会议室。 此组将用于针对 MTR Pro 代理的部署。
  
> [!NOTE]
> 为此，可以考虑在 Azure AD 中使用动态组，有关详细信息，请参阅[使用 Microsoft Endpoint Manager 在 Windows 设备上注册Microsoft Teams 会议室 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **下载 MTR Pro 代理****安装程序** – 从<https://aka.ms/serviceportalagentmsi>下载代理的 zip 文件，并将 zip (ManagedRoomsInstaller.msi) 的内容提取到本地临时文件夹。

**使用 Intune 进行安装**

1. 登录到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
1. 选择 **“应用** > **”“所有应用** > **添加**”。
1. 在 **“选择应用类型** ”窗格中的“ **其他** 应用类型”下，选择“ **业务线应用**”。
1. 单击 **“选择**”。 将显示 **“添加应用** ”步骤。 
1. 在 **“添加应用** ”窗格中，单击“ **选择应用包文件**”。
   1. 在 **“应用包文件** ”窗格中，选择“  **浏览**”。 然后，选择之前下载 **的ManagedRoomsInstaller.msi** 文件， (请参阅) 先决条件部分。
   1. 完成后，在“**应用包文件**”窗格中选择“**确定**”以添加应用。
1. 在 **“应用信息** ”页中，执行以下更改：
   1. 发布者：输入 **Microsoft Corporation**。
   1. 忽略应用版本：选择“ **是**”。

      > [!NOTE]
      > MTR Pro 代理正在自行更新;因此，应显式忽略应用版本， (任何基线版本都可以) 自动更新。

   1.  (可选) 类别：选择 **“计算机管理**”。
   
1. 单击“ **下一步** ”以显示 **“分配”** 页。
   1. 在“ **必需** ”部分下，单击“ **+ 添加组** ”，将一组设备作为安装代理的目标。
   1. 在 **“选择组** ”窗格中，在“搜索”框中键入组名称 (引用上述) 先决条件，然后单击所需 **组** 并单击“ **选择**”。
      有关详细信息，请参阅[添加组以组织用户和设备](https://go.microsoft.com/fwlink/?linkid=2202166)，以及[使用Microsoft Intune将应用分配到组](https://go.microsoft.com/fwlink/?linkid=2202270)。
1. 单击“ **下一步** ”以显示“ **查看 + 创建** ”页。
1. 查看为应用输入的值和设置。 完成后，单击“**创建**”将应用添加到Intune。

完成此过程后，设备将在几分钟后开始安装 MTR Pro 代理。

> [!NOTE]
> 安装后，MTR Pro 代理可能需要长达 8 小时才能执行最新版本的自我更新，并在 MTR Pro 门户中列出。
若要加快 MTR Pro 门户中的自动注册速度，请考虑在代理部署后重启 MTR 设备。

## <a name="completing-enrollment"></a>完成注册

安装完成后，请等待 5-10 分钟，然后刷新门户以查看列表中的设备，报告为 *“正在载入* ”状态。

处于 *“载入”* 状态时，将显示和更新会议室的状态，但不会引发任何警报或创建调查票证。

选择聊天室，然后选择 **“注册”**  以开始接收事件警报。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>取消注册和卸载监视软件

若要取消注册设备，请从 MTR 设备中删除监视代理，如下所示：

1. 在受监视的设备上，以管理员身份登录设备。 请务必按照以 *设备管理员用户身份执行操作* 中的步骤操作。
1. 从 [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding) 下载重置脚本。
1. 提取设备上的某个位置的脚本，并复制路径。
1. 以管理员身份打开 PowerShell：在屏幕) 左下角 (“Windows **搜索** _”字段中输入“Powershell”，然后右键单击_*_Windows PowerShell_**。
1. 选择 *“以管理员身份运行”* 并接受 UAC 提示。
1. 输入 *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* ，然后在下一个提示符下按 **Y** 。
1. 将解压缩的卸载脚本的完整路径粘贴或键入到 PowerShell 窗口中，然后按 **Enter**。

   示例：

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   此命令将设备重置为用户标准 MTR 更新，并删除 MTR Pro 监视代理和文件。

1. 在Microsoft Teams 会议室专业版管理门户的左侧菜单中，选择“**会议室**”。
1. 在提供的房间列表中，选择要取消注册的会议室，然后选择“ **取消注册** ”以停止获取事件警报或调查票证，或报告会议室的事件。

## <a name="troubleshooting-table"></a>故障排除表

> [!NOTE]
> 所有Microsoft Teams 会议室专业版监视错误都记录在名为 **Microsoft 托管会议室** 的特定事件日志文件中。

***应用程序运行时日志文件位置*** =

C：\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log，其中 **x.x.x** 是应用版本号。

|症状|建议的过程|
|---|---|
|你会收到一条错误消息，指出： </p><p> ***错误：请使用_ 运行此应用程序** <br> _ *_elevated 特权_**|使用升级的权限运行应用程序，然后重试。|
|||
|你会收到一条错误消息，指出： </p><p> ***找不到 TPM 数据***|确保设备的 BIOS 中已打开 TPM (受信任的平台模块) 。 这通常在设备 BIOS 的安全设置中找到。|
|||
|你会收到一条错误消息： </p><p> ***错误：找不到名为“管理员”或“Skype”的本地用户帐户***|确保用户帐户存在于经过认证的Microsoft Teams 会议室系统设备上。|
|||
|你会收到上述未涵盖的任何错误状态消息。|请向 Microsoft Teams 系统支持代理提供安装日志的副本。|
