---
title: Skype for Business Server 2015 中的新增功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的新功能。 有关新的客户端体验的详细信息，请参阅 Lync 现在为 Skype for Business--了解新增功能。
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221082"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的新增功能

**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中的新功能。 有关新的客户端体验的详细信息，请参阅[Lync 现在为 Skype For business--了解新增功能](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync 现在是 Skype for Business，这是一种通信和协作平台，通过 Skype 提供的企业级安全性、合规性和控制能力共同引入了一些体验。 Skype for Business 提供功能，包括状态、即时消息、语音和视频呼叫和联机会议。 Skype for Business 提供了新的客户端体验、新的服务器版本以及 Microsoft 365 或 Office 365 中的服务更新。 如果贵组织中的用户已经熟悉 Skype，他们将享受 Skype for business 的强大功能和简洁性，以便轻松找到并与同事进行连接。 如果组织中的用户来自 Lync 的 Skype for business，他们将识别他们已使用的所有功能，但在具有简化控件和新添加功能的全新新界面中。 除了新的客户端体验之外，Skype for business Server 2015 还提供了几种新功能来提高本地服务器和混合解决方案的可管理性。
  
Skype for Business Server 2015 中的新功能包括以下方面的改进：
  
- 用户体验  
- 语音和视频支持
- 支持的移动应用程序
- 本地服务器的管理
- 混合解决方案的部署和管理
- 多因素身份验证支持
    
## <a name="user-experience"></a>用户体验

Skype for Business 客户端看起来与 Skype 的使用者版本非常相似，并使用相同的按钮和图标。 较少的菜单和更简单的任务层次结构使用户能够轻松地快速找到所需的控件和命令。 
  
Skype for Business 包括上面所述的新用户体验，以及之前发布的 Lync 2013 用户体验。 同时包含这两种体验，企业可以通过控制新客户端的过程和时间来管理其用户的更改。默认用户体验取决于所使用的服务器版本。 管理员通过将**set-csclientpolicy** Cmdlet 与 EnableSkypeUI 参数一起使用，选择首选体验。 有关配置客户端体验的详细信息，请参阅[Configure the client experience With skype For business](deploy/deploy-clients/configure-the-client-experience.md)和[桌面客户端功能比较（针对 skype for business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)）。
  
> [!NOTE]
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保其不以数字16开头;例如： x.x.x。 
  
## <a name="voice-and-video-improvements"></a>语音和视频改进

Skype for Business Server 2015 包括对语音和视频功能的改进，包括呼叫数据收集和分析，以及改进与第三方视频电话会议系统的互操作性。
  
### <a name="call-data-collection-and-analysis"></a>调用数据收集和分析

"评价我的呼叫" 功能允许 Skype for Business Server 2015 管理员收集呼叫数据。 此功能仅适用于本地部署。 在完成呼叫后，系统会提示用户进行调查。 有关详细信息，请参阅[在 Skype for Business Server 2015 中对我的呼叫评级](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>改进了与第三方视频电话会议系统的互操作性

视频互操作服务器（VIS）充当 Skype for Business Server 和 Cisco Video 电话会议（VTC）系统之间的媒介。 加入会议时，用户现在可以选择 Cisco VTC 系统。 视频互操作服务器（VIS）实现为本地部署的独立服务器角色。 有关详细信息，请参阅[Plan For Video Interop server In Skype For Business Server 2015](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>通过工作进行呼叫

"通过工作进行呼叫" 功能允许企业用户拨打来自 Skype for Business 客户端的语音呼叫。 当用户发出语音呼叫时，会将其从 Skype for Business 路由到发起人的 PBX 或 PSTN 手机。 发起人应答电话后，呼叫将被定向到目标号码。 呼叫收件人应答，并建立与 "控制面板" 的 Skype for Business 服务的呼叫。 发起人可以从 Skype for Business 管理其状态和呼叫控制。 服务器管理员可通过企业的工作来启用和配置呼叫。 有关详细信息，请参阅[Plan For Call Via Work In Skype For Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 
  
## <a name="mobile-device-support-improvements"></a>移动设备支持改进

对移动设备支持的改进包括改进适用于企业版用户的移动体验的功能，例如访问对话历史记录和日志数据、增强的移动会议体验，以及跨 Office 的单一登录支持。 此外，还对 Android 支持、性能改进和功能进行了改进，以简化通过常见应用框架的集成。 
  
> [!NOTE]
> Lync 2013 UCWA 服务器必须升级到 Skype for Business Server 2015，以支持移动客户端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>服务器端对话历史记录现已在移动设备上可用

若要启用对对话历史记录、错过的 IM 和呼叫日志数据的移动访问，现在可以通过服务器为所有移动客户端处理此信息的存档。 IM 的自动接受功能可在移动用户未立即响应即时消息时阻止服务器超时消息，从而提高可靠性。 若要利用基于服务器的 Exchange/Outlook 文件夹集成，需要使用 Exchange Server 2013 或更高版本，并更新了移动客户端。 
  
### <a name="enhanced-meeting-experiences"></a>增强的会议体验

桌面上提供的会议功能现在也适用于移动用户。 新功能包括：
  
- 共享 PowerPoint 内容的异步导航
- 演示者控制共享 PowerPoint 内容的能力
- 演示者的前厅浏览管理，允许他们承认或拒绝参与者
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for business on Android 改进功能

Android 上的 skype for Business 现在提供了类似于 iOS 上的 Skype for business 和 Windows 上的 Skype for business 中可用功能的功能：
  
- 继续或重新加入对话
- 启用证书和被动身份验证
- 邀请其他人加入对话
- 轻松启动组对话
- 加入会议，而不是 Skype for Business 用户
- 在 Android 平板电脑上启用智能手机 UI
- 通过添加或删除参与者来管理会议
    
> [!NOTE]
> 这些功能需要 Android OS 版本4.0 或更高版本。 
  
## <a name="management-of-on-premises-servers"></a>本地服务器的管理

Skype for Business Server 2015 提供了几个新功能来提高本地服务器的可管理性，包括就地升级、智能安装、改进的修补程序和升级过程、改进的前端池冷启动功能、SQL Server AlwaysOn 支持以及集中日志记录和故障排除。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>本地服务器的就地升级

现在，您可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for business Server 2015，该功能使用现有的 Lync Server 2013 硬件和服务器投资，从而降低了部署 Skype for Business Server 2015 的总成本。
  
就地升级有两个方案： Move User 方法（无需停机）和脱机方法（需要停机时间）。 有关哪种升级过程适合您的企业的详细信息，请参阅[Plan to upgrade To Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 如果要从 Lync Server 2010 升级，则 "就地" 选项不可用。 有关从 Lync Server 2010 升级的详细信息，请参阅[Plan to upgrade To Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智能设置

自动检测和下载更新的智能安装功能现在是安装程序的一部分。 在安装过程中，系统会询问用户安装过程是否应检查更新。 有关详细信息，请参阅[Install Skype For Business Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改进了前端服务器修补和升级过程

Skype for Business Server 引入了两个新的 cmdlet，以帮助升级或修补前端服务器，而不是在以前版本的 Lync Server 中执行更多的工作。
  
如果需要在前端服务器上应用修补程序或执行任何其他维护，只需键入**CsComputerFailOver**并指定该服务器的名称即可。 Skype for Business Server 将该服务器的工作负载临时移动到池中的其他服务器。 然后，您可以执行维护，然后使用**CsComputerFailback** cmdlet 将该服务器重新投入使用。 如果需要修补池中的每台服务器，只需对每个服务器（一次一个）执行此过程。 利用这些新的 cmdlet，您可以在以前的版本中更快地修补服务器，并具有更高的可靠性和更简单的工作流。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改进了前端池冷启动功能

Skype for Business Server 引入了一个新的 cmdlet，可简化和提高冷启动整个前端池的过程。 使用新的**start-cspool** cmdlet 时，它会检查池中所有前端服务器的先决条件，然后尝试启动每台服务器。 如果遇到任何问题，则会对其进行诊断并使用详细信息和解决方法提醒你。 在某些情况下，即使某些单个服务器无法启动，也可以启动池。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>对本地服务器的 SQL Server AlwaysOn 支持

Skype for Business Server 2015 添加了对 SQL Server AlwaysOn 可用性组和 SQL Server AlwaysOn 故障转移群集实例的支持。 除了这些功能之外，Skype for Business Server 仍将继续支持数据库镜像和 SQL Server 群集，就像在以前版本的 Lync Server 中一样。
  
SQL Server AlwaysOn 可用性组是 SQL Server 2012 和 SQL Server 2014 中的高可用性和灾难恢复解决方案，可提供数据库镜像的替代方法。 可用性组为故障转移的一组离散数据库（称为可用性数据库）支持故障转移环境。 可用性组支持一组读写主数据库和一到四个对应的辅助数据库集。 （可选）辅助数据库可供进行只读访问，也可用于某些备份操作。
  
SQL Server 故障转移群集实例利用 Windows Server 故障转移群集（WSFC）功能，通过服务器实例级别的冗余（故障转移群集实例（FCI））提供本地高可用性。 FCI 是跨 Windows Server 故障转移群集（WSFC）节点安装的单个 SQL Server 实例，也可能跨多个子网安装。
  
有关详细信息，请参阅[在 Skype For Business Server 2015 中规划高可用性和灾难恢复](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>对本地服务器的集中日志记录和疑难解答改进

集中日志记录服务是 Skype for business Server 2015 的首选日志记录环境。 此版本没有新的功能，但同时改进了服务和集中日志记录服务代理（ClsAgent）的可靠性和性能，服务可执行文件与控制器通信并接收管理员发出的命令。
  
Skype for Business Server 2015 使用 Windows PowerShell cmdlet 管理日志记录服务代理、启动跟踪并生成报告。 （Lync Server 2013 使用 ClsController 执行这些任务。）
  
集中日志记录服务可在任何 Skype for Business Server 2015 上运行。 内置方案（预定义跟踪）保持不变，这也是创建自定义方案的能力。 有一种称为 AlwaysOn 的特殊方案，它始终处于运行状态，并允许管理员在近实时的时间内找到常见问题。
  
Snooper.exe 调试工具也进行了更新，以允许调试移动性日志，并将与连接到 Lync 2013 或 Skype for business Server 2015 的设备一起使用。 此工具可从[调试工具](https://go.microsoft.com/fwlink/?LinkId=285257)下载为 Web。
  
## <a name="hybrid-deployment-and-management"></a>混合部署和管理

Skype for Business Server 2015 通过引入以下功能来实现混合部署管理和管理功能：
  
- 基于客户本地资产的状态的混合部署的建议，由 OnRamp for Office 365 自动协助工具决定。
- Skype for business Server 控制面板和 Skype for Business Server 管理中心的增强功能，以便管理员可以使用这些工具管理混合部署。
- 使用 "混合配置" 向导，可让管理员登录 Microsoft 365 或 Office 365 租户并设置与 Skype for Business Online 的混合功能的控制面板增强功能。
- 支持将本地用户移动到 Skype for Business Online 或将 Skype for Business Online 用户移动回本地的控制面板。
- "控制面板" 功能，用于标识和筛选已移动到 Skype for business Online （即混合用户）的本地用户的本地用户对象。
- 管理中心功能，用于标识和筛选最初在 Skype for Business Online 中从本地迁移到联机的混合用户创建的云用户。
- 能够使用控制面板管理混合用户，以实现从本地管理的属性，以及可从 Skype for Business Online 管理的属性的管理员中心。
- 将密码同步与 DirSync 结合使用，能够将本地 Active Directory 密码与联机租户同步。 如果配置了此功能，则无需为联合身份验证部署 AD FS，但多因素身份验证仍需要 AD FS。 
- 继续支持 Skype for Business Online 与本地 Exchange 之间的共存。
    
> [!NOTE]
> Lync Online 2013 与 Exchange 本地共存和支持体验之间没有任何变化。 
  
## <a name="multi-factor-authentication"></a>多重身份验证

多重身份验证是一种身份验证方法，它需要使用多种验证方法，并向用户登录和事务添加一个严重的第二层安全。 例如，需要用户名和密码以及证书。 Skype for Business Server 2015 仍在 Lync Server 2013 累积更新中提供的多因素身份验证功能上构建。 多重身份验证中的重大变化包括：
  
- 使用 Office 2013 SP1 Active Directory 身份验证库与 Exchange 和 SharePoint 集成
- 支持 Skype for Business Web 应用客户端中的多因素身份验证功能
    
通过 Skype for Business 多重身份验证，现在可以根据地理位置提供不同的身份验证选项。 例如，客户可以配置其环境，以便内部身份验证依赖于集成的 Windows 身份验证，而从组织外部进行身份验证的员工使用多重身份验证。 
  
Skype for Business 多因素身份验证体验无缝，无论：
  
- 地理位置-用户是否正在从组织内部或外部登录 
- 客户端/设备类型-使用的是哪种 Skype for Business 客户端，以及运行客户端的设备（PC、mobile、iPad 等）
- 帐户位置-用户是否托管在本地 Active Directory 或 Azure Active Directory Online 中。
