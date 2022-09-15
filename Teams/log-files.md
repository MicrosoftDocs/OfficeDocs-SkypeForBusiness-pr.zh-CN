---
title: 在 Teams 中配置日志文件以进行监视和故障排除
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
description: 了解 Microsoft Teams 生成的调试、媒体和桌面日志、可在其中找到日志以及如何帮助监视和故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2edddca64bf0cb50dc29758fd60bc397cbc00f8b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705811"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>在 Teams 中配置日志文件以进行监视和故障排除

客户端自动生成了三种类型的日志文件，这些文件可用于帮助监视和排查 Teams：

-   [调试日志](#debug-logs)

-   [媒体日志](#media-logs)

-   [桌面日志](#desktop-logs)

本文介绍这些日志及其使用方式。 有关排查特定问题的信息，请参阅： [Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)。 

有关从Microsoft Teams 会议室设备收集日志的信息，请[参阅“下载设备日志](/microsoftteams/rooms/rooms-manage#download-device-logs)”。

有关如何联系支持人员的信息，请参阅 [“获取支持](/microsoft-365/business-video/get-help-support)”。

> [!NOTE]
> 在本文中，术语 **“调试日志”** 是指用于故障排除的日志。 但是，为这些日志生成的文件将包含其名称中的术语 **诊断日志** 。  

## <a name="logs-overview"></a>日志概述

一旦出现问题，必须立即收集日志。

通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。 在创建支持请求之前手动启用调试日志可让 Microsoft 快速开始对问题进行故障排除。 仅当 Microsoft 请求时，才需要 **媒体** 或 **桌面** 日志。

调试、桌面和媒体日志将收集在名为 _MSTeams 诊断日志 \<local date and time\>_ 的文件夹中。 使用pomoc techniczna firmy Microsoft打开支持请求时，可以压缩和共享此文件夹。 该文件夹将包含桌面、会议 (媒体) 和调试 (Web) 的文件夹。 可以使用以下键盘快捷方式收集文件：

- Windows： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac： <kbd>选项</kbd> + <kbd>命令</kbd> + <kbd>班次</kbd> + <kbd>1</kbd>


如果特定会议或实时事件出现问题，则将 URL 与会议关联会很有帮助。 该 URL 提供其他信息，以帮助确定日志中的确切会议或实时事件。 可以从会议的任何参与者或直播活动的演示者或制作者收集此信息。 可以通过将鼠标悬停在联接 URL 上并选择 **复制超链接** 来捕获此 URL。

> [!NOTE]
> 如果启用了媒体日志记录，则会议文件夹中将包含其他文件，这是调查音频和视频问题所必需的。 如果未启用媒体日志记录，则可用的日志数量有限。
  
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

调试日志由 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成。 日志基于文本，从自下而上读取。 可以使用任何基于文本的编辑器读取它们，并在登录到客户端时创建新日志。

调试日志显示以下数据流：

-   登录

-   连接到中间层服务的请求

-   通话/对话

若要收集 Linux 的日志，请执行以下操作：
- 键盘快捷方式： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `~/Downloads`

若要收集浏览器和 Windows 的日志，请执行以下操作：
- 键盘快捷方式： <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `%userprofile%\Downloads`

若要收集 Mac 日志，请执行以下操作：
- 键盘快捷方式： <kbd>选项</kbd> + <kbd>命令</kbd> + <kbd>班次</kbd> + <kbd>1</kbd>  
- 文件将在其中可用 `~/Downloads`

## <a name="media-logs"></a>媒体日志

媒体日志包含有关 Teams 会议中音频、视频和屏幕共享的诊断数据。 对于与呼叫相关的问题相关的支持案例，需要使用它们。

如果 CPU 为：
- 任何 Apple M1
- 任何 Intel Xeon
- 除 U、G7、M 和 MQ 系列之外的任何 Intel i9
- 除 U、G7、M 和 MQ 系列之外的任何第 6 代及更高版本的 Intel i7

否则，默认情况下会将其关闭。 有两种方法可以记录 Teams 会议的诊断数据：

- 管理员配置 - 可以为最终用户管理媒体日志
- 最终用户配置 - 最终用户可以打开媒体日志

### <a name="admin-configuration"></a>管理员配置

为最终用户管理媒体日志可提供无缝的故障排除体验，尤其是在问题间歇性时。 管理员可以使用 TeamsMediaLoggingPolicy cmdlet 为用户启用和管理媒体日志记录。

阅读 [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) for PowerShell cmdlet 和详细信息。

### <a name="end-user-configuration"></a>最终用户配置

为使最终用户能够记录 Teams 会议的诊断数据，他们必须在 Teams 客户端中启用该选项。 他们将转到 **“常规设置”** > **，****选中音频、视频和屏幕共享诊断数据 (“启用媒体日志”)** 复选框，然后重现问题。

> [!NOTE]
> 当用户注销 Teams 时，媒体日志记录将重置为默认值。

### <a name="collecting-and-sending-media-logs"></a>收集和发送媒体日志

在将日志文件发送到 Microsoft 支持之前，请验证日志文件的时间戳，以确保在重现问题时日志涵盖时间范围。

若要收集 Linux 的日志，请执行以下操作：  
- 这些文件将在以下位置可用：
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

若要收集适用于 Windows 的日志，请执行以下操作：  
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

桌面日志（也称为引导程序日志）包含在桌面客户端和浏览器之间发生的日志数据。 与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。 日志是基于文本的，可以使用自上而下格式的任何基于文本的编辑器进行读取。

若要收集 Linux 的日志，请执行以下操作：
- 单击系统托盘中的 Microsoft Teams 图标，然后选择 **“获取日志**”。
- 这些文件将在其中可用 `~/.config/Microsoft/Microsoft Teams/logs.txt`。

若要收集 Mac 日志，请执行以下操作：
- 单击 Microsoft Teams 中的“帮助”菜单，然后选择 **“收集支持文件**”。
- 该 `logs.txt` 文件将位于 _MSTeams 诊断日志 \<local date and time>_ 文件夹内的桌面文件夹中。

若要收集适用于 Windows 的日志，请执行以下操作：
- 单击系统托盘中的 Microsoft Teams 图标，然后选择 **“收集支持文件**”。
- 该 `logs.txt` 文件将在记事本中自动打开。

在调查登录 Teams 时遇到的问题时，可能需要手动收集桌面日志。 这些日志文件位于 Windows 中的 %appdata%\Microsoft\Teams。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

[Teams 的浏览器日志和跟踪](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
