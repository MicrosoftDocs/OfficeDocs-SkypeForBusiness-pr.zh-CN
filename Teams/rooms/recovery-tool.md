---
title: 使用 Microsoft Teams 会议室恢复工具
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文讨论如何使用恢复工具Microsoft Teams 会议室恢复工具，该工具用于使过期系统进入受支持状态。
ms.openlocfilehash: 4abd13abcfd20385c6f26e029dae1435883f0f8e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503689"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 会议室恢复工具

本文讨论如何使用恢复工具Microsoft Teams 会议室恢复工具，该工具用于使过期系统进入受支持状态。 当主机上显示"Microsoft Teams 会议室配置已过期"错误，或者在执行按钮重置出厂还原之前，应应用[此工具](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>先决条件

下载最新的 [Microsoft Teams 会议室 安装包](https://go.microsoft.com/fwlink/?linkid=851168)，并解压缩到可供用户访问的 U 盘或Microsoft Teams 会议室。

> [!NOTE]
> 从 MSI 提取文件可以通过多种方法完成。 提取所有文件并保留其目录结构的任何机制都是可接受的。 其中一种方式`msiexec /a PathToMsi /qb TARGETDIR=PathToTarget``PathToMsi`是使用 命令，其中 表示 Microsoft Teams Room `PathToTarget` 安装包的完整路径，并表示要提取文件的文件夹的完整路径。

## <a name="running-the-tool"></a>运行工具

1) 登录到设备中的管理员帐户Microsoft Teams 会议室，并启动提升的命令提示符。
2) 从Microsoft Teams 会议室设备`RecoveryTool.ps1`验证你能够访问文件，该文件包含在从安装包中提取Microsoft Teams 会议室文件。 可以在准备先决条件时所使用的网络共享或 U 盘上找到该工具包。
3) 运行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。
4) 若要执行恢复出厂设置，请执行以下操作：
   1. 当脚本提示时，请选择选项 2： **重置**。
   2. 如果 BitLocker 已打开，请按照脚本输出末尾提供的说明禁用它。
   3. 执行工厂还原。
      1. 打开 **设置 应用**，然后选择"**更新&安全性"**
      2. 导航到"恢复 **"** 选项卡。
      3. 在 **"重置此电脑"下**，选择 **"开始使用"**
      4. 选择" **删除所有内容"**，然后选择"下 **一步"和** " **重置"**
        > [!WARNING]
        > 如果在Microsoft Teams 会议室重置过程中选择了"保留我的文件 **-** 删除应用和设置，但保留个人文件"选项，则Windows不可用。 不要选择此选项。
      5. 系统将多次重新启动。 重置完成后，系统将位于 OOBE Windows"开箱即用"屏幕 (") 屏幕。



## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)
