---
title: 解决 Windows 上的 Microsoft Teams 安装和更新问题
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何解决 Windows 上 Teams 桌面客户端应用的安装和更新问题。
ms.openlocfilehash: a6070dbd6bd0540c7402f8d8077ea468a3296c31
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300276"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>解决 Windows 上的 Microsoft Teams 安装和更新问题

本文提供有关如何诊断和解决在 Windows 上运行的 Teams 桌面客户端应用的安装和更新问题的指南。

## <a name="check-whether-teams-is-updated-successfully"></a>检查 Teams 是否已成功更新

按照以下步骤检查是否已成功安装 Teams 更新。

1. 在 Teams 中，选择你的个人资料图片，然后单击“**关于**” > “**版本**”。
2. 在同一菜单上，单击“**检查更新**”。
3. 等待应用顶部的横幅指示需要“刷新”Teams。 该链接应在此进程下载 Teams 新版本后大约 1 分钟内显示。 通过该横幅，你还可以知道自己是否已在运行最新版本，如果是，则无需进行更新。
4. 单击横幅上的刷新链接。
5. 等待 Teams 重新启动，然后重复步骤 1 以查看应用是否已更新。

如果看到失败消息，或者版本号与步骤 4 中的相同，则表示更新进程失败。

## <a name="troubleshoot-installation-and-update-issues"></a>解决安装和更新问题

### <a name="troubleshoot-installation-issues"></a>解决安装问题

安装 Teams 后，Teams 安装程序会将事件序列记录到 %LocalAppData%\SquirrelTemp\SquirrelSetup.log。 首先要查找错误消息或日志末尾附近的调用堆栈。 请注意，日志开头的调用堆栈可能并不意味着存在安装问题。 更简单的方式是将你的日志与成功安装（即使是在另一台计算机上）后的日志进行比较，查看预期效果。

如果 SquirrelSetup 未指明原因，或者如果你需要更多信息以解决问题，请参阅[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。

### <a name="troubleshoot-update-issues"></a>解决升级问题

成功安装 Teams 后，日志位置将从 %LocalAppData%\SquirrelTemp 切换到 %LocalAppData%\Microsoft\Teams。 在这里，有两个需要关注的日志文件：SquirrelSetup.log 和 logs.txt。

- 这里的 SquirrelSetup.log 文件是由 Update.exe 写入的，后者是为 Teams 应用服务的可执行文件。
- Logs.txt 文件用于 Teams 应用（具体来说，是 Teams.exe）记录重要应用程序事件。 它可能包含失败信息。

这些日志文件包含个人身份信息 (PII)，因此不会发送给 Microsoft。

Teams 可以自动启动更新进程（具体取决于策略），或者，用户可以通过访问其个人资料图片 >“**检查更新**”来手动检查更新。 两种方法均使用以下事件序列。

1. **检查是否有更新**。 Teams 提出 web 请求，包括当前应用版本和部署铃声信息。 此步骤旨在获取下载链接。 此步骤中的失败将记录在 Logs.txt 中。
2. **下载更新**。 Teams 将使用从步骤 1 中获得的下载链接下载更新。 下载完成后，Teams 将调用 Update.exe 来暂存下载。 下载失败也记录在 Logs.txt 中。
3. **暂存更新**。 下载的内容将经过验证，并由 Update.exe 解压缩到中间文件夹 %LocalAppData%\Microsoft\Teams\stage) 中。 此步骤中的失败将记录在 SquirrelTemp.log 中。
4. **安装更新**。 可通过多种方式启动 Teams。 用户登录时，系统会自动启动 Teams，或者，可以通过快捷方式启动 Teams。 在此步骤中，Update.exe 会检查暂存文件夹是否存在，再次验证内容，并执行文件操作来取消暂存应用。 %LocalAppData%\Microsoft\Teams\current 中的旧应用程序文件夹将备份到 %LocalAppData%\Microsoft\Teams\previous，且暂存文件夹将重命名为“current”。 此步骤中的失败将记录在 SquirrelTemp.log 中。

如果 SquirrelTemp.log 或 Logs.txt 没有包含足以确定基本原因的信息，而且你需要更多信息来解决问题，请转至[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。

## <a name="collect-and-analyze-application-and-system-logs"></a>收集和分析应用程序和系统日志

本节介绍如何收集和分析应用程序和系统日志，以获取更全面的信息来解决问题。 可使用 Sysinternals 工具来完成这些步骤。 要了解更多信息，请参阅 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。

### <a name="collect-logs"></a>收集日志

1. 下载 [Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。
2. 将 zip 文件提取到本地驱动器上的 % TEMP% 文件夹。
3. 打开提升的命令提示符，然后执行以下操作：

    1. 运行以下命令以转至 TEMP 文件夹：

        ```console
        cd /d %TEMP%
        ```
    2. 复制安装和应用程序日志。 请注意，根据故障点，某些日志可能不会显示。

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 运行以下命令以捕获打开的句柄。

        ```console
        handle > handles.txt
        ```

    4. 运行以下命令以捕获打开的 DLL。

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. 运行以下命令以捕获正在运行的驱动程序。

        ```console
        driverquery /v > driverquery.txt
        ```

    6. 运行以下命令以捕获 Teams 文件夹的访问控制列表 (ACL)。

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>分析日志（适用于高级用户）

更新失败可能会导致无法预测的应用行为。 例如，用户可能无法退出 Teams、拥有过时的 Teams 版本或无法启动 Teams。 如果你在更新过程中遇到问题，请先在 SquirrelTemp.log 中查找原因。 下面列出了几种不同类型的更新失败（从最常见到最不常见），以及如何使用日志对它们进行分析和故障排除。

#### <a name="unable-to-exit-teams"></a>无法退出 Teams

当 Teams 确定需要将自身更新到较新版本时，它会下载并暂存新应用，然后等待机会，在计算机下次空闲时重新启动。 此过程中的一个常见问题是，当另一个进程或文件系统驱动程序锁定了 Teams.exe 进程时，会导致其无法退出。 因此，Teams 应用就无法被新下载和暂存的应用取代。

疑难解答提示：

- 要确认这是就是你遇到的问题，请退出 Teams（在任务栏上右键单击 Teams，然后单击“**退出**”）。 然后，在 Windows 中打开任务管理器，查看 Teams 的实例是否仍在运行。  
- 如果你不在发生此问题的计算机上，请检查从发生此问题的计算机上收集的 SquirrelTemp，并查找“Program: Unable to terminate the process in the log”条目。
- 要确定导致 Teams.exe 无法退出的原因，请查找 Dlls.txt 和 Handles.txt 日志。 这些日志会告诉你阻止 Teams 退出的进程。
- 导致 Teams 无法退出的另一个可能原因是内核模式文件系统筛选器驱动程序。 可以使用 SysInternals 工具 [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)，通过运行 ```procdump -mk <pid>```（其中，<pid> 是从任务管理器中获取的进程 ID）收集内核模式进程转储。 你也可以检查 Driverquery.txt 日志文件，查看是否有可能干扰 Teams 的活动筛选器驱动程序。
- 要从此状态还原，请重启计算机。

#### <a name="file-permissions"></a>文件权限

在整个安装和更新过程中，Teams 会在用户配置文件中创建大量子文件夹和文件。 由于应用程序和更新程序是以非提升用户的身份运行的，因此必须对以下文件夹授予读取和写入权限：

|文件夹  |使用方  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Teams 安装程序（例如，Teams_Windows_x64.exe）在安装阶段使用        |
|%LocalAppData%\Microsoft\Teams  | Teams 更新程序 (Update.exe) 在更新过程中用于提取和暂存应用包        |
|%AppData%\Microsoft\Teams   |  Teams 应用 (Teams.exe) 用于保存设置、应用状态和（预先暂存的）已下载更新包       |

如果 Teams 由于无法写入文件而被拒绝访问，另一个软件应用程序可能会产生干扰，或者安全描述符条目可能会限制对文件夹的写入权限。

疑难解答提示：

- 在 SquirrelTemp.log 或 Logs.txt 中查找“access denied”的证据。 检查这些文件，了解是否曾尝试写入文件但失败。
- 打开 Icacls.txt，查找阻止非管理员用户写入操作的有效访问控制项 (ACE)。这通常是一个 DACL 项。 有关详细信息，请参阅 [icacls 文档](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。

#### <a name="file-corrupted"></a>文件损坏

在某些情况下，加密软件可能会更改 %LocalAppData%\Microsoft\Teams 文件夹中的文件，进而导致 Teams 无法启动。 这种情况可能在任何时候发生，即使不在更新应用时也不例外。 遗憾的是，如果文件损坏，从此状态恢复的唯一方法是卸载并重新安装 Teams。

> [!NOTE]
> 如果使用上述任何步骤均无法确定问题的根本原因，则可能需要尝试 [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) 会话。 Process Monitor 是一个 Sysinternals 工具，可以记录对注册表和文件系统的访问。

## <a name="related-topics"></a>相关主题

- [获取 Teams 客户端](get-clients.md)
- [Teams 客户端更新](teams-client-update.md)
- [Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
