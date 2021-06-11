---
title: Microsoft Teams 所需的桌面客户端诊断数据
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 的策略控制的桌面属性和事件列表。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c255fd02342eb6db1878608ad2da09683d7a83ec
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863223"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 所需的桌面诊断数据

以下文章包含 Microsoft Teams 桌面事件的列表，以及各个事件收集的属性列表。

要详细了解诊断数据，包括如何控制发送到 Microsoft 的诊断数据，请参阅 [从 Teams 应用发送到 Microsoft 的诊断数据](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft)。 要查看要发送到 Microsoft 的诊断数据，可使用 [诊断数据查看器](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)。

## <a name="events"></a>事件

> [!NOTE]
> 下面列出了所有事件的通用属性，若要评论它们，请参阅[与所有事件一起发送的属性](#properties-sent-with-all-events)。

### <a name="logging"></a>日志记录

> [!NOTE]
> 有关记录事件的属性的详细信息，请参阅 [与日志记录事件一起发送的属性](#properties-sent-with-logging-events)。

- **adal-anonymous-mac.ts:this.logger.logError** - 记录在 Mac 设备上匿名登录时发生的通用 sso 错误。
- **adalAnonymousUtil.ts：loggingService.getInstance** - 记录应用程序无法启动匿名用户身份验证的错误操作语句。
- **adal-anonymous-windows.ts：this.logger.logError** -  记录在windows设备上匿名登录时发生的通用 sso 错误。
- **adalBase.ts： this.loggingService.logError** - 记录确定用户配置文件为NULL或空的的所需信息。
- **adal-impl-mac.ts:this.loggingService.logError** - 记录解析身份认证期间分析接收到的遥测数据时发生的问题，或在 Mac 设备上登录时发生的通用 sso 错误。
- **adal-rigel-windows.ts：this.logger.logError** -一般性日志记录声明，表示在登录到我们的会议室设备上时出现了一个通用sso错误。
- **adal-sso-windows.ts：this.loggingService.logError** -记录在 Windows 设备上登录时发生的通用sso错误、启动聊天服务时的错误或登录失败信息的错误。
- **appOnlineService.ts： loggingService.getInstance**  -记录由于在启动过程中无法解析设置或下载预用户认证、预授权设置时发生的错误。
- **appStart.ts：loggingService.logError** - 记录应用程序无法启动、磁盘空间错误、有效证书错误或未能找到正确证书、以及重启应用程序时发生的错误。
- **browserWindowHttp.ts：this.loggingService.logError** - 记录信息以表明，由于文件系统问题而无法更新应用程序。
- **contextInstallService.ts： loggingService.getInstance** - 记录以下情况下发生的错误：
  - 试图解析或读取一个文件或解析一个对情境式安装功能至关重要的URL。
  - URL缩短器试图运行情境式安装功能。
- **crashManager.ts：loggingService.logError** - 当应用程序崩溃时，记录信息以确定出错的原因。
- **localStorageService.ts： loggingService.getInstance** - 当必要的启动数据无法正常加载运行应用程序时，记录错误的发生。
- **logProviders\pageDumpProvider.ts：loggingService.getInstance** - 记录应用程序崩溃时的错误信息。
- **multiWindowManager.ts： this.logError** - 当必要的启动数据无法正常加载运行应用程序时，记录错误的发生。
- **nativeElectronNotifications\osNotificationService.ts： this.loggingService.logError** - 此事件记录了尝试启动有关失败的通知时发生的错误。
- **OutlookMeetingAddinHelper.ts： loggingService.getInstance** - 记录当使用Outlook会议加载项试图连接到会议时发生的错误。
- **recoveryManager.ts：loggingService.getInstance** - 记录更新回滚期间发生的错误。
- **renderer\startPage\startPage.ts：this.logger.logError** - 记录应用程序起始页发生的错误。
- **settingsService.ts：loggingService.getInstance** - 记录设置应用程序时发生的错误。
- **updateInfo.ts：loggingService.getInstance** - 记录传输更新时发生的错误。
- **updatenotification.js：this._loggingService.logError** -记录磁盘空间问题的发生。
- **utility.ts：loggingService.logError** -记录访问本地文件（应用程序中的文件）的错误。
- **utility.ts：loggingService.getInstance** - 记录可用磁盘空间中、显示问题、url问题、cookie问题、协议或计算机上的注册密钥问题来加载应用程序的错误。
- **windowmanager.js：this._loggingService.logError** - 记录Cookie问题、白屏问题、桌面和壳层通信之间的问题、url问题、加载页面信息的错误、进程渲染的错误、网络连接问题的发生。
- **windowmanager.js：loggingService.getInstance** - 记录表明恢复窗口无法显示的信息。

### <a name="outlook-addin"></a>Outlook 加载项

> [!NOTE]
> 有关Outlook加载项事件属性的详细信息，请参阅[与Outlook加载项事件一起发送的属性](#properties-sent-with-outlook-addin-events)。

- **joinmeetingoperation** - 记录用户加入会议所需的信息。
- **meetingaddinapplifecycle** - 记录应用程序状态的信息，如启动或退出。
- **meetingaddinloadtime** - 记录从Outlook加载会议信息所需的时间。
- **openmeetingoperation** - 记录召开预定会议所需的信息。
- **savemeetingoperation** - 在进行会议安排的同时，记录保存会议所需的信息。

### <a name="scenario"></a>使用场景

> [!NOTE]
> 有关场景事件属性的详细信息，请参阅 [与场景事件一起发送的属性](#properties-sent-with-scenario-events)。

- **desktop_app_load** -记录确定桌面应用程序已启动，该服务应该被初始化，以及该服务能够被初始化所需的信息。
- **desktop_app_not_ready** - 记录确定桌面应用程序未准备好运行所需的信息。
- **desktop_install** - 记录确定桌面应用程序已成功安装或安装失败所需的信息。
- **desktop_previous_lifecycle_invalid** - 记录确定桌面应用程序在之前运行后重新启动，然后崩溃所需的信息。

### <a name="tracking"></a>跟踪

> [!NOTE]
> 有关跟踪事件属性的详细信息，请参阅 [与日志跟踪事件一起发送的属性](#properties-sent-with-tracking-events)。

- **deeplink_scenario_missing** - 已从深层链接启动 Teams，但是未提供遥测/诊断。
- **desktop_app_initialized** - 记录初始化桌面应用程序时确定应用程序是否已成功启动所需的信息。
- **desktop_app_quit_exception** - 应用程序在试图关闭时崩溃。
- **desktop_blankScreenDetected** - 记录桌面应用程序呈现空白屏幕时确定错误所需的信息。
- **desktop_blankScreenDetectedAfterRepaint** - 在检测渲染尝试时，检测到该页面为空白。
- **desktop_blankScreenRecoveredAfterRepaint** - 已从之前未渲染屏幕的渲染问题中恢复。
- **desktop_configuration_failed_to_save** - 收集在桌面设置无法保存时，确定配置错误所需的信息。
- **desktop_navigation_error_recovery** - 收集在尝试五次后页面仍旧加载失败时，确定桌面导航错误所需的信息。
- **desktop_previous_gpu_crashed** - 记录在桌面崩溃时，确定图形处理单元错误所需的信息。
- **desktop_previous_plugin_host_crashed** - 收集确定与桌面应用程序崩溃相关的媒体堆栈问题所需的信息。
- **desktop_recovery_cleared_user_data** - 记录应用程序多次崩溃，其应用程序必须清除本地缓存才能恢复。
- **desktop_settings_blank_on_load** - 这是提示应用程序设置不存在的错误。
- **desktop_settings_failed_to_load** - 收集在桌面设置无法加载时确定原因所需的信息。
- **desktop_silent_restart** - 客户端更新是阶段性的，并且客户端的更新不会影响用户的使用。
- **desktop_terminated** - 记录在用户关闭桌面应用程序时，确定进程间通信是否已断开所需的信息。
- **desktop_uncaught_exception** 对未定义的对象进行函数调用，这将导致崩溃/应用重启。
- **desktop_write_storage_failed** - 当桌面应用程序无法写入存储时，记录确定磁盘错误所需的信息。
- **registration_failed** - 记录解决插件注册失败所需的信息。
- **registration_success** - 记录确定插件注册是否成功所需的信息。
- **security_unsupported_ipc_channel** - 不被允许的进程间消息是入站的。
- **sfb_running_not_connected** 检测到 Skype for Business 应用程序未运行。
- **sfb_not_running** - 记录呼叫Skype of Business的 "等待响应 "已超时。
- **sfb_never_replied** - 跟踪与Skype for Business通信时，无API响应。
- **server_error_hit** - 追踪与Skype for Business通信的ipc管道发生的错误。
- **unexpected_sfb_ipc_disconnection** - 记录确定服务连接失败所需的信息。
- **unregister_failed** - 记录确定注销Outlook会议插件的出错所需的信息。

## <a name="userbi-panelaction"></a>UserBI 面板视图

> [!NOTE]
> 关于UserBI 面板视图事件属性的详细信息，请参阅[与UserBI面板视图事件一起发送的属性](#properties-sent-with-userbi-panelaction-events)。

- **inlinereply** - 记录用户是否已从通知中回复信息。
- **toastclick** - 记录用户点击导航到toast通知的消息项，以监控服务SLA，并加载与toast通知相应的响应。
- **toastdismiss** - 记录当用户拒绝渲染toast通知时，确定错误和延迟所需的信息。

- **toast_skip** - 记录避免toast通知传送延迟所需的信息。
- **toastdismiss** - 记录当toast通知的渲染超时时，确定错误和延迟所需的信息。

### <a name="userbi-panelview"></a>UserBI 视图面板

> [!NOTE]
> 关于UserBI 视图面板事件属性的详细信息，请参阅[与UserBI视图面板事件一起发送的属性](#properties-sent-with-userbi-panelview-events)。

- **toastshow** -记录确定toast已被渲染所需的信息。

## <a name="property-lists"></a>属性列表

### <a name="properties-sent-with-all-events"></a>与所有事件一起发送的属性

| 属性名称                              | 说明                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | 事件生成时间                                              |
| EventInfo_Name                             | 事件名称-用于区分事件类型             |
| EventInfo_BaseType/name                    | 事件名称 - 用于区分一个事件中的事件类型 |
| EventInfo_Sequence                         | 事件序列                                              |
| userAgent                                  | 浏览器代理字符串                                               |
| userpdclevel                               | 用户的隐私数据控制设置                           |
| eventpdclevel                              | 活动的隐私数据控制分类级别             |
| AppInfo_Language                           | 应用语言                                                       |
| clientType/AppInfo_ClientType              | 正在运行的应用程序客户端类型                               |
| environment/AppInfo_Environment            | 服务于用户请求的工程环境               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | 应用的版本                               |
| 构建时间                                  | 应用程序在工程系统中构建的时间戳。            |
| osversion/DeviceInfo_OsVersion             | 操作系统版本                                                         |
| AppInfo_ProcessArchitecture                | 系统体系结构（32bit/64bit）                                  |
| 首选区域                           | 用户的首选区域                                      |
| locale/AppInfo_Locale                      | 应用程序区域                                                         |
| os/DeviceInfo_OsName                       | 操作系统名称                                                            |
| UserInfo_Language                          | 所选用户语言                                             |
| UserInfo_Id                                | 用户 ID                                                            |
| UserInfo_TenantId/TenantId                 | 租户 ID                                                          |
| ring/UserInfo_Ring                         | 有助于以分阶段方式交付应用程序的概念          |
| 地区                                     | 为用户请求提供服务的数据中心区域                       |
| UserInfo_ConfigIds/UserInfo_Etag           | ID有助于在不同的实验/转动中识别用户的ID。     |
| DeviceInfo_BrowserName                     | 浏览器名称                                                       |
| DeviceInfo_BrowserVersion                  | 浏览器版本。                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | 帮助识别设备的ID                                  |
| totalMemory                                | 设备的硬件内存                                      |
| 核心                                      | 设备的硬件核心                                       |
| cpu的速度                                   | 设备的硬件 cpu 速度                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | 设备的CPU体系结构                                     |
| UserRole                                   | 帮助标识租户中的用户角色                               |
| DeviceInfo_WindowsMode                     | 帮助识别 Windows 安全模式                               |
| desktopSession/Session_Id                  | 帮助标识会话                                           |
| dbOpen                                     | 捕获本地数据库的状态                               |
| UserInfo_Upn                               | 用户标识符的单侧散列                                  |

### <a name="properties-sent-with-logging-events"></a>与日志记录事件一起发送的属性

| 属性名称         | 说明                                                        |
|-----------------------|--------------------------------------------------------------------|
| 消息               | 捕获有关日志记录的详细消息                          |

### <a name="properties-sent-with-scenario-events"></a>与场景事件一起发送的属性

| 属性名称                     | 说明                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | 场景的状态                                                               |
| Scenario_Step                     | 场景中的步骤                                                                 |
| 序列                          | 场景的顺序号                                                    |
| delta                             | 完成场景中不同步骤所需的时间。                               |
| 消耗                           | 场景开始后的时间                                                    |
| 场景                          | 唯一识别场景                                                       |
| Scenario_Name                     | 场景名称                                                               |
| errorInfo                         | 场景中可能发生的错误信息                       |
| 会话                           | 唯一会话 ID                                                                  |
| freeMemory                        | 捕获可用的空闲内存                                                     |
| processMemory                     | 捕获进程内存                                                            |
| scenarioDelta                     | 捕获两个场景步骤之间的时间差异                                   |
| Session_DesktopId                 | 唯一会话 ID                                                                  |
| machineLocked                     | 捕获计算机是否被锁定                                          |
| windowIsVisible                   | 若应用程序窗口可见，则捕获以便使用                                      |
| appStates/webAppStates            | 记录应用所经历的应用状态列表。这有助于崩溃调查，因为我们可以看到应用程序处于什么状态 |
| crashDesktopSession               | 捕获崩溃会话的 ID                                                 |
| appRuntime                        | 捕获应用程序的运行时间                                                        |
| diagnosticEvents                  | 应用程序崩溃前的最后50个网页应用程序诊断事件                                 |
| 活动​​                        | 崩溃前的最后50个已发生的用户场景名称                            |
| crashSession                      | 捕获崩溃会话的 ID                                                 |
| crashId                           | 捕获崩溃会话的 ID                                                 |
| isPreviousLifecycleValid          | 之前的应用程序是否已完全初始化并成功终止             |
| isSettingValid                    | 预认证设置是否有效                                                 |
| rollbackReason                    | 撤消应用程序的原因                                            |
| deeplinkType                      | 深层链接的类型                                                               |
| watchdogCrash                     | 是否因挂机而导致应用程序崩溃                                                    |
| 协议                         | 用于启动应用程序的协议                                                    |
| electronBuild                     | 电子应用程序的内部版本                                                      |
| 分发                      |  Teams是通过exe或msi或dmg或pkg等方式安装的。                    |
| updateTimeOfDay                   | 应用程序的更新时间                                                           |
| launchPath                        | Teams是否安装在%LOCALAPPDATA%， %PROGRAMFILES% 或其他位置上   |
| loggedIn                          | 如果用户已登录                                                          |
| envType/complianceEnvironmentType | 商业云或私有云（例如，DoD、GCC-High等）                              |
| cpuusage                          | CPU 使用率                                                                          |
| installationSource                | 用户拥有的安装类型                                                      |
| adalVersion                       | 身份验证库的版本                                                        |
| asyncStart                        | 应用程序是使用同步启动还是异步启动                                 |
| 尝试                          | 在显示屏蔽屏幕之前，对用户进行在线检查尝试的次数 |

### <a name="properties-sent-with-tracking-events"></a>与跟踪事件一起发送的属性

| 属性名称                      | 说明                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | 捕获跟踪事件的名称                                              |
| numVisibleNotifications            | 可见应用程序通知的数量                                      |
| giphyEnabled                       | Giphy 服务是否已被启用                                                |
| 错误                              | 捕获与跟踪事件相关的错误详细信息                             |
| 方法                             | GET 或 POST的协议方法                                                      |
| 频道                            | 捕获应用程序内的进程间通信通道                      |
| windowTitle                        | 与事件相关的显示窗口的类型                                     |
| 消息                            | 错误消息的类型                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | 捕获用于会话调试用途的唯一 ID |
| ResponseCode                       | 捕获服务呼叫的响应代码                                      |
| errorUrl                           | 无法加载的 URL                                                      |
| errorCode                          | 捕获错误代码                                                              |
| ssoEventData                       | 身份验证状态                                                  |
| correlationId                      | 用于将事件与服务端相关联以便进行调试的 ID                      |
| errorDescription                   | 捕获错误代码的说明                                            |
| 源                             | 获取Teams应用程序的方法以及Teams的安装包的类型       |
| windowIsDestroyed                  | 在事件进行期间应用程序窗口的 True/False 状态                             |
| windowIsFocused                    | 在事件进行期间应用程序窗口的 True/False 状态                             |
| windowIsVisible                    | 事件发生时应用程序是否可见                                  |
| windowIsMinimized                  | 在事件进行期间应用程序窗口的 True/False 状态                             |
| windowIsMaximized                  | 在事件进行期间应用程序窗口的 True/False 状态                             |
| windowIsFullscreen                 | 在事件进行期间应用程序窗口的 True/False 状态                             |
| distSrc                            | 捕获用户登陆到应用的分布源                    |
| 重试                            | 尝试连接到端点时的重试次数                            |
| uses_slimcore                      | 如果网页调用使用 slimcore，则为 True 或 false                                      |
| persistCookieExpiresIn             | 网页应用程序cookie的剩余有效期                             |
| tenantName                         | 应用程序用户的租户名称                                       |
| appStartReason                     | 应用程序会话的启动方式，如用户启动、更新后启动等。 |
| machineLocked                      | 事件期间机器是否被锁定或未被锁定                        |
| 数据                               | 捕获用于场景调查的技术数据                               |
| appRuntime                         | 捕获应用程序的运行时间                                                      |
| 活动​​                         | 崩溃前的最后50个已发生的用户场景名称                          |
| timeSinceActivity                  | 距离上次用户活动的时间                                                    |
| appStates                          | 记录桌面应用程序所经历的应用状态列表，这有助于崩溃调查，因为它显示了桌面应用所处的状态 |
| timeSinceAppState                  | 应用程序状态更改后的时间                                                 |
| webAppStates                       | 记录网页客户端所经历的应用状态列表，这有助于崩溃调查，因为它显示了网页客户端所处的状态 |
| timeSinceWebAppState               | 网页应用程序状态更改后的时间                                             |
| diagnosticEvents                   | 应用程序崩溃前的最后50个网页应用程序诊断事件                               |
| timeSinceLastDiagnosticEvent       | 距离上次发送诊断事件的时间                                            |
| timeSinceSecondLastDiagnosticEvent | 距离倒数第二次发送诊断事件的时间                                     |
| appInitialized                     | Webapplication 是否已启动                                               |
| TargetVersion                      | 应用程序版本将更新至                                    |
| 端口                               | 互联网信息端口号                                                     |
| originalUrl                        | 正在渲染页面的原始位置                                         |
| deeplinkId                         | Teams链接目标类型的 GUID                                          |
| appSessionEnd                      | 在应用程序会话结束时是否发生事件                             |
| EventData                          | 捕获机器状态和应用程序配置，以便在出现问题时帮助进行调试        |
| deeplinkType                       | 深层链接的类型（聊天、会议和频道）                                    |
| previousUpdateUrl                  | 应用程序最后一次获取更新的位置                        |
| previousUpdateVersion              | 上一版本的应用程序已更新为                                          |
| previousUpdateTime                 | 应用程序二进制文件最后更新的时间                                      |
| 协议                           | 链接的处理程序类型，例如文件或图像                                     |
| 文件                              | 与事件相关联的文件的类型，如应用程序缓存或 GPU 缓存    |
| Perf_WorkingSetSizeKB              | 内存缓存大小                                                             |
| isTimeboxingWebAppInitialize       | 应用程序是否在时间盒计数器失效前完成初始化                          |
| isExp                              | 正在使用的应用程序版本是否是实验的一部分                          |
| deviceType                         | 设备的捕获类型                                                      |
| sanitizedErr                       | 捕获错误信息的净化版本。                              |
| rigelVersion                       | 捕获 rigel 设备的版本                                                 |
| DeviceInfo_OsSku                   | 捕获操作系统 SKU 的信息                                                      |
| isLoggedOut                        | 捕获用户是否已注销                                               |
| complianceEnvironmentType          | 商业云或私有云（例如，DoD、GCC-High等）                           |
| restartTimes                       | 以前重新启动的确切次数                                                 |
| Skype_ResultCode                   | 捕捉Skype和Teams之间的交互通信的结果                 |
| cpumodel                           | 捕获 CPU 模型                                                            |
| isSlimCoreRunningOutproc           | Slimcore 组件是否正在自己的进程中运行                         |
| isSlimCoreStartedAsync             | 内部音频/视频（A/V）栈的启动类型                               |
| networkState                       | 捕获网络状态                                                    |
| desktopBuildAge                    | 在事件发生时，应用程序版本的新旧程度                                   |
| vdiMode                            | 捕获应用程序是否在VDI模式下运行                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>与UserBI视图面板事件一起发送的属性

| 属性           | 说明                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | 提供给用户的面板Uri                   |
| Panel_Type         | 用户访问的面板类型                          |
| Team_Id            | 用户进行操作的团队的ID |
| Thread_Id          | 用户访问的线程的 ID               |
| Panel_PreviousUri  | 之前的面板的 URI                                |
| Panel_Region       | 应用程序中托管了面板的区域             |
| Panel_LaunchMethod | 启动面板的方法              |
| Panel_PreviousType | 之前的面板的类型                               |
| Thread_Type        | 用户访问的线程类型                          |
| Panel_LaunchSource | 已启动的面板的数据源信息        |
| Tab_Type           | 用户访问的选项卡类型                         |
| Team_Type          | 用户访问的团队类型                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>与UserBI动作面板事件一起发送的属性

| 属性名称         | 说明                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | 被用户操作访问的资源的 Uri                  |
| Panel_Uri             | 提供给用户的面板Uri                             |
| Action_Gesture        | 用户在应用程序上执行的手势类型                       |
| Action_ScenarioType   | 与功能商业指标相关的功能分组       |
| Panel_Type            | 用户访问的面板类型                                    |
| Action_Outcome        | 用户所执行的操作的结果                            |
| Team_Id               | 用户进行操作的团队的ID           |
| Module_Type           | 承载用户操作所在模块的类型                        |
| Module_Name           | 承载用户操作所在模块的名称                        |
| Module_Summary        | 屏蔽用户操作的模块摘要                       |
| Thread_Id             | 用户访问的线程的 ID                         |
| Panel_PreviousUri     | 之前的面板的 URI                                          |
| Panel_Region          | 应用程序中托管了面板的区域                       |
| Panel_LaunchMethod    | 启动面板的方法                        |
| Panel_PreviousType    | 之前的面板的类型                                         |
| Thread_Type           | 用户访问的线程类型                                    |
| Module_State          | 用户访问的模块的状态                               |
| Action_Scenario       | 与商业指标相关的一组功能中的功能 |
| Panel_LaunchSource    | 已启动的面板的数据源信息                  |
| Tab_Type              | 用户访问的选项卡类型                                   |
| Team_Type             | 用户访问的团队类型                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>与Outlook加载项事件一起发送的属性

| 属性名称                   | 说明                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | 加载项将帐户与Teams帐户进行比较，以确定是否允许创建，如果比较失败，则会发送此事件。 |
| AccountComparisonSuccessful     | 加载项将帐户与Teams帐户进行比较，以确定是否允许创建，如果比较成功，则会发送此事件。 |
| AdalVersion                     | 使用的身份验证库的版本                               |
| AddinBitness                    | 加载项版本                                                         |
| AddinLanguage                   | 正在使用的加载项字符串的语言                                     |
| AggregatorSetupCompletedTime    | 加载项加载的设置时间                                              |
| AppDomainCreatedTime            | 加载项加载初始化应用程序域的时间                            |
| AppointmentDisplayTime          | 在创建会议期间显示预约项目的时间 |
| AuthenticationCompletedTime     | 对特定请求进行身份验证的时间            |
| ConnectionMode                  | 表示用户的主要Exchange账户的连接模式     |
| ConnectionStartedTime           | Outlook 呼叫 OnConnection 的时间                                     |
| ErrorDetails                    | 捕获错误的细节                                            |
| ErrorName                       | 捕获错误的名称                                               |
| ExchangeVersion                 | 捕获Exchange的版本                                             |
| IsSmtpFormatError               | SMTP地址错误                                                    |
| IsTeamsRunning                  | 捕获是否有团队进程正在运行                             |
| IsTeamsUserLoggedOut            | 捕获用户是否已注销 Teams                              |
| LanguageSetupCompletedTime      | 语言设置完成的时间                               |
| ManagedConnectTime              | 管理插件收到连接回调的时间。               |
| ManagedOnStartupTime            | 管理开始启动的时间                                    |
| MTFetchCompleted                | MT 会议选项请求完成的时间                        |
| NetFrameworkVersion             | 使用的 .nET Framework                                                      |
| NetworkAvailable                | 网络是否可用                                                     |
| OperationStartTime              |  不同操作开始的时间                                  |
| OsBitness                       | OS的位                                                            |
| OutlookLanguage                 | 捕获 Outlook 应用程序的语言                                     |
| OutlookVersion                  | 捕获Outlook应用程序的版本                                          |
| OwnerResolutionTime             | 解析会议所有者的时间                                        |
| ParseResponseCompletedTime      | 已完成的响应解析时间                                  |
| RecipientResolutionError        | 解析收件人时出现的错误细节                                 |
| RecipientsResolutionTime        | 解析所有收件人的总时间                                     |
| RehydrateCompletedTime          | 从 Outlook 中读取属性的时间                               |
| SaveToOutlookCompletedTime      | 属性储存至 Outlook 中的时间                                |
| ServiceRequestStartTime         | 服务请求的开始时间                                        |
| ServiceResponseReceiveTime      | 服务的响应时间                                        |
| SettingsInitializeCompletedTime | 设置初始化的时间                                           |
| SetupLoggingCompletedTime       | 设置日志记录的时间                                             |
| ShutdownBeginTime               | 开始关闭加载项的时间                                       |
| ShutdownCompletedTime           | 关机完成的时间                                             |
| StartupBeginTime                | 开始启动加载项的时间                                        |
| StartupCompletedTime            | 启动完成的时间                                              |
| TeamsDeployment                 | 部署Teams客户端（开发、生产）                                   |
| TeamsRing                       | 当前用户已登录Teams客户端的振铃                            |
| TeamsVersion                    | 捕获Teams应用程序的版本                                            |
| TelemetrySetupCompletedTime     | 完成遥测设置的时间                                   |
| UpnMismatch                     | Outlook 与Teams 之间是否存在 upn 不匹配的情况                  |
| UserDomain                      | 用户的域                                                       |
| ViewUpdatedTime                 | 视图获取更新的时间                                           |
