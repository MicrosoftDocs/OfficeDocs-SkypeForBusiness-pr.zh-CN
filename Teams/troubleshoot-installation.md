---
title: 解决 Windows 上的 Microsoft 团队安装和更新问题
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何解决 Windows 上的团队桌面客户端应用的安装和更新问题。
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920144"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>解决 Windows 上的 Microsoft 团队安装和更新问题

本文提供了有关如何诊断和解决 Windows 上运行的团队桌面客户端应用的安装和更新问题的指南。

## <a name="check-whether-teams-is-updated-successfully"></a>检查团队是否已成功更新

按照以下步骤检查团队更新是否已成功安装。

1. 在 "团队" 中，选择您的个人资料图片，然后单击 "**关于** > **版本**"。
2. 在同一菜单上，单击 "**检查更新**"。
3. 请等待应用顶部的横幅，以指示需要团队的 "刷新"。 在此过程下载新版本的团队时，该链接稍后应显示大约一分钟。 横幅还让你知道是否已运行最新版本，在这种情况下，不需要更新。
4. 单击横幅中的 "刷新" 链接。
5. 等待团队重新启动，然后重复步骤1以查看是否更新了应用。

如果您看到一条错误消息，或者版本号与步骤4中的版本号相同，则更新过程失败。

## <a name="troubleshoot-installation-and-update-issues"></a>解决安装和更新问题

### <a name="troubleshoot-installation-issues"></a>解决安装问题

在安装团队时，团队安装程序会将事件序列记录到%LocalAppData%\SquirrelTemp\SquirrelSetup.log。 要查找的第一件事是出现一条错误消息或一个靠近日志末尾的调用堆栈。 请注意，日志开头的调用堆栈可能并不意味着存在安装问题。 将日志与日志进行比较比从成功安装（甚至在另一台计算机上）到日志，以查看预期效果。

如果 SquirrelSetup 未指明原因，或者你需要详细信息来解决该问题，请参阅[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)。

### <a name="troubleshoot-update-issues"></a>更新问题疑难解答

成功安装团队后，日志位置将从%LocalAppData%\SquirrelTemp 切换到%AppData%\Microsoft\Teams。 在此位置，有两个感兴趣的日志文件： SquirrelSetup 和 .log。

- 此位置的 SquirrelSetup 文件由 update.exe 编写，后者是为团队应用服务的可执行文件。
- "团队" 应用（特别是 "团队 .exe"）使用日志 .txt 文件记录重要的应用程序事件。 它可能会包含失败信息。

这些日志文件包含个人身份信息（PII），因此它们不会发送给 Microsoft。

团队可以自动启动更新过程（具体取决于策略），或者用户可以通过转到其个人资料图片来手动检查更新 >**检查是否有更新**。 这两种方法都使用以下事件序列。

1. **检查更新**。 团队发出 web 请求，包括当前应用版本和部署震铃信息。 此步骤的目标是获取下载链接。 此步骤中的失败记录在 ".txt" 中。
2. **下载更新**。 团队使用从步骤1获取的下载链接下载更新。 下载完成后，团队将调用 update.exe 以暂存下载。 日志 .txt 中也会记录下载失败。
3. **暂存更新**。 下载的内容将验证并解压缩到中间文件夹%LocalAppData%\Microsoft\Teams\stage）中，该文件夹由 update.exe 完成。 此步骤中的失败记录在 SquirrelTemp 中。
4. **安装更新**。 有多种方法可以启动团队。 当用户登录时，系统会自动启动团队，或者你可以通过快捷方式启动团队。 在此步骤中，update.exe 检查是否存在暂存文件夹，再次验证内容，并执行文件操作来取消暂存应用。 %LocalAppData%\Microsoft\Teams\current 中的旧应用程序文件夹将备份到%LocalAppData%\Microsoft\Teams\previous，并将 "暂存" 文件夹重命名为 "当前"。 此步骤中的失败记录在 SquirrelTemp 中。

如果 SquirrelTemp 或 .log 不包含足够的信息来确定基础原因，并且你需要更多的信息来解决该问题，请转到 "[收集和分析应用程序和系统日志](#collect-and-analyze-application-and-system-logs)"。

## <a name="collect-and-analyze-application-and-system-logs"></a>收集和分析应用程序和系统日志

本部分介绍了如何收集和分析应用程序和系统日志，以获取更全面的信息来解决该问题。 您将使用 Sysinternals 工具完成这些步骤。 若要了解详细信息，请参阅[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。

### <a name="collect-logs"></a>收集日志

1. 下载[Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。
2. 将 zip 文件解压缩到本地驱动器上的% TEMP% 文件夹。
3. 打开提升的命令提示符，然后执行下列操作：

    1. 运行以下操作以转到 TEMP 文件夹：

        ```
        cd /d %TEMP%
        ```
    2. 复制设置和应用程序日志。 请注意，根据故障点，某些日志可能不存在。

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 运行以下操作以捕获打开的句柄。

        ```
        handle > handles.txt
        ```

    4. 运行以下操作以捕获打开的 Dll。

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. 运行以下操作以捕获正在运行的驱动程序。

        ```
        driverquery /v > driverquery.txt
        ```

    6. 运行以下操作以捕获 "团队" 文件夹的访问控制列表（Acl）。

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>分析日志（适用于高级用户）

失败的更新会导致不可预测的应用行为。 例如，用户可能无法退出团队、拥有团队的陈旧版本或无法启动团队。 如果您在更新过程中遇到问题，第一个查找原因的位置是 SquirrelTemp。 下面是不同类型的更新失败内容，按从最常见到最不常见的列表列出，以及如何使用日志分析和排除它们。

#### <a name="unable-to-exit-teams"></a>无法退出团队

当团队认为需要将其自身更新为较新的版本时，它会下载并阶段新应用，然后等待商机在下次计算机空闲时重新启动它。 此过程中的一个常见问题是当另一个进程或文件系统驱动程序锁定了团队 .exe 进程时，这将阻止团队 .exe 退出。 因此，不能将团队应用替换为新下载和暂存的应用。

疑难解答提示：

- 若要确认这是你遇到的问题，请退出团队（右键单击任务栏上的 "团队"，然后单击 "**退出**"）。 然后，在 Windows 中打开任务管理器，以查看团队实例是否仍在运行。  
- 如果你不在遇到此问题的计算机上，请检查从遇到此问题的计算机收集的 SquirrelTemp，并查找 "程序：无法终止日志中的进程" 条目。
- 若要确定哪些人正在阻止团队成员退出，请查看 Dll 并处理 .txt 日志。 这将告诉你阻止团队退出的流程。
- 可防止团队退出的另一个原因是内核模式文件系统筛选器驱动程序。 使用 SysInternals 工具[ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)，通过运行```procdump -mk <pid>```来收集内核模式进程转储，其中<pid>是从任务管理器获取的进程 ID。 你还可以检查 Driverquery 日志文件，查看可能会干扰团队的活动筛选器驱动程序。
- 若要从该状态恢复，请重新启动计算机。

#### <a name="file-permissions"></a>文件权限

在整个安装和更新过程中，团队会在用户的配置文件中创建许多子文件夹和文件。 由于应用和更新程序作为非提升用户运行，因此必须在以下文件夹上授予 read 和 write 权限：

|收藏夹  |使用者  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | 安装阶段中的团队安装程序（例如，Teams_Windows_x64）        |
|%LocalAppData%\Microsoft\Teams  | 团队更新程序（update.exe），用于在更新过程中提取并暂存应用包        |
|%AppData%\Microsoft\Teams   |  用于保存设置、应用状态和已下载（预暂存）的更新程序包的团队应用（团队 .exe）       |

如果团队因无法写入文件而被拒绝访问，则另一个软件应用程序可能会干扰，或者安全描述符条目可能会限制对文件夹的写入访问权限。

疑难解答提示：

- 在 SquirrelTemp 或 readme.txt 中查找 "拒绝访问" 证据。 检查这些文件，查看是否有尝试写入失败的文件。
- 打开 Icacls 并查找有效的访问控制条目（ACE），该条目由非管理员用户阻止写入操作。通常，这是一个 DACL 条目。 有关详细信息，请参阅[icacls 文档](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。

#### <a name="file-corrupted"></a>文件已损坏

在某些情况下，加密软件可以更改%LocalAppData%\Microsoft\Teams 文件夹中的文件，这可以防止团队启动。 这可能会在任何时间发生，即使应用未更新也是如此。 遗憾的是，当文件损坏时，从该状态恢复的唯一方法是卸载并重新安装团队。

> [!NOTE]
> 如果你无法使用以下任一步骤确定问题的基本原因，你可能需要尝试[进程监视器](https://docs.microsoft.com/sysinternals/downloads/procmon)会话。 进程监视器是记录对注册表和文件系统的访问的 Sysinternals 工具。

## <a name="related-topics"></a>相关主题

- [获取 Teams 客户端](get-clients.md)
- [Teams 客户端更新](teams-client-update.md)