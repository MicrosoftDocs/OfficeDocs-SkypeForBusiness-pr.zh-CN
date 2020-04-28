---
title: 部署 Microsoft Teams 会议室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本文以了解如何部署 Microsoft 团队聊天室，包括部署阶段。
ms.openlocfilehash: cf5ba9614426c59412c53b7e0e9420ca09ef6267
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905404"
---
# <a name="deployment-overview"></a>部署概述

Microsoft 团队聊天室的部署实质上分为几个阶段：

- 确认部署位置（会议室）满足部署依赖关系
- 创建 Microsoft 团队或 Skype for business 和 Exchange 帐户，并将其分配给控制台设备（请参阅[配置 Microsoft 团队聊天室的帐户](rooms-configure-accounts.md)）
- 重置 Microsoft Surface 平板电脑以作为 Microsoft 团队聊天室控制台工作（请参阅[配置 Microsoft 团队聊天室控制台](console.md)或[部署 Microsoft 团队聊天室大容量部署指南](rooms-scale.md)）
- 可选为你的系统设置 Microsoft Operations Management Suite （请参阅[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)
- 在会议室中设置控制台并连接所需的外围设备（请参阅适用于您的设备集的 OEM 文档）

AV techs 可用于最后一项任务，但你所在组织的 IT 部门将需要执行该过程的其他部分。 


## <a name="site-readiness"></a>网站准备情况 

当已订购的设备正在发送给你的组织时，请与你的网络和设备和 AV 团队协作，以确保满足部署依赖关系，并且每个网站和聊天室均可在 power、网络和显示器方面随时准备就绪。 此外，请确保满足物理安装要求。 有关物理安装的注意事项，请访问供应商的网站，在安装和装入屏幕以及运行缆线时充分利用 AV 团队的体验。

你可以在下面的规划指南链接中了解有关这些依赖关系的详细信息：

-   [检查网络可用性](rooms-prep.md#check-network-availability)
-   [证书](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**Pro 提示**-如果你打算使用代理服务器提供对团队或 Skype For business Online 的访问权限，请先[查看本文](../proxy-servers-for-skype-for-business-online.md)。 请注意，当通过代理服务器上的 Skype for business 通信时，我们建议完全跳过代理服务器。 Skype for business 通信已加密，因此代理服务器不会使其更安全。 作为更宽部署的一部分，我们建议你按照为[团队](../prepare-network.md)进行带宽规划和评估你的网络对实时流量的适用性中的指南进行操作。

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您的网站满足 Microsoft 团队聊天室的关键要求。</li><li>确认您是否为每个网站都提供了足够的带宽。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署和配置。</li></ul>| 

## <a name="service-readiness"></a>服务就绪

若要准备 Microsoft 团队聊天室部署，请执行以下关键的中央任务：

-   定义 Microsoft 团队聊天室服务帐户功能。
-   准备组织单元和 Active Directory 组以保存 Microsoft 团队聊天室计算机和服务帐户，并（可选）准备组策略对象（Gpo）以启用 PowerShell 远程处理。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>定义 Microsoft 团队聊天室服务帐户功能 

根据你使用 Microsoft 团队聊天室部署确定要启用的协作方案，你需要确定分配给你启用的每个 Microsoft 团队聊天室服务帐户的功能和功能。

| **使用场景** | **说明** | **Microsoft 团队聊天室服务帐户功能** |
|---------- |------------- | --- |
| 交互式会议            | 使用语音、视频和屏幕共享;使 Microsoft 团队聊天室成为 bookable 资源                     | 已启用 Skype for Business，支持 Exchange （资源邮箱） |
| 电话拨入式会议            | 使用电话拨入式会议坐标*直接*从 Microsoft 团队聊天室控制台开始会议 | 已启用音频会议                                          |
| 出站/入站 PSTN 呼叫 | 启用 Microsoft 团队聊天室控制台以拨打和接收 PSTN 呼叫                                         | 已启用电话系统                                                |

有关 Microsoft 团队聊天室帐户的详细信息，请参阅[为 Microsoft 团队聊天室配置帐户](rooms-configure-accounts.md)。


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定你将支持哪些方案，并确定你的 Microsoft 团队聊天室服务帐户的授权要求。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备托管计算机和服务帐户。</li></ul>| 


_Microsoft 团队聊天室服务帐户规划表示例_

| **站点**  | **聊天室名称** | **会议室类型** | **未来的会议室功能**                                                 | **Microsoft 团队聊天室帐户功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 伦敦总部 | Curie         | 中        | 1屏幕，音频和视频以及演示文稿 <br>电话拨入式会议访问<br> PSTN 访问  | 已启用 Skype for Business，支持 Exchange （资源邮箱） <br>已启用音频会议 <br>已启用电话系统 |
| 悉尼总部 | 山          | 大         | 2屏、音频和视频以及演示文稿<br>电话拨入式会议访问<br> PSTN 访问  | 已启用 Skype for Business，支持 Exchange （资源邮箱）<br> 已启用音频会议 <br>已启用电话系统 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>准备托管 Microsoft 团队聊天室计算机和服务帐户（可选）

若要使你能够在 Microsoft 团队聊天室计算机和服务帐户上管理和报告，请准备你的本地 Active Directory 或 Azure Active Directory （Azure AD）。 

定义本地 Active Directory 或 Azure AD 组以将所有 Microsoft 团队聊天室服务（用户）帐户添加到，然后通过在 Microsoft 团队聊天室部署中使用 CSUserSession PowerShell cmdlet 创建使用情况报告。 例如，创建名为 "SkypeRoomSystemsv2" 的组-"服务帐户"。 


在本地 Active Directory 或 Azure AD 层次结构中定义一个组织单位，以容纳所有 Microsoft 团队聊天室计算机帐户（如果它们已加入域）和一个组织单位以保存所有 Microsoft 团队聊天室用户帐户。 如果你为 Microsoft 团队聊天室计算机帐户创建了一个组织单元，请考虑禁用继承，以确保仅将你打算应用的策略应用到加入域的 Microsoft 团队聊天室。 

创建分配给包含您的 Microsoft 团队聊天室计算机帐户的组织单位的组策略对象。 使用此内容可以： 

-   [设置 "电源" 和 "本地帐户" 设置](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   启用 Windows 更新。
-   启用 PowerShell 远程处理。 你可以配置启动脚本以运行简单脚本： Enable-PSRemoting

你可以使用 PowerShell 执行大量远程管理活动，包括获取和设置配置信息。 必须*先*启用 powershell remoting，然后才能执行任何 powershell 远程管理，并将其视为部署过程的一部分或通过组策略进行配置。 有关这些功能和启用这些功能的详细信息，请参阅[维护和操作](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>配置和部署 

规划配置和部署涵盖以下主要方面：

-   帐户预配
-   设备软件安装
-   设备部署
-   Microsoft 团队聊天室应用程序和外围设备配置
-    测试
-   资产管理

### <a name="account-provisioning"></a>帐户预配 

每个 Microsoft 团队聊天室设备都需要一个专用且唯一的资源帐户，该帐户必须同时为 Microsoft 团队或 Skype for business 和 Exchange 启用。 此帐户必须具有 Exchange 托管的聊天室邮箱，并且在团队或 Skype for business 部署中作为会议室启用。 在 Exchange 面上，必须配置日历处理，以便设备可以自动接受传入的会议请求。 有关创建这些帐户的详细信息，请参阅[为 Microsoft 团队聊天室配置帐户](rooms-configure-accounts.md)。 

**Pro 提示**-使这些帐户的显示名称具有描述性且易于理解。 这些是用户在搜索和将 Microsoft 团队聊天室系统添加到会议时将看到的名称。 某些组织使用约定*网站*-*聊天室名称*（*最大房间容量*）-rs，例如 Curie ———伦敦的12人会议室，可能会有显示名称 LON-Curie （12）-RS。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 团队聊天室帐户的命名约定。</li><li>确定是创建单个帐户还是使用批量预配脚本。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署。</li></ul>| 


### <a name="device-software-installation"></a>设备软件安装 

当规划部署 Microsoft 团队聊天室时，您有许多选项可考虑安装所需的软件。 下表介绍了常见的方案和方法。 

| **使用场景**            | **实现**         |
|-------------------------|-----------------------|   
|部署少量 Microsoft 团队聊天室设备（<10）。 | 如果使用基于 Surface Pro 的 Microsoft 团队会议室，请遵循针对[每台设备安装的安装说明](console.md)。 [此方便的视频可引导你完成此过程。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果使用集成的解决方案，请使用供应商映像部署，并根据需要配置设置。 |
| 从单个供应商的10和50设备之间进行部署。     | 创建基于 WIM 的映像，[在指南中的步骤 6](console.md)之后暂停，并捕获要与你的克隆分发技术一起使用的分发映像。    |
| 部署50多个 Microsoft 团队聊天室设备，从多个供应商处部署设备，或者要求组织特定的代理作为部署的一部分。 | 使用基于任务排序器的软件内部版本和分发平台，如[Microsoft 终结点配置管理器](rooms-scale.md)。  |


**Pro 提示**-每个 Microsoft 团队聊天室必须在您的网络上拥有一个有效且唯一的计算机名称。 许多监视和警报系统将计算机名称显示为密钥标识符，因此开发 Microsoft 团队会议室部署的命名约定非常重要，这使支持人员能够轻松找到已标记为需要操作的 Microsoft 团队聊天室。 示例可能使用了*MTR*-的模式 *（MTR* -CURIE）。 

作为部署的一部分，你还需要考虑管理和配置由 Microsoft 团队聊天室应用程序安装程序创建的[本地帐户](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)的策略。

我们提供有关如何使用[Microsoft Azure 监视器](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)监视 Microsoft 团队聊天室部署和报告可用性、硬件/软件错误和 Microsoft 团队聊天室应用程序版本的指南。 如果你决定使用 Microsoft Operations Management Suite，则应安装 Operations Management Suite 代理作为软件安装过程的一部分，并为你的工作区配置工作区连接信息。 

另一个考虑因素是，Microsoft 团队聊天室是否将加入域。 有关域加入的好处的信息可以在[Skype 会议室系统领域的 "加入注意事项](domain-joining-considerations.md)" 中找到。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定要在部署期间使用的 Microsoft 团队聊天室设备命名约定。</li><li>确定你是否要将 Microsoft 团队聊天室设备加入你的域，以及如何管理和配置本地帐户。 </li><li>确定是否使用 Operations Management Suite 监视 Microsoft 团队会议室部署。</li><li>确定你将使用哪种方法将软件和代理部署到 Microsoft 团队聊天室系统，以便为设备部署做好准备。 </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署方法。</li></ul>| 


### <a name="device-deployment"></a>设备部署

将软件部署到 Microsoft 团队会议室后，请创建你的计划以将设备和分配的外围设备发送到你的聊天室，然后继续安装和配置。 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定由谁来管理网站的网站部署。</li><li> 确定将在网站上安装 Microsoft 团队聊天室设备并执行配置和测试的资源。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试。</li></ul>| 

_示例部署表_

| **站点**  | **聊天室名称** | **会议室类型** | **Microsoft 团队会议室系统**  | **外围设备**  | **Microsoft 团队聊天室计算机名**  | **Microsoft 团队聊天室资源帐户**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 伦敦总部 | Curie         | 中        |                                   |                  |                                          |                                             |
| 悉尼总部 | 山          | 大         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft 团队聊天室应用程序和外围设备配置 

在每个 Microsoft 团队会议室系统均已进行物理部署且支持的外围设备已连接后，你需要配置 Microsoft 团队聊天室应用程序以分配之前创建的 Microsoft 团队聊天室资源帐户和密码，以使 Microsoft 团队聊天室系统能够登录到 Microsoft 团队或 Skype for business 和 Exchange。 利用在文档中其他位置链接的认证 USB 音频和视频设备的关键。 不要这样做可能会导致不可预测的行为。 

你可以手动配置每个 Microsoft 团队聊天室系统。 或者，你可以使用集中存储的每个-Microsoft 团队聊天室 XML 配置文件来管理应用程序设置，并利用启动 GPO 脚本重新应用所需的配置，每次 Microsoft 团队聊天室系统启动。 

有关如何使用 XML 配置文件的详细信息，请参阅[使用 xml 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)。 

你可以使用[远程 PowerShell](rooms-operations.md#remote-management-using-powershell)来获取 Microsoft 团队聊天室配置，以满足报告需求。 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定你是否要手动配置每个 Microsoft 团队聊天室系统或使用中央 XML 文件（每个 Microsoft 团队聊天室设备一个）。</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义您的远程管理方法。</li></ul>| 

### <a name="testing"></a> 测试

部署 Microsoft 团队聊天室系统后，应进行测试。 检查[Microsoft 团队聊天室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能是否在部署的设备上工作。 我们强烈建议部署团队验证 Microsoft 团队聊天室是否正在记录到 Microsoft Operations Management Suite （如果使用）。 您必须进行大量测试通话和会议才能查看质量。 有关详细信息，请参阅此[有用的部署清单](console.md#microsoft-teams-rooms-deployment-checklist)。

我们建议作为常规团队或 Skype for business 推出的一部分，配置为通话质量仪表板（CQD）生成文件、监控质量趋势以及参与体验审核流程。 有关详细信息，请参阅[体验质量检查指南](https://aka.ms/qerguide)。 

### <a name="asset-management"></a>资产管理

作为部署的一部分，你将需要使用房间名称、Microsoft 团队聊天室设备名称、登录的 Microsoft 团队聊天室资源帐户和分配的外围设备（以及它们使用的 USB 端口）更新资产注册。 

_示例资产表_

| **站点**  | **聊天室名称** | **会议室类型** | **Microsoft 团队聊天室序列号**  | **外围设备/串行 nos./端口**  | **Microsoft 团队聊天室计算机名**  | **Microsoft 团队聊天室服务帐户**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 伦敦总部 | Curie         | 中        |                                          |                                          |                                          |                                            |                   |
| 悉尼总部 | 山          | 大         |                                          |                                          |                                          |                                            |                   |


