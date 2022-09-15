---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文讨论如何将恢复工具用于Microsoft Teams 会议室，用于使过期系统进入受支持的状态。
ms.openlocfilehash: 70b2d199c4fe13138e2f46fd0b49e95efbd18e9c
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706161"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 会议室恢复工具

本文讨论如何将恢复工具用于Microsoft Teams 会议室，用于使过期系统进入受支持的状态。 当Microsoft Teams 会议室控制台显示“系统配置过期”错误，或在执行推送按钮重置[出厂还](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)原之前，应应用此工具。

## <a name="prerequisites"></a>先决条件

下载最新的[Microsoft Teams 会议室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其提取到可Microsoft Teams 会议室访问的 USB 内存棒或网络共享。

> [!NOTE]
> 可通过多种方法从 MSI 中提取文件。 任何提取所有文件并保留其目录结构的机制都是可以接受的。 其中一种方法是使用表示Microsoft Teams 会议室安装包的完整路径的命令`msiexec /a PathToMsi /qb TARGETDIR=PathToTarget``PathToMsi`，并`PathToTarget`表示要将文件提取到的文件夹的完整路径。

## <a name="running-the-tool"></a>运行工具

1) 登录到Microsoft Teams 会议室设备上的管理员帐户，并启动提升的命令提示符。
2) 从Microsoft Teams 会议室设备验证是否能够访问`RecoveryTool.ps1`文件，该文件包含在从Microsoft Teams 会议室安装包中提取的文件中。 可以在准备先决条件时使用的网络共享或 USB 驱动器上找到该工具包。
3) 运行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4) 若要执行工厂还原，请执行以下操作：
   1. 当脚本提示时，选择选项 2： **重置**。
   2. 如果 BitLocker 处于打开状态，请按照脚本输出末尾提供的说明禁用它。
   3. 执行工厂还原。
      1. 打开 **“设置”** 应用，然后选择 **“更新&安全性**
      2. 导航到 **“恢复** ”选项卡。
      3. **在“重置此电脑**”下方，选择 **“入门”**
      4. 选择 **“删除所有内容**”，然后 **选择“下一步****”和“重置”**
        > [!WARNING]
        > 如果“**保留我的文件 - 删除应用和设置**”，则Microsoft Teams 会议室设备可能变得不可用，但会在 Windows 重置过程中选择“保留个人文件”选项。 请勿选择此选项。
      5. 系统将多次重启。 重置完成后，系统将在 Windows“开箱即用体验” (OOBE) 屏幕。



## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)
