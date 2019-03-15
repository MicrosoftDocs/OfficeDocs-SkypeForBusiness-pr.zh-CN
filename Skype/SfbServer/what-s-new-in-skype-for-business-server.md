---
title: Skype for Business Server 2015 中的新增功能
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 摘要： 阅读此主题以了解业务服务器 2015 Skype 中的新功能。 有关新的客户端体验的详细信息，请参阅 Lync 现 for Business 的 Skype--请参阅 what's new。
ms.openlocfilehash: e1ae2a046b955e83ccc7c811984a526c26f7c526
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "24961027"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的新增功能

**摘要：** 阅读本主题可了解业务服务器 2015 Skype 中的新功能。 有关新的客户端体验的详细信息，请参阅[Lync 是现在 for Business 的 Skype--请参阅 what's new](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync 是现在 Skype 业务、 通信和协作平台，将企业级安全、 合规性以及的 Lync 控件结合在一起的 Skype 灵感来源的体验。 Skype for Business 提供了功能，包括状态、 IM、 语音和视频呼叫和联机会议。 Skype for Business 提供新的客户端体验、 新的服务器版本和更新到 Office 365 中的服务。 如果您的组织中的用户已经熟悉 Skype，他们将对电源和 Skype for Business 其中很容易地查找和联系的同事的简单性。 如果您的组织中的用户到 for Business 的 Skype 来自于 Lync，它们将识别的所有功能已使用但全新新界面中使用简化控件和新增功能。 除了新的客户端体验，业务服务器 2015年的 Skype 提供了几种新功能，以提高可管理性的内部部署服务器和混合解决方案。
  
中的业务服务器 2015 Skype 的新功能包括改进：
  
- 用户体验  
- 语音和视频支持
- 移动支持
- 内部服务器管理
- 混合解决方案部署与管理
- 多因素身份验证支持
    
## <a name="user-experience"></a>用户体验

业务客户端 Skype 非常类似于 Skype 的使用者版本，并使用相同的按钮和图标。 更精简的菜单和扁平化的任务层次结构让用户可以迅速找到所需控件和命令。 
  
Skype for Business 包括上面所述的新用户体验和以前发布的 Lync 2013 用户体验。 包含两个体验允许企业能够通过控制过程和计时的新客户端推出管理他们的用户的更改。默认用户体验取决于您正在使用哪个版本的服务器。 管理员通过使用 **Set-CsClientPolicy** cmdlet 和 EnableSkypeUI 参数来选择首选体验。 有关配置客户端体验的详细信息，请参阅[的配置客户端体验的 Skype for Business](deploy/deploy-clients/configure-the-client-experience.md)和[Skype for Business 的桌面客户端功能比较](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)。
  
> [!NOTE]
> Lync 2013 客户端体验不是业务 2016年客户端版本的 Skype 选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="voice-and-video-improvements"></a>语音和视频改进

Skype 的业务服务器 2015年改善了语音和视频功能，包括呼叫数据收集和分析和改进与第三方远程视频会议系统的互操作性。
  
### <a name="call-data-collection-and-analysis"></a>呼叫数据收集与分析

速率我呼叫功能允许 Skype 业务服务器 2015年管理员收集呼叫数据。 这项功能仅适用于内部部署。 在呼叫完成后，系统将提示用户参与调查。 如需了解详细信息，请参阅 [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>与第三方视频电话会议系统的更好互操作性

视频互操作服务器 (VIS) 作为中介的业务服务器和 Cisco 视频电话会议 (VTC) 系统的 Skype。 加入会议时，用户现可选择 Cisco VTC 系统。 视频互操作服务器 (VIS) 作为内部部署的独立服务器角色实施。 有关详细信息，请参阅[规划视频中的业务服务器 2015 Skype 的互操作服务器](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>通过工号拨号

单位电话呼叫功能允许企业用户进行业务客户端 Skype 从语音呼叫。 当用户发出语音呼叫时，它是从 for Business 的 Skype 路由到原始发件人的 PBX 或 PSTN 电话。 在发起方应答电话时，呼叫随后将转到目标号码。 与业务充当控制面板的 Skype 建立呼叫收件人答复，并调用。 原始发件人可以管理其状态和 for Business 中 Skype 的呼叫控制。 服务器管理员可为企业启用和配置通过工号拨号功能。 有关详细信息，请参阅[规划呼叫通过单位电话的业务服务器 2015 Skype 中](plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 
  
## <a name="mobile-device-support-improvements"></a>移动设备支持改进

为移动设备支持的改进包括要改进 Office Enterprise Edition 用户，例如访问对话历史记录和日志数据、 增强移动会议体验和单一登录支持的移动体验的功能。 此外，有 Android 支持改进，性能改进，以简化常见的应用程序框架通过集成的功能。 
  
> [!NOTE]
> Lync 2013 UCWA 服务器必须升级到业务服务器 2015 以支持移动客户端的 Skype。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>服务器端对话历史记录现已可在移动设备上使用。

若要启用对话历史记录和错过的 IM、 呼叫日志数据移动访问，此信息的存档现在处理通过服务器的所有移动客户端。 IM 自动接收功能可在移动用户未能立即回复 IM 时防止服务器超时消息，从而提高可靠性。 若要利用基于服务器的 Exchange/Outlook 文件夹集成，Exchange Server 2013 或更高版本，和更新的移动客户端是必需的。 
  
### <a name="enhanced-meeting-experiences"></a>增强的会议体验

移动用户现在同样可以使用桌面版会议功能。 新功能包括：
  
- 共享 PowerPoint 内容的异步导航
- 演示者能够控制共享 PowerPoint 内容
- 演讲者的会议厅管理，允许其允许或禁止参与者加入会议
    
### <a name="skype-for-business-on-android-improvements"></a>在 Android 改进业务的 Skype

在 Android 业务的 Skype 现在提供类似于在 iOS 和 Windows 上的业务的 Skype for Business 的 Skype 上可用的功能：
  
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

Skype 的业务服务器 2015年提供了几种新功能，以提高可管理性的内部部署服务器，包括就地升级、 智能安装、 改进修补和升级处理，改进的前端池冷启动功能，SQL Server AlwaysOn支持，和集中日志记录和故障排除。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>内部服务器的就地升级

为业务服务器 2015 使用新的就地升级功能，它使用现有的 Lync Server 2013 硬件和服务器投资，从而减少了部署业务服务器 2015 Skype 的总成本中，现在可以将对 Lync Server 2013 系统升级到 Skype。
  
就地升级有两种情景：无需停机的移动用户方法和需要停机的脱机方法。 有关哪种升级过程最适合您的企业的详细信息，请参阅 [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 就地选项不可用，如果您要从 Lync Server 2010 升级。 有关从 Lync Server 2010 升级的详细信息，请参阅[计划升级到业务服务器 2015年的 Skype](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智能设置

能够自动检测和下载更新的智能设置功能现已纳入安装程序。 在安装过程中，则询问用户应检查更新的安装过程。 如需了解详细信息，请参阅 [Install Skype for Business Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改进的前端服务器修补和升级过程

Skype 业务服务器引入了两个帮助确保升级或修补前端服务器会容易得多比早期版本的 Lync Server 中的新 cmdlet。
  
当您需要应用修补程序，或执行任何其他的维护到前端服务器，只需键入**Invoke CsComputerFailOver**并指定该服务器的名称。 Skype 业务服务器到其他服务器池中暂时移动该服务器的工作负荷。 随后即可后自行维护，然后使用 **Invoke-CsComputerFailback** cmdlet 将该服务器重新投入服务。 如果需要修补池中的每一台服务器，只需依次为每台服务器执行此过程。 这些新 cmdlet 支持比旧版本更快地修补服务器，并且提供了更加可靠、简单的工作流。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改进的前端池冷启动功能

Skype 业务服务器引入了新的 cmdlet，可简化并提高冷启动整个前端池的过程。 使用新增的 **Start-CsPool** cmdlet 时，它会检查池中所有前端服务器的先决条件，随后尝试启动各服务器。 如果遇到任何问题，则将执行诊断并通过警告通知您详细信息和解决方法。 在某些情况下，它还允许您启动池 - 即便部分服务器无法启动。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>内部服务器的 SQL Server AlwaysOn 支持

Skype 的业务服务器 2015年添加为 SQL Server AlwaysOn 可用性组和 SQL Server AlwaysOn 故障转移群集实例的支持。 除了这些功能，业务服务器 Skype 仍继续支持数据库镜像和 SQL Server 群集，如以前版本的 Lync Server 中所示。
  
高可用性和灾难恢复解决方案在 SQL Server 2012 和代替数据库镜像的 SQL Server 2014，SQL Server AlwaysOn 可用性组。 可用性组为一组同时发生故障的不同数据库（称为可用性数据库）提供了故障转移环境。 可用性组支持一组读-写主数据库和一到四组对应辅助数据库。 可以选择将辅助数据库设为只读访问，用于某些备份操作。
  
SQL Server 故障转移群集实例利用 Windows Server 故障转移群集 (WSFC) 功能，以提供冗余服务器实例级别通过本地高可用性，故障转移群集实例 (FCI)。 FCI 是安装在 Windows Server 故障转移群集 (WSFC) 节点以及可能的跨多个子网的 SQL Server 的单个实例。
  
有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>内部服务器的集中日志和故障排除改进

The Centralized Logging Service 是业务服务器 2015年的 Skype 的首选的日志记录环境。 此版本并未增加新功能，但这项服务和集中日志服务代理 (ClsAgent.exe)（与控制器通信，接收管理员发出的命令的服务可执行文件）的可靠性和性能均有所改进。
  
Skype 的业务服务器 2015年使用 Windows PowerShell cmdlet 管理的日志记录服务代理，启动跟踪，并生成报告。 （Lync Server 2013 用于 ClsController.exe 执行这些任务。）
  
The Centralized Logging Service 可以在任何 Skype 上运行业务服务器 2015年。 内置情景（预定义跟踪）仍然相同，创建自定义情景的能力也完全相同。 但有一种称为 AlwaysOn 的特殊情景，它将始终运行，允许管理员以接近实时的方式找到常见问题。
  
在 Snooper 调试工具也已更新以允许对移动日志进行调试和将设备连接到 Lync 2013 或 Skype 业务服务器 2015年一起工作。 可用作[调试工具](https://go.microsoft.com/fwlink/?LinkId=285257)从网站下载该工具。
  
## <a name="hybrid-deployment-and-management"></a>混合部署与管理

业务服务器 2015年的 Skype 支持混合部署管理和管理功能，通过引入了以下功能：
  
- 确定适用于 O365 自动化的帮助工具，可根据客户的内部部署资产的状态的混合部署的建议。
- Skype 业务 Server Control Panel 和业务服务器管理中心的 Skype 的增强功能，以便管理员可以使用这些工具来管理混合部署。
- 控制让管理员登录到 O365 租户和业务 online 使用混合配置向导设置与 Skype 的混合的面板增强功能。
- 控制业务 online 将内部部署用户移动到 Skype 或移动的 Skype 的业务 Online 用户返回到内部部署的支持面板。
- 控制从内部部署用户面板功能，用于标识和筛选器已移至 Skype 业务 online （即，混合用户） 的内部部署用户对象。
- Admin Center 功能，用于标识和筛选器云用户最初中创建 Skype 业务 Online 的混合用户从内部部署迁移到 Online。
- 管理混合用户业务 online 属性可从本地和 Admin Center 属性可从 Skype 管理管理使用控制面板的能力。
- 通过 DirSync 使用密码同步，可将内部 Active Directory 密码与联机租户同步。如果配置了此项功能，即无需部署 AD FS 以启用联合身份验证，但多因素身份验证仍然需要 AD FS。 
- 继续支持 Skype 业务 online 和 Exchange 内部部署之间的共存。
    
> [!NOTE]
> 不没有从 Lync Online 2013 和 Exchange 内部部署共存和支持经验的任何更改。 
  
## <a name="multi-factor-authentication"></a>多因素身份验证

多因素身份验证是一种需要使用多种验证方法的身份验证方式，为用户登录和交易多加了一层安全防御。 例如，需要用户名和密码以及证书。 Skype 的业务服务器 2015年继续在 Lync Server 2013 累积更新中提供的多因素身份验证功能构建。 多因素身份验证的主要变化包括：
  
- 使用 Office 2013 SP1 Active Directory 身份验证库集成 Exchange 和 SharePoint
- Skype 业务 Web App 客户端中的多因素身份验证功能的支持
    
与业务多因素身份验证的 Skype，现可提供基于地理位置的不同的身份验证选项。 例如，用户可以对环境进行配置，使内部身份验证依赖于集成的 Windows 身份验证，而从组织外部访问的员工必需使用多因素身份验证进行验证。 
  
业务多因素身份验证体验 Skype 是无缝无论：
  
- 地理位置-是否用户从登录内部或外部组织 
- 使用客户端/设备类型-的 Skype 业务客户端和设备 (PC，mobile、 iPad 等) 上运行客户端
- 是否在内部部署 Active Directory 中或在 Azure Active Directory Online (O365) 承载用户帐户位置-