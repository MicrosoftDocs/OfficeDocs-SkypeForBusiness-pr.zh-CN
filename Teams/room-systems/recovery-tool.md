---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: 本文讨论如何使用 Microsoft 团队会议室，您将用于将过期系统导入支持状态恢复工具。
ms.openlocfilehash: d784e20656d6f97340e8cfa797d9f64bcb83d4b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916540"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 会议室恢复工具
 
本文讨论如何使用 Microsoft 团队会议室，您将用于将过期系统导入支持状态恢复工具。 Microsoft 团队聊天室控制台将显示"系统配置过期"错误时，应使用此工具。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>先决条件

下载最新的[Microsoft 团队聊天室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其提取到某个 USB 内存继续有效或网络共享访问的 Microsoft 团队聊天室设备。

您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>验证 Windows 版本 

1. 通过从 Microsoft 团队聊天室设备转**Settings> Windows Setting> 管理员登录**到的管理员帐户登录。 此选项将您带到登录屏幕。
2. 登录到一个管理帐户，默认管理员帐户进行`admin`使用密码`sfb`。
3. 单击开始菜单和类型`winver.exe`到搜索框和单击 **运行命令*的结果。
4. 记数后版本第二条直线上的信息窗格。

>[!NOTE]
>如果显示的版本为 1607年或更早版本，向<a href="#Perform">执行恢复</a>步骤按照之前进行的<a href="#Windows-up">更新 Windows 恢复之前</a>步骤中的步骤。 如果显示的版本大于 1607年，请按照仅<a href="#Perform">执行恢复</a>中的步骤。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>在恢复之前更新 Windows （如果需要）

1. 仍在登录为管理员用户，启动一个提升的 Powershell 提示符。
2. 运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。
3. 运行 Windows 更新并安装 Windows 1709 的更新。
4. 1709 到更新后完成登录回管理员帐户，并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。 更新可能完成从链接或使用 Windows Update。
5. 作为一个可选步骤，安装 Windows Update 提供任何其他更新。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>执行恢复

1. 登录到您的 Microsoft 团队聊天室设备上的管理帐户并启动提升的命令提示符。
2. 从 Microsoft 团队聊天室设备验证您是否能够访问`RecoveryTool.ps1`从 Microsoft 团队聊天室安装程序包中提取的文件中包含的文件。 可以使用准备先决条件时的 USB 驱动器或网络共享上找到工具包。
3. 运行 Powershell.exe 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4. 当提示您的选择脚本选项`1:"Repair System"`。
5. 完成后，重新启动 Microsoft 团队聊天室设备。 它将重新自动重新启动，并提出完全恢复第二次。



<a name="See"> </a>  
## <a name="see-also"></a>另请参阅
 
[Microsoft Teams 会议室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
