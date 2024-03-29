---
title: 手动更新Microsoft Teams 会议室设备
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 了解如何手动将Microsoft Teams 会议室设备更新到特定版本。
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267637"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手动更新Microsoft Teams 会议室设备

Microsoft Teams 会议室应用通过 Microsoft Store 分发。 汇报在夜间维护期间自动从 Microsoft Store 安装到应用;建议使用此方法获取更新。 但是，在某些情况下，Teams 会议室设备无法从 Microsoft Store 接收更新。 例如，安全策略可能不允许设备连接到 Internet，或者可能不允许从 Microsoft Store 下载应用。 或者，可能需要在执行安装程序之前更新设备，在此期间 Microsoft Store 不可用。

如果无法从 Microsoft Store 获取更新，则可以使用脱机应用更新 PowerShell 脚本，手动将Teams 会议室设备更新为较新版本的Teams 会议室应用。 按照本文中的步骤手动更新Teams 会议室设备。

> [!NOTE]
> 此过程只能更新已安装Teams 会议室应用的Teams 会议室设备。 它不能用于执行新安装。 它也不能用于将应用降级到较旧的版本。 若要执行Teams 会议室应用的新安装，请联系设备的制造商，了解特定于它的媒体。

## <a name="step-1-download-the-offline-app-update-script"></a>步骤 1：下载脱机应用更新脚本

首先，下载脱机应用更新脚本的最新版本。 若要下载脚本，请单击 <https://go.microsoft.com/fwlink/?linkid=2151817>。 脚本将下载到设备上的默认下载文件夹。

下载的文件可能被 Windows 标记为阻止。 如果需要在没有交互的情况下运行脚本，则需要取消阻止脚本。 若要取消阻止脚本，请执行以下操作：

1. 右键单击文件资源管理器中的文件
2. 单击 **“属性”**
3. 选择 **“取消阻止”**
4. 单击 **“确定”**

若要使用 PowerShell 取消阻止脚本，请参阅 [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

下载脱机应用更新脚本后，将文件传输到Teams 会议室设备。 可以通过使用 USB 驱动器或在设备上的管理员模式下从网络文件共享访问文件，将文件传输到设备。 请务必注意在设备上保存文件的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步骤 2：运行脚本以更新Teams 会议室应用

脱机应用更新脚本需要从提升的命令提示符运行，而 Skype 用户 (运行应用的用户) 仍然登录。 有关如何在 Skype 用户仍登录时登录到管理员帐户以使用提升的命令提示符的详细信息，请[参阅切换到管理员模式并在Microsoft Teams 会议室应用崩溃时返回](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)。

执行以下操作，从提升的命令提示符运行脚本：

1. 切换到管理员模式
2. 单击“开始”图标，键入 **命令提示符**，然后选择 **“以管理员身份运行”**
3. 运行以下命令，其中 `<path to script>` 包含脚本的完整路径和脚本文件的名称：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果脚本文件位于脚本文件中 `C:\Users\Admin\Downloads`且脚本文件名为 `MTR-Update-4.5.6.7.ps1`，请运行以下命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允许运行脚本。 完成后，脚本将重新启动Teams 会议室设备。

也可以使用远程 PowerShell 运行脚本。 有关将远程 PowerShell 用于Teams 会议室设备的详细信息，请参阅[使用 PowerShell 的远程管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步骤 3：验证应用是否已成功更新

如果脚本成功运行，设备将重新启动到Teams 会议室应用。

如果脚本遇到问题，它将指示命令行上的问题，并将其输出记录到文件。 按照脚本提供的任何说明操作。 如果需要联系Microsoft 支持部门，请确保包括日志文件和支持请求。 该脚本将为你提供日志文件的路径。
