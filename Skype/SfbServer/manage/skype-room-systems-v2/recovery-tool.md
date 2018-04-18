---
title: 使用 Skype 的空间系统 v2 恢复工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: 本文讨论如何使用恢复工具 Skype 的空间系统 v2，用来将已过期的系统引入到受支持的状态。
ms.openlocfilehash: 5972f38370227e93cb0154771a35f3c5b0458052
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>使用 Skype 的空间系统 v2 恢复工具
 
本文讨论如何使用恢复工具 Skype 的空间系统 v2，用来将已过期的系统引入到受支持的状态。 当 Skype 的空间系统 v2 控制台显示"系统配置已过期"错误，您将使用此工具。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>先决条件

将最新的[Skype 的空间系统 v2 安装包](https://go.microsoft.com/fwlink/?linkid=851168)下载并解压缩到 USB 内存棒或网络可访问的共享到 Skype 的空间系统 v2 设备。

您可能还需要安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>验证 Windows 版本 

1. 登录到管理员帐户转到**设置 > Windows 设置 > 管理登录**从 Skype 的空间系统 v2 设备。 此选项将带您到登录屏幕。
2. 登录到管理员帐户，默认管理员帐户被`admin`密码`sfb`。
3. 单击开始菜单和类型`winver.exe`到搜索框中，单击 * 结果上的*运行命令*。
4. 在版本的第二行上的信息窗格后请记数。

> [注]如果显示的版本是 1607年或更早版本，<a href="#Perform">执行恢复</a>的步骤按照前进行<a href="#Windows-up">更新 Windows 在恢复之前</a>步骤中的步骤。 如果大于 1607年版本显示，请按照只<a href="#Perform">执行一次恢复</a>。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>在恢复之前更新 Windows （如果需要）

1. 虽然仍以管理员用户身份登录，则启动提升的 Powershell 提示符。
2. 运行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。
3. 运行 Windows 更新并为 Windows 1709 安装更新。
4. 为 1709年更新后完成登录回管理员帐户，并安装[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。 此更新可以从链接或使用 Windows 更新。
5. 从 Windows Update 安装其他所有可用的更新。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>执行恢复

1. 登录到管理员帐户上 Skype 的空间系统 v2 设备，并启动提升的命令提示符。
2. 从 Skype 的空间系统 v2 设备验证您是否可以访问`RecoveryTool.ps1`文件，其中包括在从 Skype 的空间系统 v2 安装程序包中提取文件。 工具包可以位于网络共享或准备系统必备组件时使用的 USB 驱动器。
3. 运行 Powershell.exe 命令`-file "<path to RecoveryTool.ps1>" -ExecutionPolicy Unrestricted`。
4. 当提示您的脚本选择选项`1:"Repair System"`。
5. 完成后，重新启动 Skype 的空间系统 v2 设备。 它会自动再次重新引导，并提出完全恢复第二次。



<a name="See"> </a>  
## <a name="see-also"></a>另请参阅


#### 

[Skype 的机房管理系统 v2](skype-room-systems-v2.md)
#### 