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
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的新增功能。 有关新的客户体验的详细信息，请参阅 Lync 现在是 Skype for business--查看新增功能。
ms.openlocfilehash: 0a11c94f7c31b0140a256ab350f5dad6112bc71e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824076"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的新增功能

**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中的新增功能。 有关新的客户体验的详细信息，请参阅[Lync 现在是 Skype for business--查看新增功能](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync 现在是 Skype for Business，它是一种通信和协作平台，通过 Skype 的企业级安全性、合规性和控制功能将 Skype 的体验汇集到了一起。 Skype for Business 提供的功能包括状态、IM、语音和视频呼叫以及联机会议。 Skype for Business 提供了新的客户体验、新的服务器版本以及 Office 365 中服务的更新。 如果您的组织中的用户已经熟悉 Skype，他们将非常欣赏 Skype for business 的强大功能和简洁性，在这里，您可以轻松找到并与同事联系。 如果您的组织中的用户来自 Lync 的 Skype for business，他们将识别他们已使用的所有功能，但在具有简化的控件和新添加的全新界面中。 除了全新的客户体验，Skype for Business Server 2015 提供了一些新功能来提高本地服务器和混合解决方案的可管理性。
  
Skype for Business Server 2015 中的新增功能包括以下内容的改进：
  
- 用户体验  
- 语音和视频支持
- 移动支持
- 内部服务器管理
- 混合解决方案部署与管理
- 多因素身份验证支持
    
## <a name="user-experience"></a>用户体验

Skype for Business 客户端看起来非常类似于 Skype 的消费者版本，并使用相同的按钮和图标。 更精简的菜单和扁平化的任务层次结构让用户可以迅速找到所需控件和命令。 
  
Skype for business 包括上文所述的新用户体验和之前发布的 Lync 2013 用户体验。 通过同时包含这两个体验，企业可以通过控制新客户端的流程和计时来管理其用户的更改。默认的用户体验取决于你使用的是哪个版本的服务器。 管理员通过使用 **Set-CsClientPolicy** cmdlet 和 EnableSkypeUI 参数来选择首选体验。 有关配置客户端体验的详细信息，请参阅为 Skype for business[配置客户端体验 skype for](deploy/deploy-clients/configure-the-client-experience.md) Business 和[桌面客户端功能比较](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)。
  
> [!NOTE]
> Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="voice-and-video-improvements"></a>语音和视频改进

Skype for Business Server 2015 包括对语音和视频功能的改进，包括调用数据收集和分析，以及改进与第三方视频 teleconferencing 系统的互操作性。
  
### <a name="call-data-collection-and-analysis"></a>呼叫数据收集与分析

"通话费率" 功能允许 Skype for business Server 2015 管理员收集呼叫数据。 这项功能仅适用于内部部署。 在呼叫完成后，系统将提示用户参与调查。 如需了解详细信息，请参阅 [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>与第三方视频电话会议系统的更好互操作性

视频互操作服务器（VIS）充当 Skype for Business 服务器和 Cisco 视频 teleconferencing （VTC）系统之间的媒介。 加入会议时，用户现可选择 Cisco VTC 系统。 视频互操作服务器 (VIS) 作为内部部署的独立服务器角色实施。 有关详细信息，请参阅[在 Skype for Business server 2015 中规划视频互操作服务器](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>通过工号拨号

"通过工作电话通话" 功能允许企业用户从 Skype for Business 客户端进行语音呼叫。 当用户拨打电话时，它将从 Skype for Business 路由到始发者的 PBX 或 PSTN 手机。 在发起方应答电话时，呼叫随后将转到目标号码。 呼叫收件人的答案，并建立与 "控制面板" 的 Skype for Business 服务通话。 始发者可以从 Skype for Business 管理其状态和呼叫控制。 服务器管理员可为企业启用和配置通过工号拨号功能。 有关详细信息，请参阅[通过 Skype For Business Server 2015 中的工作计划呼叫](plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 
  
## <a name="mobile-device-support-improvements"></a>移动设备支持改进

对移动设备支持的改进包括改善适用于企业版用户的移动体验的功能，例如访问对话历史记录和日志数据、增强的移动会议体验，以及跨 Office 的单一登录支持。 此外，对 Android 支持、性能改进和功能进行了改进，以简化通过通用应用框架的集成。 
  
> [!NOTE]
> Lync 2013 UCWA 服务器必须升级到 Skype for Business Server 2015，才能支持移动客户端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>服务器端对话历史记录现已可在移动设备上使用。

若要启用对对话历史记录、错过的 IM 以及呼叫日志数据的移动访问，现在可通过服务器为所有移动客户端处理此信息的存档。 IM 自动接收功能可在移动用户未能立即回复 IM 时防止服务器超时消息，从而提高可靠性。 若要利用基于服务器的 Exchange/Outlook 文件夹集成，需要使用 Exchange Server 2013 或更高版本，以及更新的移动客户端。 
  
### <a name="enhanced-meeting-experiences"></a>增强的会议体验

移动用户现在同样可以使用桌面版会议功能。 新功能包括：
  
- 共享 PowerPoint 内容的异步导航
- 演示者获取共享 PowerPoint 内容的控制权的能力
- 演讲者的会议厅管理，允许其允许或禁止参与者加入会议
    
### <a name="skype-for-business-on-android-improvements"></a>Android 版 Skype for Business 改进

Android 版 skype for business 现在提供的功能类似于 iOS 版 Skype for business 和 Windows 版 Skype for business 中的可用功能：
  
- 继续或重新加入对话
- 支持证书和被动式身份验证
- 邀请他人加入对话
- 轻松开始组对话
- 支持非 Skype for Business 用户加入会议
- 在 Android 平板电脑上支持智能手机 UI
- 通过添加或删除与会者管理会议
    
> [!NOTE]
> 这些功能需要 Android OS 4.0 或更高版本。 
  
## <a name="management-of-on-premises-servers"></a>内部服务器管理

Skype for Business Server 2015 提供了多种新功能来提高本地服务器的可管理性，包括就地升级、智能设置、改进的修补程序和升级过程、改进的前端池冷启动功能、SQL Server AlwaysOn支持以及集中式日志记录和疑难解答。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>内部服务器的就地升级

现在2013，你可以使用全新的就地升级功能将 Lync Server 2013 系统升级到 Skype for Business Server 2015，从而降低部署 Skype for Business Server 2015 的总成本。
  
就地升级有两种情景：无需停机的移动用户方法和需要停机的脱机方法。 有关哪种升级过程最适合您的企业的详细信息，请参阅 [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 如果从 Lync Server 2010 升级，则就地选项不可用。 有关从 Lync Server 2010 升级的详细信息，请参阅[计划升级到 Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智能设置

能够自动检测和下载更新的智能设置功能现已纳入安装程序。 在安装过程中，系统会询问用户安装过程是否应检查更新。 如需了解详细信息，请参阅 [Install Skype for Business Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改进的前端服务器修补和升级过程

Skype for Business 服务器引入了两个新的 cmdlet，可帮助升级或修补前端服务器，比在早期版本的 Lync Server 中更轻松。
  
如果需要将修补程序或执行任何其他维护应用于前端服务器，只需键入**CsComputerFailOver** ，然后指定该服务器的名称。 Skype for business 服务器将该服务器的工作负荷临时移动到池中的其他服务器。 随后即可后自行维护，然后使用 **Invoke-CsComputerFailback** cmdlet 将该服务器重新投入服务。 如果需要修补池中的每一台服务器，只需依次为每台服务器执行此过程。 这些新 cmdlet 支持比旧版本更快地修补服务器，并且提供了更加可靠、简单的工作流。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改进的前端池冷启动功能

Skype for Business 服务器引入了一个新 cmdlet，可简化和改进从一个完整的前端池的冷启动过程。 使用新增的 **Start-CsPool** cmdlet 时，它会检查池中所有前端服务器的先决条件，随后尝试启动各服务器。 如果遇到任何问题，则将执行诊断并通过警告通知您详细信息和解决方法。 在某些情况下，它还允许您启动池 - 即便部分服务器无法启动。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>内部服务器的 SQL Server AlwaysOn 支持

Skype for Business Server 2015 添加了对 SQL Server AlwaysOn 可用性组和 SQL Server AlwaysOn 故障转移群集实例的支持。 除了这些功能，Skype for Business 服务器还会继续支持数据库镜像和 SQL Server 群集，就像在以前版本的 Lync Server 中一样。
  
SQL Server AlwaysOn 可用性组是 SQL Server 2012 和 SQL Server 2014 中的高可用性和灾难恢复解决方案，可替代数据库镜像。 可用性组为一组同时发生故障的不同数据库（称为可用性数据库）提供了故障转移环境。 可用性组支持一组读-写主数据库和一到四组对应辅助数据库。 可以选择将辅助数据库设为只读访问，用于某些备份操作。
  
SQL Server 故障转移群集实例利用 Windows Server 故障转移群集（WSFC）功能通过服务器实例级别的冗余（故障转移群集实例（FCI））提供本地高可用性。 FCI 是跨 Windows Server 故障转移群集（WSFC）节点安装的单个 SQL Server 实例，并且可能跨多个子网进行安装。
  
有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>内部服务器的集中日志和故障排除改进

集中式日志记录服务是 Skype for business Server 2015 的首选日志记录环境。 此版本并未增加新功能，但这项服务和集中日志服务代理 (ClsAgent.exe)（与控制器通信，接收管理员发出的命令的服务可执行文件）的可靠性和性能均有所改进。
  
Skype for Business Server 2015 使用 Windows PowerShell cmdlet 管理日志记录服务代理、启动跟踪和生成报告。 （Lync Server 2013 使用 ClsController 执行这些任务。）
  
集中式日志记录服务可以在任何 Skype for Business 服务器2015上运行。 内置情景（预定义跟踪）仍然相同，创建自定义情景的能力也完全相同。 但有一种称为 AlwaysOn 的特殊情景，它将始终运行，允许管理员以接近实时的方式找到常见问题。
  
Snooper 调试工具也已更新为允许调试移动性日志，并且将与连接到 Lync 2013 或 Skype for business Server 2015 的设备协同工作。 该工具可从[调试工具](https://go.microsoft.com/fwlink/?LinkId=285257)下载到 Web。
  
## <a name="hybrid-deployment-and-management"></a>混合部署与管理

Skype for Business Server 2015 通过引入以下功能来实现混合部署管理功能：
  
- 基于客户本地资源状态的混合部署的建议，由 OnRamp for O365 自动协助工具确定。
- 对 Skype for Business 服务器控制面板和 Skype for business 服务器管理中心的增强功能，以便管理员可以使用这些工具管理混合部署。
- 控制面板增强功能，允许管理员使用混合配置向导登录到 O365 租户并使用 Skype for Business Online 设置混合。
- 支持将本地用户移动到 Skype for business Online 或将 Skype for business Online 用户移回本地的控制面板支持。
- "控制面板" 功能，可标识和筛选已移动到本地用户的 Skype for business Online （即混合用户）的本地用户对象。
- 管理中心功能，用于识别和筛选最初在从本地从本地迁移到联机的 Skype for business Online 中创建的云用户。
- 使用控制面板管理混合用户的功能，可从本地和 Skype for business Online 中管理属性。
- 通过 DirSync 使用密码同步，可将内部 Active Directory 密码与联机租户同步。如果配置了此项功能，即无需部署 AD FS 以启用联合身份验证，但多因素身份验证仍然需要 AD FS。 
- 继续支持 Skype for Business Online 和本地 Exchange 之间的共存。
    
> [!NOTE]
> Lync Online 2013 和 Exchange 本地共存和支持体验没有任何更改。 
  
## <a name="multi-factor-authentication"></a>多因素身份验证

多因素身份验证是一种需要使用多种验证方法的身份验证方式，为用户登录和交易多加了一层安全防御。 例如，需要用户名和密码以及证书。 Skype for Business Server 2015 将继续基于 Lync Server 2013 累积更新中提供的多因素身份验证功能。 多因素身份验证的主要变化包括：
  
- 使用 Office 2013 SP1 Active Directory 身份验证库集成 Exchange 和 SharePoint
- Skype for Business Web 应用客户端中的多因素身份验证功能的支持
    
通过 Skype for Business 多因素身份验证，现在可以提供基于地理位置的不同身份验证选项。 例如，用户可以对环境进行配置，使内部身份验证依赖于集成的 Windows 身份验证，而从组织外部访问的员工必需使用多因素身份验证进行验证。 
  
Skype for Business 多因素身份验证体验是无缝的，无论：
  
- 地理位置-用户是否从组织内部或外部登录 
- 客户端/设备类型-使用的 Skype for business 客户端和客户端运行的设备（电脑、手机、iPad 等）
- 帐户位置-用户是否托管在本地 Active Directory 或 Azure Active Directory Online （O365）中
