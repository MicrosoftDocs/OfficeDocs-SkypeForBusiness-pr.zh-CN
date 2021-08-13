---
title: 2015 年 Skype for Business Server 的新增功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的新功能。 有关新客户端体验的详细信息，请参阅 Lync is now Skype for Business -- see what's new.
ms.openlocfilehash: e32b55c6eb41a5800f4bceb1e213a44efed5d2292ccd57766dbf56c1c0cd6e4b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344511"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>2015 年 Skype for Business Server 的新增功能

**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中的新功能。 有关新客户端体验的详细信息，请参阅 Lync [is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync 现已Skype for Business，它是一个通信和协作平台，它提供由 Skype 启发的体验以及 Lync 的企业级安全性、合规性和控制。 Skype for Business提供状态、IM、语音和视频呼叫以及联机会议等功能。 Skype for Business提供了新的客户端体验、新的服务器版本以及 Microsoft 365 或 Office 365 中的服务更新。 如果贵组织的用户已经熟悉Skype，那么他们将会非常体验 Skype for Business 在轻松查找同事并联系同事时，Skype for Business这种功能和简单性。 如果贵组织的用户即将从 Lync Skype for Business，他们将识别他们已使用的所有功能，但会在全新的界面中识别简化的控件和新增功能。 除了新的客户端体验之外，Skype for Business Server 2015 还提供了一些新功能，以提高本地服务器和混合解决方案的可管理性。
  
2015 年 Skype for Business Server 中的新功能包括以下改进：
  
- 用户体验  
- 语音和视频支持
- 支持的移动应用程序
- 管理内部部署服务器
- 混合解决方案的部署和管理
- 多重身份验证支持
    
## <a name="user-experience"></a>用户体验

客户端Skype for Business客户端外观与客户端的使用者版本Skype使用相同的按钮和图标。 更少的菜单和扁平的任务层次结构使用户能够轻松快速找到所需的控件和命令。 
  
Skype for Business包括上述新用户体验以及之前发布的 Lync 2013 用户体验。 通过包含这两种体验，企业可以控制新客户端推出的过程和时间，来管理用户的更改。默认用户体验取决于您使用的服务器的哪个版本。 管理员使用 **Set-CsClientPolicy** cmdlet 和 EnableSkypeUI 参数选择首选体验。 有关配置客户端体验的信息，[请参阅使用](deploy/deploy-clients/configure-the-client-experience.md)Skype for Business 配置客户端体验和桌面客户端[功能比较Skype for Business。](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> Lync 2013 客户端体验不是适用于 Skype for Business 2016 客户端版本的选项。 在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保它不会以数字 16 开始;例如：16.x.x.x。 
  
## <a name="voice-and-video-improvements"></a>语音和视频改进

Skype for Business Server 2015 包括语音和视频功能的改进，包括呼叫数据收集和分析，以及改进的第三方视频电话会议系统的互操作性。
  
### <a name="call-data-collection-and-analysis"></a>呼叫数据收集和分析

"评价我的呼叫"功能Skype for Business Server 2015 管理员收集呼叫数据。 此功能仅适用于本地部署。 在完成呼叫后，将提示用户参加调查。 有关详细信息，请参阅[Rate my Call in Skype for Business Server 2015。](manage/health-and-monitoring/rate-my-call.md)
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>改进了第三方视频电话会议系统的互操作性

视频互操作服务器 (VIS) 充当 Skype for Business Server 和 (Cisco 视频电话会议与 VTC) 系统之间的中介。 加入会议时，用户现在可以选择 Cisco VTC 系统。 视频互操作服务器 (VIS) 作为本地部署的独立服务器角色实现。 有关详细信息，请参阅[Plan for Video Interop Server in Skype for Business Server 2015。](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>通过工作电话呼叫

单位电话呼叫功能允许企业用户从 Skype for Business 客户端进行语音呼叫。 当用户发出语音呼叫时，该呼叫Skype for Business到发起方 PBX 或 PSTN 电话。 一旦发起方接听电话，呼叫将定向到目标号码。 呼叫接收者应答，呼叫建立时Skype for Business控制面板。 发起方可以从用户管理其状态和呼叫Skype for Business。 服务器管理员为企业启用和配置单位电话呼叫。 有关详细信息，请参阅[Plan for Call Via Work in Skype for Business Server 2015。](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>移动设备支持改进

对移动设备支持的改进包括改进 Enterprise Edition 用户的移动体验的功能，例如访问对话历史记录和日志数据、增强的移动会议体验以及跨 Office 的单一登录支持。 此外，还改进了 Android 支持、性能改进和功能，以通过 Common App Framework 简化集成。 
  
> [!NOTE]
> Lync 2013 UCWA 服务器必须升级到 Skype for Business Server 2015 以支持移动客户端。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>现在可在移动设备上使用服务器端对话历史记录

为了允许移动访问对话历史记录、错过的 IM 和呼叫日志数据，此信息的存档现在通过服务器处理所有移动客户端。 IM 的自动接受功能在移动用户没有立即响应 IM 时阻止服务器出现错误消息，从而提高了可靠性。 若要利用基于服务器的 Exchange/Outlook 文件夹集成，Exchange Server 2013 或更高版本以及更新的移动客户端是必需的。 
  
### <a name="enhanced-meeting-experiences"></a>增强的会议体验

桌面版上可用的会议功能现在也可供移动用户使用。 新功能包括：
  
- 共享内容内容的PowerPoint导航
- 演示者控制共享内容PowerPoint的能力
- 演示者的会议厅管理，允许他们允许或拒绝参与者
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business Android 改进

Skype for Business Android 版现在提供的功能与 iOS 上的 Skype for Business 和 Skype for Business 上Windows：
  
- 继续或重新加入对话
- 启用证书和被动身份验证
- 邀请其他人加入对话
- 轻松启动组对话
- 无需成为用户即可Skype for Business会议
- 在 Android 平板电脑上启用智能手机 UI
- 通过添加或删除参与者来管理会议
    
> [!NOTE]
> 这些功能需要 Android OS 4.0 版或以上版本。 
  
## <a name="management-of-on-premises-servers"></a>管理内部部署服务器

Skype for Business Server 2015 提供了一些新功能来提高本地服务器的可管理性，包括就地升级、智能设置、改进的修补和升级过程、改进的前端池冷启动功能、SQL Server AlwaysOn 支持以及集中日志记录和故障排除。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>本地服务器的就地升级

现在，您可以使用新的就地升级功能将 Lync Server 2013 系统升级到 Skype for Business Server 2015，该功能使用现有的 Lync Server 2013 硬件和服务器投资，从而降低了部署 Skype for Business Server 2015 的总成本。
  
就地升级有两种方案：Move User 方法（无需停机）和 Offline 方法（需要停机时间）。 有关哪种升级过程适合你的企业的信息，请参阅 Plan [to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
> [!NOTE]
> 如果从 Lync Server 2010 升级，则就地选项不可用。 有关从 Lync Server 2010 升级的详细信息，请参阅 Plan [to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)。 
  
### <a name="smart-setup"></a>智能设置

自动检测和下载更新的智能设置功能现在是安装程序的一部分。 在安装过程中，将询问用户安装过程是否应检查更新。 有关详细信息，请参阅 Install [Skype for Business Server 2015](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>改进的前端服务器修补和升级过程

Skype for Business Server引入了两个新的 cmdlet，这两个 cmdlet 可帮助使升级或修补前端服务器比早期版本的 Lync Server 中容易得多。
  
当您需要向前端服务器应用修补程序或执行任何其他维护时，只需键入 **Invoke-CsComputerFailOver** 并指定该服务器的名称。 Skype for Business Server将该服务器的工作负荷临时移动到池中的其他服务器。 然后，您可以执行维护，然后使用 **Invoke-CsComputerFailback** cmdlet 使该服务器重新进入服务。 如果需要修补池中的每台服务器，只需针对每台服务器执行此过程，一次修补一个服务器。 这些新 cmdlet 使您能够比早期版本更快地修补服务器，并且具有更高的可靠性和更简单的工作流。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>改进的前端池冷启动功能

Skype for Business Server引入了一个新的 cmdlet，可简化并改进冷启动整个前端池的过程。 使用新的 **Start-CsPool** cmdlet 时，它会检查池中所有前端服务器的先决条件，然后尝试启动每台服务器。 如果遇到任何问题，它会诊断它们，并通知你详细信息和解决方法。 在某些情况下，即使某些单台服务器无法启动，它仍允许您启动池。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server对内部部署服务器的 AlwaysOn 支持

Skype for Business Server 2015 增加了对 AlwaysOn 可用性SQL Server和 AlwaysOn 故障转移SQL Server实例的支持。 除了这些功能之外，Skype for Business Server像以前版本的 Lync Server 一样SQL Server对数据库镜像和数据库群集的支持。
  
SQL ServerAlwaysOn 可用性组是 SQL Server 2012 和 SQL Server 2014 中的高可用性和灾难恢复解决方案，可提供数据库镜像的替代方法。 可用性组支持一组离散数据库的故障转移 (称为可用性) 一起故障转移的数据库。 可用性组支持一组读写主数据库以及一到四组相应的辅助数据库。 （可选）辅助数据库可用于只读访问和某些备份操作。
  
SQL Server故障转移群集实例利用 Windows Server 故障转移群集 (WSFC) 功能，通过服务器实例级别的冗余（故障转移群集实例 (FCI) ）提供本地高可用性。 FCI 是一个 SQL Server 实例，它安装在 Windows Server 故障转移群集 (WSFC) 节点，并且可能跨多个子网。
  
有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>内部部署服务器的集中日志记录和故障排除改进

集中日志记录服务是 Skype for Business Server 2015 的首选日志记录环境。 此版本没有新功能，但服务和集中日志记录服务代理 (ClsAgent.exe) （与控制器通信并接收管理员发出的命令的服务可执行文件）的可靠性和性能都得到了改进。
  
Skype for Business Server 2015 Windows PowerShell cmdlet 管理日志记录服务代理、启动跟踪并生成报告。  (Lync Server 2013 ClsController.exe执行这些任务。) 
  
集中日志记录服务可在任何 Skype for Business Server 2015 运行。 预定义跟踪 (的内置方案) 与创建自定义方案的能力相同。 有一种称作 AlwaysOn 的特殊方案始终在运行，并允许管理员以近实时状态查找常见问题。
  
Snooper 调试工具也进行了更新，以允许调试移动日志，并用于连接到 Lync 2013 或 Skype for Business Server 2015 的设备。 该工具可从调试工具 下载[Web。](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>混合部署和管理

Skype for Business Server 2015 中引入了以下功能，从而启用混合部署管理和管理功能：
  
- 推荐客户本地资产的状态（由 OnRamp for Office 365自动协助工具确定）进行混合部署。
- 增强的 Skype for Business Server 控制面板和 Skype for Business Server 管理中心，以便管理员可以使用这些工具管理混合部署。
- 控制面板增强功能，使管理员能够登录到 Microsoft 365 或 Office 365 租户，并借助混合Skype for Business向导设置与 Skype for Business Online 的混合。
- 控制面板支持将本地用户移动到 Skype for Business Online 或Skype for Business Online 用户移回本地。
- 控制面板功能，用于标识和筛选已移动到 Skype for Business Online (（即混合用户) 本地用户）。
- 用于标识和筛选最初在 Skype for Business Online 中创建的云用户的管理中心功能，这些用户来自从本地迁移到 Online 的混合用户。
- 使用控制面板管理从本地可管理的属性和管理中心管理混合用户的能力，以及使用管理中心从 Skype for Business Online 管理的属性。
- 使用密码同步与 DirSync，能够将本地 Active Directory 密码与联机租户同步。 如果配置此功能，则无需部署 AD FS 进行联合身份验证，但多重身份验证仍然需要 AD FS。 
- 继续支持 Skype for Business Online 和 Exchange 内部部署之间的共存。
    
> [!NOTE]
> 与 Lync Online 2013 和 Exchange共存和支持体验没有变化。 
  
## <a name="multi-factor-authentication"></a>多重身份验证

多重身份验证是一种身份验证方法，要求使用多种验证方法，并将关键的第二层安全性添加到用户登录和事务中。 例如，需要用户名和密码以及证书。 Skype for Business Server 2015 年继续基于 Lync Server 2013 累积更新中提供的多重身份验证功能构建。 多重身份验证的显著变化包括：
  
- 使用 Office 2013 SP1 Active Directory 身份验证库与 Exchange 和 SharePoint
- 支持客户端中的多重Skype for Business Web应用功能
    
通过Skype for Business多重身份验证，现在可以基于地理位置提供不同的身份验证选项。 例如，客户可以配置其环境，以便内部身份验证依赖于集成身份验证Windows身份验证，而从组织外部进行身份验证的员工使用多重身份验证。 
  
无论Skype for Business，多因素身份验证体验都是无缝的：
  
- 地理位置 - 用户是从组织内部还是外部登录 
- 客户端/设备类型 - Skype for Business客户端以及客户端在 (电脑、移动设备、iPad等设备上) 
- 帐户位置 - 用户是托管在本地 Active Directory 中，还是托管在 Azure Active Directory Online 中。
