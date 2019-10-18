---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573645"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 会议室恢复工具
 
本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。 当 Microsoft 团队聊天室控制台显示 "系统配置已过期" 错误时，你将使用此工具。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>先决条件

下载最新的[Microsoft 团队聊天室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其解压缩到 Microsoft 团队聊天室设备可访问的 USB 记忆棒或网络共享。

您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>验证 Windows 版本 

1. 通过转到 "**设置"> Windows 设置 "> 管理员**从 Microsoft 团队聊天室设备登录，登录到管理员帐户。 此选项可将您带入 "登录" 屏幕。
2. 登录到管理员帐户， `admin`使用密码`sfb`的默认管理员帐户。
3. 单击 "开始" 菜单并在`winver.exe`搜索框中键入，然后在结果中单击 "**运行命令*"。
4. 记下 "信息" 窗格第二行中 "版本" 之后的数字。

>[!NOTE]
>如果显示的版本是1607或更早版本，请在 proceding 之前的<a href="#Windows-up">更新窗口</a>中的步骤，然后再<a href="#Perform">执行恢复</a>步骤。 如果显示的版本大于1607，请仅按照<a href="#Perform">执行恢复</a>中的步骤操作。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>恢复之前更新 Windows （如果需要）

1. 当仍以管理员用户身份登录时，请启动提升的 Powershell 提示。
2. 运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。
3. 运行 windows 更新并安装适用于 Windows 1709 的更新。
4. 更新到1709后，请重新登录到管理员帐户并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。 更新可能是通过链接或使用 Windows 更新完成的。
5. 作为可选步骤，请安装 Windows 更新中提供的任何其他更新。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>执行恢复

1. 在 Microsoft 团队聊天室设备上登录到管理员帐户，并启动提升的命令提示符。
2. 从 Microsoft 团队聊天室设备验证你是否能够访问该`RecoveryTool.ps1`文件，该设备包含在从 Microsoft 团队聊天室安装包提取的文件中。 在准备必备条件时使用的网络共享或 USB 驱动器上可以找到该工具包。
3. 运行 Powershell 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4. 当脚本选择 "选项`1:"Repair System"`" 时出现提示。
5. 完成后，重新启动 Microsoft 团队聊天室设备。 它将自动重新启动，并在第二次恢复时完全恢复。



<a name="See"> </a>  
## <a name="see-also"></a>另请参阅
 
[Microsoft Teams 会议室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
