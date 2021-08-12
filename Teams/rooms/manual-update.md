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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解如何手动将设备Microsoft Teams 会议室到特定版本。
ms.openlocfilehash: 2a37a6b1eb349d38d1579bf5c69822db8dac7dd0dd000e60bfdba034cdf62680
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350464"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手动更新Microsoft Teams 会议室设备

Microsoft Teams 会议室应用通过 Microsoft Store。 从应用程序自动安装应用更新Microsoft Store在夜间维护期间自动安装;这是获取更新的建议方法。 但是，在某些情况下，Teams 会议室设备无法从服务器接收Microsoft Store。 例如，安全策略可能不允许设备连接到 Internet，或者可能不允许从客户端下载Microsoft Store。 或者，你可能希望在执行设置之前更新设备，在此期间Microsoft Store不可用。

如果无法从 Microsoft Store 获取更新，可以使用脱机应用更新 PowerShell 脚本手动将 Teams 会议室 设备更新到较新版本的 Teams 会议室 应用。 按照本文中的步骤手动更新Teams 会议室设备。

> [!NOTE]
> 此过程只能使用已安装Teams 会议室更新Teams 会议室设备。 它不能用于执行新安装。 它还不能用于将应用降级到较旧版本。 若要执行新安装 Teams 会议室，请联系设备制造商，了解特定于它的媒体，或参阅[准备安装媒体](console.md#prepare-the-installation-media)。

## <a name="step-1-download-the-offline-app-update-script"></a>步骤 1：下载脱机应用更新脚本

首先，下载最新版本的脱机应用更新脚本。 若要下载脚本，请单击 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 脚本将下载到设备上的默认下载文件夹。

下载的文件可能标记为被Windows。 如果需要在不交互的情况下运行脚本，则需要取消阻止脚本。 若要取消阻止脚本，请执行下列操作：

1. 在文件资源管理器中右键单击文件
2. 单击" **属性"**
3. 选择 **"取消阻止"**
4. 单击" **确定"**

若要使用 PowerShell 取消阻止脚本，请参阅 [取消阻止文件](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

下载脱机应用更新脚本后，将文件Teams 会议室设备。 在设备的管理模式下，可以通过使用 U 盘或从网络文件共享访问文件，将文件转移到设备。 请务必记下文件在设备上保存的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步骤 2：运行脚本以更新 Teams 会议室 应用

脱机应用更新脚本需要从提升的命令提示符下运行，而 Skype 用户 (运行应用的用户) 登录。 若要详细了解如何在 Skype 用户仍登录时登录到管理员帐户以使用提升的命令提示符，请参阅切换到管理员模式，以及当 Microsoft Teams 会议室 应用[运行时](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)返回。

执行以下操作，从提升的命令提示符运行脚本：

1. 切换到管理模式
2. 单击"开始"图标，键入 **"命令提示符**"，然后选择" **以管理员角色运行"**
3. 运行以下命令， `<path to script>` 其中包括脚本的完整路径和脚本文件的名称：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果脚本文件位于 中，并且脚本 `C:\Users\Admin\Downloads` 文件名为 `MTR-Update-4.5.6.7.ps1` ，请运行以下命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允许运行脚本。 完成后，脚本将重新启动Teams 会议室设备。

也可使用远程 PowerShell 运行脚本。 有关在远程设备上使用远程 PowerShell Teams 会议室，请参阅使用[PowerShell 进行远程管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步骤 3：验证应用已成功更新

如果脚本成功运行，设备将重新启动到Teams 会议室应用。

如果脚本遇到问题，它将指示命令行上的问题，并记录其输出到文件。 按照脚本提供的任何说明进行操作。 如果需要联系 Microsoft 支持部门，请确保包括日志文件支持请求。 该脚本将提供目标路径日志文件。