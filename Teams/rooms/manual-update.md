---
title: 手动更新 Microsoft Teams 会议室设备
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解如何手动将 Microsoft Teams 会议室设备更新到特定版本。
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731388"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手动更新 Microsoft Teams 会议室设备

Microsoft Teams 会议室应用通过 Microsoft Store 分发。 应用更新在夜间维护期间从 Microsoft Store 自动安装;这是获取更新的建议方法。 但是，在某些情况下，Teams 会议室设备无法从 Microsoft Store 接收更新。 例如，安全策略可能不允许设备连接到 Internet，或者可能不允许从 Microsoft Store 下载应用。 或者，你可能希望在执行设置之前更新设备，在此期间 Microsoft Store 不可用。

如果无法从 Microsoft Store 获取更新，可以使用脱机应用更新 PowerShell 脚本手动将 Teams 会议室设备更新到较新版本的 Teams 会议室应用。 按照本文中的步骤手动更新 Teams 会议室设备。

> [!NOTE]
> 此过程只能更新已安装 Teams 会议室应用的 Teams 会议室设备。 它不能用于执行新安装。 此外，它不能用于将应用降级到较旧版本。 若要执行 Teams 会议室应用的新安装，请联系设备的制造商，了解特定于它的媒体，或参阅"[准备安装媒体"。](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>步骤 1：下载脱机应用更新脚本

首先，下载最新版本的脱机应用更新脚本。 若要下载脚本，请单击 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 脚本将下载到设备上的默认下载文件夹。

下载的文件可能标记为受 Windows 阻止。 如果需要在不交互的情况下运行脚本，则需要取消阻止脚本。 若要取消阻止脚本，请执行下列操作：

1. 在文件资源管理器中右键单击文件
2. 单击 **"属性"**
3. 选择 **"取消阻止"**
4. 单击 **"确定"**

若要使用 PowerShell 取消阻止脚本，请参阅["取消阻止文件"。](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

下载脱机应用更新脚本后，将文件转移到 Teams 会议室设备。 在设备的管理模式下，可以通过使用 U 盘或从网络文件共享访问文件，将文件转移到设备。 请务必记下在设备上保存文件的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步骤 2：运行脚本以更新 Teams 会议室应用

脱机应用更新脚本需要从提升的命令提示符运行，而 Skype 用户 (运行该应用的用户) 登录。 若要详细了解如何在 Skype 用户仍登录时登录到管理员帐户以使用提升的命令提示符，请参阅"切换到管理模式"，在 [Microsoft Teams 会议室](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)应用运行时返回。

执行下列操作，从提升的命令提示符运行脚本：

1. 切换到管理模式
2. 单击"开始"图标，键入 **命令提示符**，然后选择"以 **管理员角色运行"**
3. 运行以下命令 `<path to script>` ，其中包含脚本的完整路径和脚本文件的名称：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果脚本文件位于且脚本文件名为，请 `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 运行以下命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允许脚本运行。 完成后，脚本将重新启动 Teams 会议室设备。

也可使用远程 PowerShell 运行脚本。 有关将远程 PowerShell 与 Teams 会议室设备一起使用详细信息，请参阅"[使用 PowerShell 进行远程管理"。](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步骤 3：验证应用已成功更新

如果脚本成功运行，设备将重新启动到 Teams 会议室应用中。

如果脚本遇到问题，它将指示命令行上的问题，并记录其输出到文件。 按照脚本提供的任何说明进行操作。 如果需要联系 Microsoft 支持部门，请确保包括日志文件支持请求。 该脚本将提供该脚本日志文件。
