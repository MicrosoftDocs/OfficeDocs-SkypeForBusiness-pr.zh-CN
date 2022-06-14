---
title: 在对 Microsoft Teams 进行故障排除时使用日志文件
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 了解Microsoft Teams生成的调试、媒体和桌面日志，以及它们如何帮助监视和故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 178e89ff91de4638f6a9ff56a4dcb935d18f6f91
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056942"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>使用日志文件监视和排查Microsoft Teams

客户端自动生成了三种类型的日志文件，可用于帮助监视和排查Teams：

-   [调试日志](#debug-logs)

-   [媒体日志](#media-logs)

-   [桌面日志](#desktop-logs)

本文介绍这些日志及其使用方式。 有关排查特定问题的信息，请参阅：[Teams疑难解答](/MicrosoftTeams/troubleshoot/teams)。 有关如何联系支持人员的信息，请参阅 [“获取支持](/microsoft-365/business-video/get-help-support)”。 通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。 在创建支持请求之前手动启用调试日志可让 Microsoft 快速开始对问题进行故障排除。 仅当 Microsoft 请求时，才需要 **媒体** 或 **桌面** 日志。

> [!NOTE]
> 在本文中，术语 **“调试日志”** 是指用于故障排除的日志。 但是，为这些日志生成的文件将包含其名称中的术语 **诊断日志** 。  

## <a name="collect-and-enable-logging"></a>收集并启用日志记录

一旦出现问题，必须立即收集日志。 只需单击几下，即可收集日志。

- Windows：右键单击系统托盘中的Teams图标，然后选择 **“收集支持文件**”。 

- Mac：选择“帮助”菜单，然后选择 **“收集支持文件**”。

调试、桌面和媒体日志将收集在名为 _MSTeams 诊断日志 \<local date and time\>_ 的文件夹中。 使用Microsoft 支持部门打开支持请求时，可以压缩和共享此文件夹。 该文件夹将包含桌面、会议 (媒体) 和调试 (Web) 的文件夹。 可以使用以下键盘快捷方式收集文件：

- Windows：<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac： <kbd>选项</kbd> + <kbd>命令</kbd> + <kbd>班次</kbd> + <kbd>1</kbd>


默认情况下，媒体日志记录仅针对某些 CPU（ [媒体日志](#media-logs)中所述）打开。 否则，它默认处于关闭状态。 若要启用媒体日志记录，用户必须在Teams客户端中启用该选项。 转到 **设置** > **General**，然后选择 **“为会议诊断启用日志记录 (需要重启Teams)**。 必须重启Teams客户端，以便日志记录开始 (重新启动它：右键单击停靠 (Mac) 或任务栏 (Windows) 中的图标，然后选择 **“退出**”。 退出后，只需单击应用图标) 再次打开它。

如果特定会议或实时事件出现问题，则将 URL 与会议关联会很有帮助。 这会提供其他信息来帮助确定日志中的确切会议或实时事件。 可以从会议的任何参与者或直播活动的演示者或制作者收集此信息。 可以通过将鼠标悬停在联接 URL 上并选择 **复制超链接** 来捕获此 URL。

> [!NOTE]
> 如果启用了媒体日志记录，则会议文件夹中将包含其他文件，这是调查音频和视频问题所必需的。 如果未启用媒体日志记录，则可用的日志数量有限。
  
> [!NOTE]
> 调试日志以前是使用下面的键盘快捷方式收集的。 这些操作仍可正常运行，并将完成与 **“收集支持文件** ”选项相同的日志捕获。
>
> - Windows：<kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac： <kbd>选项</kbd> + <kbd>命令</kbd> + <kbd>班次</kbd> + <kbd>1</kbd>


下表概述了各种客户端及其关联的日志。 日志文件存储在特定于客户端和操作系统的位置。


|客户端 |调试|桌面|媒体|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

有关支持的操作系统和浏览器的完整列表，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。

## <a name="debug-logs"></a>调试日志

有关Windows和 Mac 说明，请参阅 _“收集并启用日志记录_”部分。 调试日志由 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成。 日志基于文本，从自下而上读取。 可以使用任何基于文本的编辑器读取它们，并在登录到客户端时创建新日志。

调试日志显示以下数据流：

-   登录

-   连接到中间层服务的请求

-   通话/对话

若要收集 Linux 的日志，请执行以下操作：
- 键盘快捷方式： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `~/Downloads`

若要收集浏览器和Windows日志，
- 键盘快捷方式： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `%userprofile%\Downloads`

若要收集 Mac 日志，请执行以下操作：
- 键盘快捷方式： <kbd>选项</kbd> + <kbd>命令</kbd> + <kbd>班次</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `~/Downloads`

## <a name="media-logs"></a>媒体日志

有关Windows和 Mac 说明，请参阅 _“收集并启用日志记录_”部分。 媒体日志包含有关Teams会议中的音频、视频和屏幕共享的诊断数据。 对于与呼叫相关的问题相关的支持案例，需要使用它们。

如果 CPU 为：
- 任何 Apple M1
- 任何 Intel Xeon
- 除 U、G7、M 和 MQ 系列之外的任何 Intel i9
- 除 U、G7、M 和 MQ 系列之外的任何第 6 代及更高版本的 Intel i7

否则，默认情况下会将其关闭。 若要记录Teams会议的诊断数据，用户必须在Teams客户端中启用该选项。 转到 **设置** > **General**，选择“**为会议诊断启用日志记录 (需要重启Teams)** 复选框、重启Teams并重现问题。 

> [!NOTE]
> 注销Teams时，媒体日志记录将重置为默认值。 

将日志文件发送到 Microsoft 支持时，请验证日志文件的时间戳，以确保在重现问题时日志涵盖时间范围。

若要收集 Linux 的日志，请执行以下操作：  
- 这些文件将在以下位置可用：
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

若要收集Windows日志，  
- 这些文件将在以下位置可用：
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

若要收集 Mac 日志，请执行以下操作：
- 这些文件将在以下位置可用：
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

下面是生成的日志文件及其包含的信息的列表。

<br/>

|日志文件名  |说明  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | 包含与媒体堆栈相关的信息。 这包括通道状态，例如所使用的解析、解码器和编码器，以及发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 会话状态。         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |记录与远程控制操作相关的信息，例如给定控件的时间戳和鼠标指针信息。          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |记录媒体堆栈跟踪事件。         |
|`Debug-0-s2790420889.blog`    | 包含与媒体代理相关的信息，包括呈现质量。          |
|`tscalling-0-2061129496.blog`   |记录 ts 调用 API 中的事件。       |

## <a name="desktop-logs"></a>桌面日志

有关Windows和 Mac 说明，请参阅 _“收集并启用日志记录_”部分。 桌面日志（也称为引导程序日志）包含在桌面客户端和浏览器之间发生的日志数据。 与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。 日志是基于文本的，可以使用自上而下格式的任何基于文本的编辑器进行读取。

若要收集 Linux 的日志，请执行以下操作：
- 单击系统托盘中的Microsoft Teams图标，然后选择 **“获取日志**”。
- 这些文件将在其中可用 `~/.config/Microsoft/Microsoft Teams/logs.txt`。

若要收集 Mac 日志，请执行以下操作：
- 单击Microsoft Teams中的“帮助”菜单，然后选择 **“收集支持文件**”。
- 该 `logs.txt` 文件将位于 _MSTeams 诊断日志 \<local date and time>_ 文件夹内的桌面文件夹中。

若要收集Windows日志，
- 单击系统托盘中的Microsoft Teams图标，然后选择 **“收集支持文件**”。
- 该`logs.txt`文件将在记事本中自动打开。

在调查登录Teams时，可能需要手动收集桌面日志。 这些日志文件位于 Windows 中的 %appdata%\Microsoft\Teams。

## <a name="browser-trace"></a>浏览器跟踪

对于某些类别的错误，Microsoft 支持部门可能需要收集浏览器跟踪。 此信息可以提供有关发生错误时Teams客户端状态的重要详细信息。

在启动浏览器跟踪之前，请确保已登录到Teams。 请务必在启动跟踪之前执行此操作，以便跟踪不包含敏感登录信息。

登录后，根据你的浏览器选择以下链接之一，然后按照提供的步骤操作。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [火狐](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步骤中，将对Azure 门户的所有引用替换为Teams客户端。
  
## <a name="webrtc-logs-in-browsers"></a>浏览器中的 WebRTC 日志
WebRTC 日志可以通过提供音频和视频呼叫的连接详细信息来帮助Microsoft 支持部门。 按照以下步骤访问 Edge (Chromium) 或 Chrome 中的 WebRTC 日志： 
  
1.  打开新选项卡并转到以下 URL 之一：
    -   边缘 (Chromium) ：`edge://webrtc-internals/`
    -   铬： `chrome://webrtc-internals/`
  
2.  打开Teams Web 应用程序并重现问题。
  
3.  返回到步骤 1 中访问的选项卡，你将看到至少两个选项卡：
    -   GetUserMedia 请求
    -   `https://teams.microsoft.com/url`

4.  选择具有Teams应用程序名称的选项卡并保存页面内容。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
