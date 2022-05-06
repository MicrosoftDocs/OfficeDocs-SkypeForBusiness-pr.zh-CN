---
title: 将 Teams 会议室设备注册到托管服务
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
description: 将Teams 会议室载入到托管服务
f1keywords: ''
ms.openlocfilehash: 4261e93a7bfab5d21620f8dbb327575352062c86
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2022
ms.locfileid: "63689093"
---
# <a name="enroll-device-into-managed-service"></a>将设备注册到托管服务

部署需要将Microsoft Teams 会议室载入到Microsoft Teams 会议室服务。 监视服务代理用于经认证的 Microsoft Teams ROOM (或) 和外围设备。

## <a name="prerequisites"></a>先决条件

在尝试注册过程之前，请按照以下过程设置硬件：

### <a name="adding-proxy-settings-optional"></a>添加代理设置 (可选) 

1. 按照以管理用户角色 [执行一些操作来登录作为 ADMINISTRATOR 设备的管理员](#performing-operations-as-the-admin-user-of-the-mtr-device)。
1. 在屏幕) 左下Windows ***Search** _ 字段 (中，输入 _ *cmd** (长按屏幕或右键选择，然后选择"以管理员角色运行") 。****  
1. 运行以下命令 (命令末尾的双引号) ：
   - 如果使用单个 ***代理服务器***：bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>：<port> ""

      *示例：* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
      

   - 如果使用 pac ***文件*** ：bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>

      
      *示例：* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
      

### <a name="enabling-tpm-settings"></a>启用 TPM 设置

> [!NOTE]
> 必须启用 TPM 以在托管服务中注册。

如果 Intel NUC 设备上禁用了 TPM，请在这些设备上启用 TPM，如下所示：  

1. 将键盘插入 NUC 设备。  
1. 重启设备。  
1. 若要显示 BIOS 屏幕，请快速按 **F2**。  
1. 选择" **高级"**。  
1. 选择" **安全性"**。  
1. 在"安全功能"下的右侧，启用 **"Intel 平台信任技术"**。  
1. 若要保存设置，请按 **F10**。  
1. 在确认框中，选择" **是"**。 
## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>以一名管理用户（作为一名用户）执行一些操作

某些配置/安装过程要求以管理员角色登录到设备。

若要以管理员或本地管理员 (登录到设备) ：

1. 确保挂断任何正在进行的呼叫并返回到主屏幕。
1. 在 Microsoft Teams 会议室用户界面中，选择"更多"，然后选择 **"设置**"，其中会提示输入设备的本地管理员密码 (默认密码是 **_sfb_**) 。
1. 选择 **设置**，然后选择"**Windows 设置**"以Windows管理员角色访问访问权限。  

1. 在登录屏幕中显示的用户Windows，选择"管理员" (或设备登录的相应的本地) 。

> [!NOTE]
> 如果计算机已 *加入域，* 请选择"其他用户"，然后使用 **.\admin** 或设备中配置的本地管理员的用户名作为用户名。  

若要在执行必要的管理Microsoft Teams返回到"会议室"应用：

1. 从Windows ***"开始"菜单***，从管理员帐户注销。
1. 选择Microsoft Teams最左侧的用户帐户图标，然后选择"Skype"，返回到 **Skype。**

> [!NOTE]
> 如果未Skype用户，请选择"其他用户"并输入 ***.\skype*** 作为用户名，然后登录。

 

## <a name="urls-required-for-communication"></a>通信所需的 URL

 > [!NOTE]
 > 在一个端口 443 上，在"一些 MICROSOFT TEAMS 会议室 - 托管服务服务门户之间的所有网络流量都是 SSL *。*  请参阅[Office 365 URL 和 IP 地址范围 - Microsoft 365 企业版 |Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true)。

如果在企业环境中启用了流量允许列表，则必须允许以下主机：

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

1. 在"服务 - 托管 [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)服务Microsoft Teams 会议室左侧导航栏上，展开设置并选择 **"** 常规 **"**。  
1. 在 *"注册聊天室"* 下 **，选择"下载安装程序**  "以下载监视代理软件。
1. **可选：** 设置代理的代理设置;请参阅 [添加代理设置 (可选)](#adding-proxy-settings-optional)。
1. 安装代理安装程序 (在步骤 2) 中下载的，可通过在一台一台或一台一般的方式将 MSI 应用程序发布到环境 (Group-Policy 等)   
1. 会议室在 5-10 分钟内显示在门户中。 如果没有，请联系 managedroomsupport@microsoft.com。  

   ![设置和自注册密钥的屏幕截图。](../media/software-installation-005new.png)
 
> [!NOTE]
> 如果需要在未安装 TEAMS APP 的情况下安装代理，TEAMS注册密钥作为可选过程。 转到"？"。 (门户) 右上角的"帮助"，然后选择"下载密钥 (可选) "。 安装代理时，将以前从门户 (下载的"自注册密钥") 放在设备的" **C：\Rigeldirectory** "上。

## <a name="installation"></a>安装

从 Microsoft 门户下载安装程序 (通过门户或上面提供的 AKA.ms URL) ，解压缩其内容以访问文件 **ManagedRoomsInstaller.msi。**

有两种安装模式：1) 单个本地计算机安装，2) 大规模部署模式 (通常通过类似方法的组策略) 。 建议为未加入域的计算机或无法远程运行 MSI 安装程序的计算机单独安装。  

由于客户可以在大规模部署模式下运行 MSI 应用程序的方式多种多样，本文档仅介绍如何在单个模式下安装。  
## <a name="individual-devicemdashdomain-joined-walkthrough"></a>单个 DeviceDomain&mdash; 联接演练

1. 以管理员角色登录到设备。 确保 *遵循以设备管理员用户角色执行* 操作的步骤。

1. 将 **文件ManagedRoomsInstaller.msi** 到"公司"设备。

   运行时 ***ManagedRoomsInstaller.msi*** 是"许可协议"屏幕。

1.  阅读协议后，选中 "**我接受** 许可协议_ 中的条款"，然后按 _*Install**。  

    此时会开始Microsoft Teams 会议室 - 托管服务监视软件安装。 系统会显示以管理员 (运行提升) 提示。

 1. 选择" **是"**。

    安装将继续。 在安装过程中，控制台窗口将打开，并开始安装Microsoft Teams 会议室 - 托管服务监视软件安装。  

    > [!NOTE]
    > 不要关闭窗口。 安装完成后，向导会显示"完成"按钮。

## <a name="completing-enrollment"></a>完成注册

安装完成后，请等待 5-10 分钟，刷新门户，设备将列出，并报告为 *载入* 状态。

在 *载入* 状态中，将显示并更新聊天室的状态，但它不会引发任何警报或创建调查票证。

选择会议室并选择" **注册"**  以开始获取事件警报、调查票证或报告事件。

如果有任何疑问或问题，请在门户中打开客户报告的事件或联系 managedroomsupport@microsoft.com。

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>取消注册和卸载监视软件

若要取消注册设备，请从一个监控代理设备中删除，如下所示：

1. 在受监视的设备上，以管理员角色登录设备。 请务必按照以设备的管理员用户角色 *执行操作中的步骤操作*。
1. 从文件下载重置 [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding)。
1. 解压缩设备上某处的脚本并复制路径。
1. 以管理员Windows打开 PowerShell：在屏幕) 左下角的"Windows ***Search** (_ 字段"中，输入"Powershell"，并右键单击"_*Windows PowerShell _"_**。
1. 选择 *"以管理员角色运行"并接受* UAC 提示。
1. 输入 *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* ，然后在下一个 **提示符下按 Y** 。  
1. 将解压缩的板载脚本的完整路径粘贴或键入到 PowerShell 窗口中，然后按 **Enter**。

   示例：

   *C：\Users\admin\Downloads\MTRPDeviceOffboarding\_\_\一Offboarding.ps1\_\_*  

   这会将设备重置为用户标准版、使用标准版、更新，并删除"一次"，并删除"一开始"的"一个"监视代理和文件。

1. 在"服务 - 托管服务Microsoft Teams 会议室的左侧菜单中，选择"会议室 **"**。  
1. 在提供的聊天室列表中，选择要取消注册的聊天室，然后选择"取消注册"以停止获取事件警报或调查票证，或报告聊天室的事件。

## <a name="troubleshooting-table"></a>故障排除表

> [!NOTE]
> 所有Microsoft Teams 会议室 – 托管服务监视错误都记录在名为 Microsoft 托管聊天室的特定 **事件日志文件中**。 

### <a name="application-runtime-log-file-location-"></a>***应用程序运行时日志文件位置*** =  

C：\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortalVerboseLogFile.log\_\_，其中 **x.x.x** 是应用版本号。

|**症状**  |**建议的过程**  |
| :- | :- |
|<p>你收到一条错误消息，指出   </p><p>***错误：请使用_ 运行此应用程序** </p><p>_ *_提升的权限_**  </p>|使用提升的权限运行应用程序，然后重试  |
|  |  |
|<p>你收到一条错误消息，指出   </p><p>***找不到 TPM 数据***  </p>|确保设备已在其 BIOS (TPM) 平台模块。 这通常位于设备 BIOS 的安全设置中  |
|  |  |
|<p>收到错误消息  </p><p>` `***错误：找不到名为"Admin"或"Skype"的本地用户帐户***  </p>|确保用户帐户存在于经过认证的会议室Microsoft Teams设备上。  |
|  |  |
|你收到上面未涵盖的任何错误消息  |请向系统支持代理提供安装Microsoft Teams的副本。 |