---
title: 部署 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
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
description: 阅读本文以了解如何部署 Microsoft Teams 会议室（包括部署阶段）。
ms.openlocfilehash: 86564c8b90b0c7c8269d5de258c31d140eca7dc4
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646693"
---
# <a name="deployment-overview"></a>部署概述

Microsoft Teams 会议室的部署基本上分为几个阶段：

- 确认部署位置（会议室）符合部署依赖项
- 创建 Microsoft Teams 或 Skype for Business 和 Exchange 帐户并将其分配到控制台设备（请参阅为 [Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)）
- 重置映像 Microsoft Surface 平板电脑以用作 Microsoft Teams 会议室控制台（请参阅[配置 Microsoft Teams 会议室控制台](console.md)或[部署Microsoft Team Rooms 批量部署指南](rooms-scale.md)）
- （可选）为系统设置 Microsoft Operations Management Suite（请参阅[使用 Azure Monitor 部署 Microsoft Teams 会议室管理](azure-monitor-deploy.md)）
- 在会议室设置控制台并连接所需的外围设备（请参阅设备组的 OEM 文档）

AV 技术可以用于最后一项任务，但你组织的 IT 部门将需要完成该过程的其他部分。 


## <a name="site-readiness"></a>网站就绪 

在将订购的设备交付给你的组织时，请与你的网络和设施以及 AV 团队合作，以确保满足部署依赖项，并且每个站点和分组讨论室都在电源、网络和显示方面准备就绪。 此外，确保满足物理安装要求。 有关物理安装注意事项，请访问供应商的站点，并利用 AV 团队在安装和安装屏幕以及运行布线时的经验。

可以在下面的规划指导链接中找到有关这些依赖项的更多信息：

-   [检查网络可用性](rooms-prep.md#check-network-availability)
-   [证书](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**专业提示** - 如果打算使用代理服务器来访问 Teams 或 Skype for Business Online，请首先 [阅读本文](../proxy-servers-for-skype-for-business-online.md)。 在通过代理服务器Skype for Business流量时，建议完全绕过代理服务器。 Skype for Business 流量已经加密，因此代理服务器无法使其更安全。 作为更广泛部署的一部分，我们建议您遵循[为 Teams 准备网络](../prepare-network.md)以进行带宽规划和评估网络对实时流量的适用性中的指导。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![确认网站](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>请确认你的网站满足 Microsoft Teams 会议室的关键要求。</li><li>请确认为每个网站提供了足够的带宽。</li></ul>| 
| ![计划设备部署](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署和配置。</li></ul>| 

## <a name="service-readiness"></a>服务就绪

要准备 Microsoft Teams 会议室部署，请执行以下关键的中心任务：

-   定义 Microsoft Teams 会议室服务帐户功能。
-   准备一个组织单位和 Active Directory 组以保存 Microsoft Teams 会议室计算机和服务帐户，并可选地准备组策略对象 (GPO) 以启用 PowerShell 远程处理。

### <a name="define-microsoft-teams-rooms-service-account-features"></a>定义 Microsoft Teams 会议室服务帐户功能 

根据决定在 Microsoft Teams 会议室部署中启用的协作方案，需要确定分配给启用的每个 Microsoft Teams 会议室服务帐户的功能和容量。

| **应用场景** | **说明** | **Microsoft Teams 会议室服务帐户功能** |
|---------- |------------- | --- |
| 交互式会议            | 使用语音、视频和屏幕共享；使 Microsoft Teams 会议室成为可预订资源                     | 为 Skype for Business 启用，为 Exchange启用（资源邮箱） |
| 拨入式会议            | 启用 *直接* 从 Microsoft Teams 会议室控制台启动的具有拨入式会议坐标的会议 | 为音频会议启用                                          |
| 出站/入站 PSTN 呼叫 | 启用 Microsoft Teams 会议室控制台以拨打和接收 PSTN 呼叫                                         | 为电话系统启用                                                |

有关 Microsoft Teams 会议室帐户的详细信息，请参阅[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)。


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![方案支持](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定将支持哪些方案，并确定 Microsoft Teams 会议室服务帐户的许可要求。</li></ul>| 
| ![准备主机](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备托管计算机和服务帐户。</li></ul>| 


_Microsoft Teams 会议室服务帐户计划表示例_

| **网站**  | **会议室名称** | **会议室类型** | **未来会议室容量**                                                 | **Microsoft Teams 会议室帐户功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 伦敦总部 | Curie         | 中型        | 1 个屏幕、音频和视频以及演示文稿 <br>拨入式会议访问<br> PSTN 访问  | 为 Skype for Business 启用，为 Exchange 启用（资源邮箱） <br>为音频会议启用 <br>为电话系统启用 |
| 悉尼总部 | Hill          | 大型         | 2 个屏幕、音频和视频以及演示文稿<br>拨入式会议访问<br> PSTN 访问  | 为 Skype for Business 启用，为 Exchange 启用（资源邮箱）<br> 为音频会议启用 <br>为电话系统启用 |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>准备托管 Microsoft Teams 会议室计算机和服务帐户（可选）

若要使你能够管理和报告 Microsoft Teams 会议室计算机和服务帐户，请准备本地Active Directory 或 Azure Active Directory (Azure AD)。 

定义本地 Active Directory 或 Azure AD 组以将所有 Microsoft Teams 会议室服务（用户）帐户添加，然后在 Microsoft Teams 会议室部署中使用 Get-CSUserSession PowerShell cmdlet 创建使用情况报告。 例如，创建一个名为 SkypeRoomSystemsv2 服务帐户的组。 


在本地 Active Directory 或 Azure AD 层次结构中定义一个组织单位以保留所有 Microsoft Teams 会议室计算机帐户（如果它们已加入域），并定义一个组织单位以保留所有 Microsoft Teams 会议室用户帐户。 如果确实要为 Microsoft Teams 会议室计算机帐户创建组织单位，请考虑禁用继承，以确保仅将要应用于已加入域的 Microsoft Teams 会议室的策略应用。 

创建分配给组织单位的组策略对象，该组织单元包含 Microsoft Teams 会议室计算机帐户。 使用此选项可以： 

-   [设置电源和本地帐户设置](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   启用 Windows 更新。
-   启用 PowerShell 远程处理。 可以将启动脚本配置为运行脚本：Enable-PSRemoting -Force

可以使用 PowerShell 执行多个远程管理活动，包括获取和设置配置信息。 必须 *先* 启用 PowerShell 远程处理，然后才能进行任何 PowerShell 远程管理，并且应将其视为部署过程的一部分或通过组策略进行配置。 有关这些功能及其启用的更多信息，请参阅[维护和操作](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>配置和部署 

配置和部署规划包括以下关键领域：

-   帐户设置
-   设备软件安装
-   设备部署
-   Microsoft Teams 会议室应用程序和外围设备配置
-   测试
-   资产管理

### <a name="account-provisioning"></a>帐户设置 

每个 Microsoft Teams 会议室设备都需要专用且唯一的资源帐户，该帐户必须同时为 Microsoft Teams 或 Skype for Business 和 Exchange 启用。 此帐户必须在 Exchange 上有一个会议室邮箱，并且必须启用为 Teams 或 Skype for Business 部署中的会议室。 在 Exchange 端，必须配置日历处理，以便设备能够自动接受传入的会议请求。 有关创建这些帐户的详细信息，请参阅[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)。 

**专业提示** – 使这些帐户的显示名称具有描述性和易于理解。 用户在搜索 Microsoft Teams 会议室系统并将其添加到会议中时将看到这些名称。 有些组织使用会议 *地点*-的 *房间名称* (*最大会议室容量*)-RS，因此例如 Curie（伦敦一个 12 人会议室）的显示名称可能是 LON-CURIE(12)-RS。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![决定命名约定](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定 Microsoft Teams 会议室帐户的命名约定。</li><li>决定是创建单个帐户还是使用批量配置脚本。</li></ul>| 
| ![下一步](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署。</li></ul>| 


### <a name="device-software-installation"></a>设备软件安装 

规划部署Microsoft Teams 会议室时，有许多选项需要考虑安装所需的软件。 下表描述了常见的应用场景和方法。 

| **应用场景**            | **方法**         |
|-------------------------|-----------------------|   
|部署一些 Microsoft Teams 会议室 设备 (<10) 。 | 如果使用基于 Surface Pro 的 Microsoft Teams 会议室，请按照[每个设备的安装说明进行操作](console.md)。 [这个便利的视频将引导你完成整个过程。](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) 如果使用集成解决方案，请使用供应商映像进行部署，并根据需要配置设置。 |
| 从单个供应商部署 10 到 50 台设备。     | 创建基于 WIM 的映像，在[指南中的步骤 6 ](console.md)之后暂停，然后捕获分发映像以用于克隆分发技术。    |
| 部署 50 多个 Microsoft Teams 会议室设备，部署来自多个供应商的设备，或需要组织特定的代理作为部署的一部分。 | 使用基于任务序列器的软件构建和分发平台，如 [Microsoft Endpoint Configuration Manager](rooms-scale.md)。  |


**专业提示** - 每个 Microsoft Teams 会议室必须在网络上有有效且唯一的计算机名称。 许多监视和警报系统将计算机名称显示为密钥标识符，因此为 Microsoft Teams 会议室部署开发命名约定非常重要，该约定允许支持人员轻松找到标记为需要操作的 Microsoft Teams 会议室。 例如，可以使用 MTR-*地点*-*会议室名称* (MTR-LON-CURIE) 模式。 

作为部署的一部分，还需要考虑管理和配置由 Microsoft Teams 会议室应用程序安装程序创建的[本地帐户](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts)的策略。

我们提供有关如何使用 [Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) 监视 Microsoft Teams 会议室部署并报告可用性、硬件/软件错误和 Microsoft Teams 会议室应用程序版本的指南。 如果决定使用 Microsoft Operations Management Suite，则应在软件安装过程中安装 Operations Management Suite 代理，并为工作区配置工作区连接信息。 

另一个需要考虑的问题是 Microsoft Teams 会议室是否加入域。 有关加入域的好处的信息可以在 [Skype 房间系统域加入注意事项](domain-joining-considerations.md)中找到。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![决策点设备命名](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定部署期间要使用的 Microsoft Teams 会议室设备命名约定。</li><li>决定是否将 Microsoft Teams 会议室设备加入你的域，以及如何管理和配置本地帐户。 </li><li>决定是否使用 Operations Management Suite 监视 Microsoft Teams 会议室部署。</li><li>决定将使用哪种方法将软件和代理部署到 Microsoft Teams 会议室系统，以准备设备部署。 </li></ul>| 
| ![接下来的步骤计划设备](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署方法。</li></ul>| 


### <a name="device-deployment"></a>设备部署

将软件部署到 Microsoft Teams 会议室单元后，创建计划，将设备及其分配的外围设备派送到会议室，然后继续安装和配置。 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![管理站点到站点部署](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定管理站点到站点部署的人员。</li><li> 确定将在现场安装 Microsoft Teams 会议室设备并进行配置和测试的资源。</li></ul>| 
| ![开始设备测试](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试.</li></ul>| 

_示例部署表_

| **网站**  | **会议室名称** | **会议室类型** | **Microsoft Teams 会议室系统**  | **外围设备**  | **Microsoft Teams 会议室计算机名称**  | **Microsoft Teams 会议室资源帐户**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 伦敦总部 | Curie         | 中型        |                                   |                  |                                          |                                             |
| 悉尼总部 | Hill          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 会议室应用程序和外围设备配置 

在实际部署了每个 Microsoft Teams 会议室系统并连接了受支持的外围设备后，需要配置 Microsoft Teams 会议室应用程序以分配先前创建的 Microsoft Teams 会议室资源帐户和密码，以使 Microsoft Teams 会议室系统能够登录到 Microsoft Teams 或 Skype for Business 和 Exchange。 利用文档中其他地方链接的认证的 USB 音频和视频外围设备是关键。 不这样做会导致不可预知的行为。 

可手动配置每个 Microsoft Teams 会议室系统。 或者，可使用集中存储的、按 Microsoft Teams 会议室的 XML 配置文件来管理应用程序设置，并在每次启动 Microsoft Teams 会议室系统时利用启动 GPO 脚本重新应用所需的配置。 

有关如何使用 XML 配置文件的详细信息，请参阅[使用 XML 配置文件远程管理 Microsoft Teams 会议室控制台设置](xml-config-file.md)。 

可使用[远程 PowerShell](rooms-operations.md#remote-management-using-powershell) 来拉取 Microsoft Teams 会议室配置以满足报告需要。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![决策点配置](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是手动配置每个 Microsoft Teams 会议室系统还是使用中央 XML 文件（每个 Microsoft Teams 会议室设备一个）。</li></ul>| 
| ![接下来的步骤远程方法](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义远程管理方法。</li></ul>| 

### <a name="testing"></a>测试

部署了 Microsoft Teams 会议室系统之后，应该对其进行测试。 检查 [Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中列出的功能是否在部署的设备上正常工作。 我们强烈建议部署团队验证 Microsoft Teams 会议室是否正在登录到 Microsoft Operations Management Suite（如果使用）。 同样重要的是要做一些测试电话和会议来检查质量。 有关更多信息，请参阅此[有用的部署清单](console.md#microsoft-teams-rooms-deployment-checklist)。

我们建议作为常规 Teams 或 Skype for Business 推出的一部分，配置通话质量仪表板 (CQD) 的构建文件，监控质量趋势，并参与体验质量审查过程。 有关更多信息，请参阅[改善和监控 Teams 通话质量](../monitor-call-quality-qos.md)。 

### <a name="asset-management"></a>资产管理

作为部署的一部分，需要使用会议室名称、Microsoft Teams 会议室设备名称、已登录的 Microsoft Teams 会议室资源帐户和分配的外围设备（以及它们使用的 US B端口）更新资产注册表。 

_资产表示例_

| **网站**  | **会议室名称** | **会议室类型** | **Microsoft Teams 会议室序列号**  | **外围设备/序列号/端口**  | **Microsoft Teams 会议室计算机名称**  | **Microsoft Teams 会议室服务帐户**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 伦敦总部 | Curie         | 中型        |                                          |                                          |                                          |                                            |                   |
| 悉尼总部 | Hill          | 大型         |                                          |                                          |                                          |                                            |                   |