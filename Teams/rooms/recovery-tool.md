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
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021720"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 会议室恢复工具

本文介绍了如何使用 Microsoft 团队聊天室的恢复工具，使用该工具可以将过时系统置于受支持状态。 当 Microsoft 团队聊天室控制台显示 "系统配置已过期" 错误或执行按钮重置[出厂还原](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)之前，应应用此工具。

## <a name="prerequisites"></a>先决条件

下载最新的[Microsoft 团队聊天室安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并将其解压缩到 Microsoft 团队聊天室设备可访问的 USB 记忆棒或网络共享。

> [!NOTE]
> 从 MSI 中提取文件可以通过多种方式完成。 提取所有文件并保留其目录结构的任何机制都是可接受的。 其中一种方法是使用该命令， `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` 其中 `PathToMsi` 表示 Microsoft 团队聊天室安装包的完整路径，并 `PathToTarget` 表示你希望将文件提取到的文件夹的完整路径。

## <a name="running-the-tool"></a>运行工具

1) 在 Microsoft 团队聊天室设备上登录到管理员帐户，并启动提升的命令提示符。
2) 从 Microsoft 团队聊天室设备验证你可以访问的，该设备 `RecoveryTool.ps1 file` 包含在从 Microsoft 团队聊天室安装包提取的文件中。 在准备必备条件时使用的网络共享或 USB 驱动器上可以找到该工具包。
3) 运行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 要执行出厂还原，请执行以下操作：
   1. 当脚本提示时，选择选项2： **Reset**。
   2. 如果 BitLocker 已打开，请按照脚本输出末尾提供的说明将其禁用。
   3. 执行出厂还原。
      1. 打开 "**设置**" 应用，然后选择 "**更新 & 安全性**"
      2. 导航到 "**恢复**" 选项卡。
      3. 在 "**重置此电脑**" 下，选择 "**开始**"
      4. 选择 "**删除所有内容**" **，然后单击**"**重置**"
        > [!WARNING]
        > 如果**保留我的文件-删除应用和设置，但**在 Windows 重置过程中选择 "保留个人文件" 选项，则 Microsoft 团队聊天室设备可能会变得不可用。 不要选择此选项。
      5. 系统将重启多次。 重置完成后，系统将处于 Windows "开箱体验" （OOBE）屏幕。



## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)
