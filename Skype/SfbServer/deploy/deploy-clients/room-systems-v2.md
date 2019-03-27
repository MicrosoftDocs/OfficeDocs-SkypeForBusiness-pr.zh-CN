---
title: 部署 Skype 会议室系统 v2
ms.author: Turgayo
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读此文，了解有关部署 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 7d80a803038724e8818ab01f6b4ae54b552cabcd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879775"
---
# <a name="deployment-overview"></a>部署概述

部署的 Skype 会议室系统 v2 本质上细分为多个阶段：

- 确认您的部署位置 （聊天室） 满足部署依赖项
- 为业务和 Exchange 帐户创建 Skype 并将其分配给 （请参阅[配置帐户的 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)） 的控制台设备
- 重新构建 Microsoft Surface 平板电脑，以用作 Skype 会议室系统 v2 控制台 （请参阅[Configure Skype 会议室系统 v2 控制台](console.md)或[部署 Skype 会议室系统 v2 大量部署指南 》](room-systems-scale.md)）
- （可选）设置您的系统 （请参阅[部署 Skype 会议室系统 v2 管理使用 Azure 监视器](azure-monitor.md)） Microsoft 操作管理套件
- 设置控制台会议室和连接的外围设备中需要 （请参阅您的设备的集 OEM 文档）

AV 技术可用于最后一项任务，但您的组织的 IT 部门将需要执行此过程的其他部分。 


## <a name="site-readiness"></a>网站准备工作 

时的有序的设备将传递给您的组织，使用您的网络和设施和 AV 团队，以确保满足部署依赖项，并且每个站点和房间已准备方面电源、 网络，并显示。 此外，请确保满足物理安装要求。 有关物理安装注意事项，请访问供应商的网站，并利用 AV 团队安装时和时装入屏幕和运行电缆的体验。

您可以找到有关在下面的规划指南链接这些依赖关系的更多信息：

-   [检查网络可用性](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#check-network-availability) 
-   [证书](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#certificates)
-   [代理](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#proxy)

**专业人员提示**-如果您打算使用代理服务器业务 online，[查看本文](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)的第一个提供对 Skype 的访问。 请注意，当谈到 Skype 的业务流量通过代理服务器，我们建议完全绕过代理服务器。 已加密的业务通信的 Skype，以便代理服务器不进行更安全。 作为您更多 Skype 业务部署的一部分，我们建议您按照[评估我的环境](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness)中的带宽规划和评估您的网络适合于实时通信的指南。 所有带宽规划，都使用[MyAdvisor 网络计划程序](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)。 （我们建议您创建 Skype 会议室系统 v2 角色反映的预期的 Skype 会议室系统 v2 用法 [视频、 屏幕共享、 音频] 并分配多个用户相匹配的 Skype 会议室系统单位为部署到每个网站数。） 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您的网站满足 Skype 会议室系统 v2 的主要要求。</li><li>确认您已为每个站点提供足够的带宽。</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划您的设备部署和配置。</li></ul>| 

**专业人员提示-** 从网站的网站规划角度看，可能会发现有用的以下资产。 他们覆盖多个只 Skype 会议室系统 v2，并可用于在完整推出 Skype 业务联机：

-   [网站推出/迁移规划传递指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [网站推出和迁移计划-设置方案](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > 设置方案，在下您计划部署 Skype 会议室系统 v2 设备每个网站的"4 终结点"表中完成部分"4.3 – > 会议室"中的任务。 这将使您可以使用批量帐户设置过程中的更高版本的脚本。 

## <a name="service-readiness"></a>服务就绪

若要准备 Skype 会议室系统部署，请执行以下项、 管理中心任务：

-   Skype 会议室系统服务帐户功能定义。
-   准备要保留 Skype 会议室系统计算机和服务帐户的组织单位和 Active Directory 组和 — （可选) — 准备组策略对象 (Gpo) 启用 PowerShell 远程功能管理。

### <a name="define-skype-room-systems-service-account-features"></a>定义 Skype 会议室系统服务帐户功能 

根据您决定要启用 Skype 会议室系统 v2 部署的协作方案，您需要确定的特性和功能分配给您启用每个 Skype 会议室系统 v2 服务帐户。

| **应用场景** | **说明** | **Skype 会议室系统 v2 服务帐户功能** |
|---------- |------------- | --- |
| 交互式会议            | 使用语音、 视频和屏幕共享;使 bookable 资源的 Skype 会议室系统 v2                     | 启用业务，启用 Exchange （资源邮箱） 的 Skype |
| 电话拨入式会议            | 启用会议启动*直接*从电话拨入式会议坐标 Skype 会议室系统 v2 控制台 | 启用音频会议                                          |
| 出站/入站 PSTN 呼叫 | 启用 Skype 会议室系统 v2 控制台发起和接收 PSTN 呼叫                                         | 启用电话系统                                                |

有关 Skype 会议室系统帐户的详细信息，请参阅[配置帐户的 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)。


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定哪种方案将支持，以及确定为 Skype 会议室系统 v2 服务帐户的许可要求。</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备承载计算机和服务帐户。</li></ul>| 


_规划表的示例 Skype 会议室系统 v2 服务帐户_

| **站点**  | **会议室名称** | **聊天室类型** | **将来聊天室功能**                                                 | **Skype 会议室系统 v2 帐户功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 伦敦总部 | Curie         | 中        | 1 个屏幕上，音频和视频以及演示文稿 <br>电话拨入式会议访问<br> PSTN 访问  | 启用业务，启用 Exchange （资源邮箱） 的 Skype <br>启用音频会议 <br>启用电话系统 |
| 悉尼总部 | 峰          | 大         | 2 屏幕，音频和视频以及演示文稿<br>电话拨入式会议访问<br> PSTN 访问  | 启用业务，启用 Exchange （资源邮箱） 的 Skype<br> 启用音频会议 <br>启用电话系统 |


### <a name="prepare-to-host-skype-room-systems-v2-machine-and-service-accounts-optional"></a>准备对主机 Skype 会议室系统 v2 和服务帐户 （可选）

若要使您能够管理和 Skype 会议室系统 v2 计算机上的报告和服务帐户，准备本地 Active Directory 或 Azure Active Directory (Azure AD)。 

定义要添加收件人、 所有 Skype 会议室系统 v2 服务 （用户） 帐户在本地 Active Directory 或 Azure AD 组，然后创建跨 Skype 会议室系统 v2 部署使用 Get-CSUserSession PowerShell cmdlet 的使用率报告。 例如，创建名为 SkypeRoomSystemsv2 服务帐户的组。 


定义您的本地 Active Directory 或 Azure AD 的层次结构来保存所有 Skype 会议室系统 v2 计算机帐户 （如果他们加入到域） 中的一个组织单位和一个组织单位来都保存所有 Skype 会议室系统 v2 的用户帐户。 如果创建组织单位的 Skype 会议室系统 v2 计算机帐户，请考虑禁用继承，以确保您应用仅适用于加入域的 Skype 会议室系统 v2 的策略。 

创建组策略对象分配给包含您 Skype 会议室系统计算机帐户的组织单位。 使用此到： 

-   [设置电源和本地帐户设置](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#configuring-group-policy-for-skype-room-systems-v2)。
-   启用 Windows Update。
-   启用 PowerShell 远程功能管理。 您可以配置启动脚本以运行一个简单的脚本： Enable-psremoting-Force

您可以使用 PowerShell 执行大量的远程管理活动，包括获取和设置配置信息。 PowerShell 远程功能管理必须启用*之前*可以远程管理任何 PowerShell 放置和应考虑部署过程的一部分，或通过组策略配置。 有关这些功能以及启用它们的详细信息，请参阅[维护和操作](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>配置和部署 

规划配置和部署包括以下主要领域：

-   帐户设置
-   设备软件安装
-   设备部署
-   Skype 会议室系统 v2 应用程序和外围设备配置
-    测试
-   资产管理

### <a name="account-provisioning"></a>帐户设置 

每个 Skype 会议室系统 v2 设备需要必须启用业务和 Exchange 这两个 Skype 的专用和唯一资源帐户。 此帐户必须具有会议室邮箱位于 Exchange，并且将启用为会议室中 Skype 业务部署。 在 Exchange 一侧，以便设备可以自动接受传入会议请求，则必须配置日历处理。 有关创建这些帐户的详细信息，请参阅[配置帐户的 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)。 

**专业人员提示**– 进行显示名称为这些帐户描述性且易于理解。 这些是搜索和将 Skype 会议室系统 v2 系统添加到会议时，用户会看到的名称。 某些组织使用的约定*网站*-*会议室名称*（*最大聊天室容量*）-RS，因此，例如 Curie — 伦敦 12 人会议室 — 可能就 CURIE （12)-RS 的显示名称。 

如果您的组织有许多需要多个的会议室，已设置的帐户，您可能需要使用[Skype 会议室系统帐户设置脚本](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5)批量设置以自动方式的多个服务帐户。


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定您 Skype 会议室系统 v2 帐户的命名约定。</li><li>决定将创建个人帐户还是使用批量设置脚本。</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署。</li></ul>| 


### <a name="device-software-installation"></a>设备软件安装 

规划部署 Skype 会议室 Systemsv2 时, 必须考虑安装所需的软件的选项数。 下表中描述常见方案和方法。 

| **应用场景**            | **方法**         |
|-------------------------|-----------------------|   
|部署少量 Skype 会议室系统设备 (<10)。 | 如果使用基于 Surface Pro Skype 会议室系统 v2，请按照[为每个设备的安装说明安装](console.md)。 [此通过单一便捷式视频将指导您完成整个过程。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果使用集成的解决方案，请使用供应商图像部署和配置所需的设置。 |
| 部署之间 10 到 50 从单一供应商的设备。     | 创建基于 WIM 图像、 在[步骤 6 指南中](console.md)后, 暂停和捕获使用与克隆分发技术的通讯组映像。    |
| 部署 50 个以上的 Skype 会议室系统设备、 部署设备从多个供应商，或需要部署的一部分的特定于组织的代理。 | 使用任务 sequencer 基于软件构建和分发平台，如[System Center Configuration Manager](room-systems-scale.md)。  |

**专业人员提示**-每个 Skype 会议室系统 v2 必须具有有效且唯一的计算机的名称，在您的网络。 许多监控和警报系统显示计算机名称为密钥标识符，因此很重要开发允许支持人员轻松地找到被标记为 Skype 会议室系统 v2 Skype 会议室系统 v2 部署的命名约定要求操作。 示例 ネ ヤ ト SR-*网站*的模式-*会议室名称*(SR 就 CURIE)。 


作为部署的一部分，您还需要考虑的策略进行管理和配置由 Skype 会议室系统应用程序安装程序创建的[本地帐户](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)。

我们提供了有关如何使用[Microsoft Azure 监视器](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)来监视 Skype 会议室系统 v2 部署和报告可用性、 硬件/软件错误和 Skype 会议室系统 v2 应用程序版本的指导。 如果您决定使用 Microsoft 操作管理套件，您应安装的软件安装过程一部分的操作管理套件代理，并为您的工作区配置 workspace 连接信息。 

其他考虑事项是 Skype 会议室系统 v2 是否将加入域的。 [Skype 会议室系统域加入注意事项](domain-joining-considerations.md)中找不到的优势的加入域的信息。 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定 Skype 会议室系统设备命名约定，您在部署期间使用。</li><li>决定是否将加入到您的域的 Skype 会议室系统 v2 设备以及如何管理和配置本地帐户。 </li><li>决定是否将使用操作管理套件监视 Skype 会议室系统 v2 部署。</li><li>决定哪种方法，您将使用部署准备设备部署中的 Skype 会议室系统 v2 系统软件和代理。 </li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署方法。</li></ul>| 


### <a name="device-deployment"></a>设备部署

您已部署到的 Skype 会议室系统 v2 单位的软件后，创建您的计划附带的设备，在聊天室中，为其分配外围设备，然后再继续安装和配置。 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定谁将管理网站的网站部署。</li><li> 确定将在网站上安装的 Skype 会议室系统 v2 设备并将要配置的资源和测试。</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始测试设备。</li></ul>| 

_示例部署表_

| **站点**  | **会议室名称** | **聊天室类型** | **Skype 会议室系统 v2 系统**  | **外围设备**  | **Skype 会议室系统 v2 计算机名称**  | **Skype 会议室系统 v2 资源帐户**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 伦敦总部 | Curie         | 中        |                                   |                  |                                          |                                             |
| 悉尼总部 | 峰          | 大         |                                   |                  |                                          |                                             |

### <a name="skype-room-systems-v2-application-and-peripheral-device-configuration"></a>Skype 会议室系统 v2 应用程序和外围设备配置 

每个 Skype 会议室系统 v2 系统已从物理上隔离部署和支持的外围设备连接，您需要配置 Skype 会议室系统 v2 应用程序分配的 Skype 会议室系统 v2 资源帐户和密码之前，创建后到启用 Skype 会议室系统 v2 系统的业务和 Exchange 登录到 Skype。 它的键来利用 Skype 业务认证 USB 音频和视频的外围设备链接文档中的其他位置。 不执行此操作会导致不可预测的行为。 

您可以手动配置每个 Skype 会议室系统 v2 系统。 或者，您可以使用集中存储 – Skype 会议室系统 XML 配置文件管理应用程序设置并利用启动 GPO 脚本重新应用您希望，每次 Skype 会议室系统 v2 系统启动的配置。 

有关如何使用 XML 配置文件的详细信息，请参阅[管理 Skype 会议室系统 v2 控制台远程使用 XML 配置文件的设置](../../manage/skype-room-systems-v2/xml-config-file.md)。 

您可以使用[远程 PowerShell](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell)提取的 Skype 会议室系统 v2 配置报告需求。 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是否将手动配置每个 Skype 会议室系统 v2 系统或使用管理中心的 XML 文件 （Skype 会议室系统 v2 设备每一个）。</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义远程管理方法。</li></ul>| 

### <a name="testing"></a> 测试

Skype 会议室系统 v2 系统部署完后，您应测试它。 检查已部署的设备上的[Skype 会议室系统 v2 帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能都正常工作。 我们强烈建议部署小组验证到 Microsoft 操作管理套件 Skype 会议室系统 v2 （是否使用） 的记录。 也很重要您进行测试呼叫和会议以检查质量的数字。 有关详细信息，请参阅此[有用的部署清单](console.md#skype-room-systems-v2-deployment-checklist)。 

我们建议，作为常规 Skype 业务范围内部署的一部分，您配置的呼叫质量仪表板 (CQD) 的生成文件、 监视质量趋势和参与体验质量审查过程。 有关详细信息，请参阅[用户体验质量审阅指南](https://aka.ms/qerguide)。 

您应当查看使用作为测试的一部分的 Skype 会议室系统 v2 测试数与**专业人员提示**– 可从[MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) [测试矩阵](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21)包含选项卡。 

### <a name="asset-management"></a>资产管理 

作为部署的一部分，您将需要更新资产注册会议室名称、 Skype 会议室系统 v2 设备名称、 登录 Skype 会议室系统 v2 资源帐户，并分配外围设备 （以及他们使用的 USB 端口）。 

_资产的示例表_

| **站点**  | **会议室名称** | **聊天室类型** | **Skype 会议室系统 v2 序列号。**  | **外围设备 / 串行 nos./ 端口**  | **Skype 会议室系统 v2 计算机名称**  | **Skype 会议室系统 v2 服务帐户**  | **部署的日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 伦敦总部 | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| 悉尼总部 | 峰          | 大         |                                          |                                          |                                          |                                            |                   |


