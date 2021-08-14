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
description: 了解调试、媒体和桌面日志Microsoft Teams、日志的查找位置，以及它们如何帮助进行监视和故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a39078371ffa30caab6ee43df90bc825c4c081a3
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235317"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>使用日志文件监视和排查Microsoft Teams

有三种类型的日志文件由客户端自动生成，可利用它们来帮助监视和排查Teams：

-   [调试日志](#debug-logs)

-   [媒体日志](#media-logs)

-   [桌面日志](#desktop-logs)

本文介绍这些日志及其使用方式。 有关排查特定问题的信息，请参阅：Teams[故障排除。](/MicrosoftTeams/troubleshoot/teams) 若要了解如何联系支持人员，请参阅 [获取支持](/microsoft-365/business-video/get-help-support)。 通过 Microsoft 支持创建支持请求时，支持工程师需要调试日志。 在创建支持请求之前，如果已处理调试日志，Microsoft 可以快速开始排查问题。 **只有** **Microsoft** 请求时，才需要媒体或桌面日志。

> [!NOTE]
> 本文中的"调试 **日志** "一词是指用于故障排除的日志。 但是，为这些日志生成的文件的名称 **中包含术语诊断** 日志。  

## <a name="collect-and-enable-logging"></a>收集和启用日志记录

出现问题时，必须收集日志。 只需单击几下鼠标，即可将日志收集在一起。

Windows：右键单击系统任务栏Teams图标，然后选择"收集 **支持文件"。** 

Mac：选择"帮助"菜单，然后选择"**收集支持文件"。**

调试、桌面和媒体日志将收集到一个文件夹中，其名称为 MSTeams 诊断日志 <local data and time> 。 向 Microsoft 支持人员提出支持请求时，可以压缩和共享此文件夹。 该文件夹将包含桌面、会议 (媒体) 和调试 (Web) 。 可以使用以下键盘快捷方式收集文件：

Windows：Ctrl + Alt + Shift + 1

Mac：Option + Command + Shift + 1

默认情况下，媒体日志记录已关闭。 若要启用媒体日志记录，用户必须在客户端中Teams选项。 转到 **"设置**  >  **常规**"，然后选择"为会议诊断启用日志记录 **(重启Teams) 。** 必须Teams客户端才能开始日志记录。

> [!NOTE]
> 如果启用了媒体日志记录，"会议"文件夹中将包含其他文件，这些文件是调查音频和视频问题所必需的。 如果未启用媒体日志记录，则可用日志数有限。

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

请参阅 _收集和启用日志记录_ 部分，了解 Windows 和 Mac 的说明。 调试日志由 Windows 和 Mac 桌面客户端以及基于浏览器的客户端生成。 日志基于文本，从下而上读取。 可以使用任何基于文本的编辑器读取这些日志，并且登录到客户端时会创建新日志。

调试日志显示以下数据流：

-   登录

-   到中间层服务的连接请求

-   通话/对话

收集 Linux 日志：键盘快捷方式：Ctrl + Alt + Shift + 1 文件将在 ~/Downloads 中提供

收集浏览器日志：键盘快捷方式：Ctrl + Alt + Shift + 1 %userprofile%\Downloads 中提供文件

## <a name="media-logs"></a>媒体日志

请参阅 _收集和启用日志记录_ 部分，了解 Windows 和 Mac 的说明。 媒体日志包含有关会议中音频、视频和屏幕共享的Teams数据。 它们对于链接到呼叫相关问题的支持案例是必需的。

默认情况下，媒体日志记录已关闭。 若要记录会议Teams数据，用户必须在客户端中打开Teams选项。 转到 **"设置** 常规"，选中"为会议诊断启用日志记录 (Teams) "复选框，重启Teams并重现  >  问题。  

将日志文件发送给 Microsoft 支持人员时，请验证日志文件的时间戳，确保日志涵盖重现问题的时间范围。

收集 Linux 日志：这些文件将在 ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog 和 *~/.config/Microsoft/Microsoft Teams/skylib/*.blog 中提供。

下面是生成的日志文件及其包含的信息的列表。

|日志文件名  |说明  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | 包含与媒体堆栈有关的信息。 这包括通道状态，例如分辨率、使用的解码器、编码器、已发送和接收的帧数，以及基于相机和视频的屏幕共享 (VBSS) 状态。         |
|rtmcontrol.msrtc-0-2415069487.blog      |记录与远程控制操作相关的信息，例如提供控件时时间戳和鼠标指针信息。          |
|Teams_MediaStackETW-2-U-xr-U.etl      |记录媒体堆栈跟踪事件。         |
|Debug-0-s2790420889.blog    | 包含与媒体代理有关的信息，包括呈现质量。          |
|tscalling-0-2061129496.blog   |在 ts-calling API 中记录事件。       |

## <a name="desktop-logs"></a>桌面日志

请参阅 _收集和启用日志记录_ 部分，了解 Windows 和 Mac 的说明。 桌面日志也称为启动程序日志，包含桌面客户端与浏览器之间发生的日志数据。 与媒体日志一样，仅当 Microsoft 要求时，才需要这些日志。 日志基于文本，可以使用任何基于文本的编辑器以自上而下的格式读取。

若要收集 Linux 的日志：单击Microsoft Teams任务栏中的"日志"图标，然后选择"获取 **日志"。**
这些文件将在 ~/.config/Microsoft/Microsoft Teams/logs.txt 中提供。  

## <a name="browser-trace"></a>浏览器跟踪

对于某些类别的错误，Microsoft 支持可能会要求你收集浏览器跟踪。 此信息提供有关发生错误时客户端Teams状态的重要详细信息。

在开始浏览器跟踪之前，请确保已登录到 Teams。 在开始跟踪之前，必须这样做，以便跟踪不包含敏感的登录信息。

登录后，根据浏览器情况选择以下链接之一，然后按照提供的步骤操作。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步骤中，将 Azure 门户的所有引用替换为 Teams 客户端。
  
## <a name="webrtc-logs-in-browsers"></a>浏览器中的 WebRTC 日志
WebRTC 日志可以通过为音频和视频呼叫提供连接详细信息来帮助 Microsoft 支持。 按照步骤访问 Edge (Chromium) 或 Chrome 中的 WebRTC 日志： 
  
1.  打开新选项卡并转到以下 URL 之一：
    -   Edge (Chromium) ："edge://webrtc-internals/"
    -   Chrome："chrome://webrtc-internals/"
  
2.  打开 Teams Web 应用程序并重现问题。
  
3.  返回到步骤 1 中访问的选项卡，你将看到至少两个选项卡：
    -   GetUserMedia 请求
    -   https://teams.microsoft.com/url

4.  选择包含应用程序名称的选项卡Teams并保存页面内容。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
