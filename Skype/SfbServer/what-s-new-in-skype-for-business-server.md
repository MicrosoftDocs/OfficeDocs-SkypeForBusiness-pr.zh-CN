---
title: Skype for Business Server 2015 中的新增功能
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 摘要： 阅读本主题可了解业务服务器 2015 Skype 中的新功能。 有关新的客户端体验的详细信息，请参阅 Lync 现在是 Skype 的业务--请参见新增功能。
ms.openlocfilehash: 0d8172e5031f8b2e51373051b2674e99f5539b6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的新增功能

**摘要：**阅读本主题可了解业务服务器 2015 Skype 中的新功能。 新的客户端体验的详细信息，请参阅[Lync 是现在 Skype 的业务--请参见新增功能](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync 现 Skype 业务、 通信和协作平台与企业级安全性、 法规遵从性和控制 Lync 一起体验 Skype 的灵感来源。 Skype 为企业提供包括状态、 即时消息、 语音和视频呼叫和联机会议的功能。 Skype 为业务提供了新的客户端体验、 新的服务器版本，并更新 Office 365 中的服务。 如果您的组织中的用户已经熟悉 Skype，它们将非常庆幸的强大威力和简洁性的业务很容易查找并与同事交流的 Skype。 如果您的组织中的用户到 Skype 的业务来自于 Lync，它们将识别所有已经使用但在全新新界面与简化控件和新增加的功能。 新的客户端体验，除了业务服务器 2015年的 Skype 提供了几种新功能，以提高内部部署服务器和混合解决方案的可管理性。
  
在业务服务器 2015年的 Skype 的新功能包括改进：
  
- 用户体验  
- 语音和视频支持
- 移动支持
- 内部服务器管理
- 混合解决方案部署与管理
- 多因素身份验证支持
    
## <a name="user-experience"></a>用户体验

Skype 业务客户机看起来非常类似于 Skype 的消费者版本，并使用相同的按钮和图标。 更精简的菜单和扁平化的任务层次结构让用户可以迅速找到所需控件和命令。 
  
Skype 的业务包括上文所述新的用户体验和以前发布的 Lync 2013 用户体验。 这两种经验包括允许企业管理控制流程和新客户机推出的时间为他们的用户更改。默认用户体验取决于您正在使用哪个版本的服务器。 管理员通过使用 **Set-CsClientPolicy** cmdlet 和 EnableSkypeUI 参数来选择首选体验。 有关配置客户端体验的详细信息，请参阅[客户端使用 Skype 业务时遇到的配置](deploy/deploy-clients/configure-the-client-experience.md)和[业务的 Skype 的桌面客户端功能比较](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)。
  
> [!NOTE]
> Lync 2013 客户端体验不是 Skype 业务 2016年的客户端版本的选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。 
  
## <a name="voice-and-video-improvements"></a>语音和视频改进

Skype 的业务服务器 2015年包括语音和视频功能，包括调用数据收集和分析，以及改进互操作性与第三方视频电话会议系统的改进。
  
### <a name="call-data-collection-and-analysis"></a>呼叫数据收集与分析

速度我调用功能，Skype 业务服务器 2015年管理员收集调用数据。 这项功能仅适用于内部部署。 在呼叫完成后，系统将提示用户参与调查。 有关详细信息，请参阅[速率业务服务器 2015年的 Skype 在我调用](manage/health-and-monitoring/rate-my-call.md)。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>与第三方视频电话会议系统的更好互操作性

视频互操作服务器 (VIS) 作为业务服务器和 Cisco 视频电话会议 (VTC) 系统的 Skype 之间的媒介。 加入会议时，用户现可选择 Cisco VTC 系统。 视频互操作服务器 (VIS) 作为内部部署的独立服务器角色实施。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 视频互操作服务器](plan-your-deployment/video-interop-server.md)。
  
### <a name="call-via-work"></a>通过工号拨号

通过工作功能调用允许企业用户进行语音呼叫从业务客户端的 Skype。 当用户发出的语音呼叫时，将送交从 Skype 业务的发起方 PBX 或 PSTN 电话。 在发起方应答电话时，呼叫随后将转到目标号码。 为企业充当控制面板的 Skype 建立调用收件人回答，然后调用。 发起人可以管理它们的存在和业务从 Skype 调用控件。 服务器管理员可为企业启用和配置通过工号拨号功能。 有关详细信息，请参见[调用通过工作在 Skype 的业务服务器 2015年计划](plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 
  
## <a name="mobile-device-support-improvements"></a>移动设备支持改进

对移动设备支持的改进包括功能可改进 Office 企业版的用户，如访问会话历史记录和日志数据、 增强移动会议的经验，以及单一登录支持的移动体验。 此外，还有对 Android 支持改进、 性能改进以及简化通过通用的应用程序框架集成的功能。 
  
> [!NOTE]
> Lync 2013 UCWA 服务器必须升级到 Skype 的业务服务器 2015 以支持移动客户端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>服务器端对话历史记录现已可在移动设备上使用。

若要启用移动访问对话历史记录、 错过的 IM 和呼叫日志数据，此信息的归档现在处理通过服务器对所有移动客户端。 IM 自动接收功能可在移动用户未能立即回复 IM 时防止服务器超时消息，从而提高可靠性。 利用基于服务器交换/Outlook 文件夹集成，Exchange Server 2013年或更高版本，并更新的移动客户端是必需的。 
  
### <a name="enhanced-meeting-experiences"></a>增强的会议体验

移动用户现在同样可以使用桌面版会议功能。 新功能包括：
  
- 共享 PowerPoint 内容的异步导航
- 演示者的能力来控制共享 PowerPoint 内容
- 演讲者的会议厅管理，允许其允许或禁止参与者加入会议
    
### <a name="skype-for-business-on-android-improvements"></a>Skype 的业务对 Android 的改进

为企业在 Android 上的 Skype 现在提供类似于 iOS 和业务在 Windows 上的 Skype 业务的 Skype 上可用的功能：
  
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

商业服务器 2015年的 Skype 提供了几种新功能，以提高可管理性的内部服务器，其中包括就地升级，智能安装、 改进修补程序和升级流程，提高了的前端池冷启动功能，SQL Server AlwaysOn支持和集中式日志记录和故障排除。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>内部服务器的就地升级

您下现在可以升级 Lync Server 2013 系统到 Skype 的业务服务器 2015 使用新的就地升级功能，它使用现有的 Lync Server 2013 硬件和服务器的投资，从而减少了业务服务器 2015年部署 Skype 的总体成本。
  
就地升级有两种情景：无需停机的移动用户方法和需要停机的脱机方法。 升级过程是最适合您的业务有关的详细信息，请参阅[计划升级到业务服务器 2015年的 Skype](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 就地选项不可用如果您要升级 Lync Server 2010 中。 有关升级 Lync Server 2010 中的详细信息，请参阅[计划升级到业务服务器 2015年的 Skype](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智能设置

能够自动检测和下载更新的智能设置功能现已纳入安装程序。 在安装过程中，应该检查更新安装过程要求用户。 有关详细信息，请参阅[有关业务服务器 2015年安装 Skype](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改进的前端服务器修补和升级过程

Skype 业务服务器引入了两个新的 cmdlet，帮助进行升级或修补前端服务器 Lync Server 的早期版本中更为简单。
  
当您需要应用修补程序，或执行其他维护，到前端服务器，只需键入**调用 CsComputerFailOver**并指定该服务器的名称。 Skype 业务服务器到池中的其他服务器暂时移动该服务器的工作负荷。 随后即可后自行维护，然后使用 **Invoke-CsComputerFailback** cmdlet 将该服务器重新投入服务。 如果需要修补池中的每一台服务器，只需依次为每台服务器执行此过程。 这些新 cmdlet 支持比旧版本更快地修补服务器，并且提供了更加可靠、简单的工作流。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改进的前端池冷启动功能

Skype 业务服务器引入了新的 cmdlet，可以简化和改进了冷启动整个前端池的过程。 使用新增的 **Start-CsPool** cmdlet 时，它会检查池中所有前端服务器的先决条件，随后尝试启动各服务器。 如果遇到任何问题，则将执行诊断并通过警告通知您详细信息和解决方法。 在某些情况下，它还允许您启动池 - 即便部分服务器无法启动。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>内部服务器的 SQL Server AlwaysOn 支持

Skype 的业务服务器 2015年添加 SQL Server AlwaysOn 可用性组和 SQL Server AlwaysOn 故障转移群集实例的支持。 除了这些功能，Skype 业务服务器将继续支持数据库镜像和群集 SQL Server，Lync Server 的早期版本。
  
SQL Server AlwaysOn 可用性组是高可用性和灾难恢复解决方案，在 SQL Server 2012年和 SQL Server 2014 提供数据库镜像的一种替代方法。 可用性组为一组同时发生故障的不同数据库（称为可用性数据库）提供了故障转移环境。 可用性组支持一组读-写主数据库和一到四组对应辅助数据库。 可以选择将辅助数据库设为只读访问，用于某些备份操作。
  
SQL Server 故障转移群集实例利用 Windows 服务器故障转移群集 (WSFC) 功能，可提供本地高可用性通过冗余服务器实例级的 — — 一个故障转移群集实例 (FCI)。 FCI 是安装在 Windows 服务器故障转移群集 (WSFC) 节点以及可能的多子网间的 SQL Server 的单个实例。
  
有关详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>内部服务器的集中日志和故障排除改进

集中式日志记录服务是业务服务器 2015年的 Skype 的首选的日志记录环境。 此版本并未增加新功能，但这项服务和集中日志服务代理 (ClsAgent.exe)（与控制器通信，接收管理员发出的命令的服务可执行文件）的可靠性和性能均有所改进。
  
业务服务器 2015年的 Skype 使用 Windows PowerShell cmdlet 以管理日志记录服务代理、 启动跟踪，并生成报告。 （Lync Server 2013 使用 ClsController.exe 来执行这些任务）。
  
集中式日志记录服务可以运行任何 Skype 业务服务器 2015年。 内置情景（预定义跟踪）仍然相同，创建自定义情景的能力也完全相同。 但有一种称为 AlwaysOn 的特殊情景，它将始终运行，允许管理员以接近实时的方式找到常见问题。
  
窥探调试工具也已更新为允许调试的移动日志，并将设备连接到 Lync 2013 或 Skype 业务服务器 2015年的一起工作。 该工具可[调试工具](https://go.microsoft.com/fwlink/?LinkId=285257)从网站下载。
  
## <a name="hybrid-deployment-and-management"></a>混合部署与管理

Skype 的业务服务器 2015年使混合部署管理和管理功能通过引入了以下功能：
  
- 基于状态的客户的内部资产，由 O365 自动的协助工具 OnRamp 的混合部署的建议。
- Skype 业务服务器的控制面板和服务器管理员商业中心的 Skype 的增强功能，以便管理员可以使用这些工具来管理混合部署。
- 控件面板的增强功能，让管理员登录到 O365 租户和为业务联机使用混合配置向导设置与 Skype 的混合。
- 控制转向内部用户 Skype 的在线业务或转向使用 Skype 的在线业务用户回内部支持面板。
- 控制内部用户面板来识别和筛选已经移动到 Skype 的在线业务 （即混合用户） 的内部用户对象的功能。
- 管理中心功能可识别并过滤掉云最初创建用户在 Skype 的在线业务从混合用户从内部迁移到联机。
- 管理混合用户使用控制面板的属性可从内部部署和管理中心从 Skype 可管理的属性管理在线业务的能力。
- 通过 DirSync 使用密码同步，可将内部 Active Directory 密码与联机租户同步。如果配置了此项功能，即无需部署 AD FS 以启用联合身份验证，但多因素身份验证仍然需要 AD FS。 
- 继续支持 Skype 的在线业务和 Exchange 部署之间的共存。
    
> [!NOTE]
> 不没有从 Lync 在线 2013年和交换内部共存和支持经验的任何更改。 
  
## <a name="multi-factor-authentication"></a>多因素身份验证

多因素身份验证是一种需要使用多种验证方法的身份验证方式，为用户登录和交易多加了一层安全防御。 例如，需要用户名和密码以及证书。 Skype 的业务服务器 2015年继续依赖 Lync 服务器 2013年累计更新中提供的多因素身份验证功能。 多因素身份验证的主要变化包括：
  
- 使用 Office 2013 SP1 Active Directory 身份验证库集成 Exchange 和 SharePoint
- 在企业 Web 应用程序客户端的 Skype 的多因素身份验证功能的支持
    
与业务多因素身份验证的 Skype，现能提供根据地域的不同的身份验证选项。 例如，用户可以对环境进行配置，使内部身份验证依赖于集成的 Windows 身份验证，而从组织外部访问的员工必需使用多因素身份验证进行验证。 
  
为业务多因素身份验证体验 Skype 是无论紧密相连：
  
- 地理位置 — 无论用户将登录从内部或外部组织 
- 使用客户端/设备类型的业务客户端的 Skype 和哪些设备 (PC，手机、 iPad 等) 上运行客户端
- 是否在内部部署 Active Directory 或在 Azure 活动目录在线 (O365) 承载用户帐户位置 —