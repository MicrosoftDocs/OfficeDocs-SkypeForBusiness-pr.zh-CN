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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本文以了解如何部署 Microsoft Teams 会议室（包括部署阶段）。
ms.openlocfilehash: 1f9edd4ccd2c0de00c91b99cef4f3f27b081b9ab
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015232"
---
# <a name="deployment-overview"></a>部署概述

Microsoft Teams 会议室的部署基本上分为几个阶段：

- 确认部署位置 (满足) 依赖项
- 创建Microsoft Teams帐户Skype for Business Exchange帐户并将其分配给Teams 会议室 (请参阅为[Microsoft Teams 会议室) ](rooms-configure-accounts.md)
-  (可选) 为系统设置 Azure Monitor ([请参阅使用 Azure Monitor](azure-monitor-deploy.md) Microsoft Teams 会议室管理
- 在Teams 会议室空间设置设备并连接所需的外围设备 (请参阅适用于您的一组设备的 OEM 文档) 

## <a name="site-readiness"></a>网站就绪 

将订购的设备传送到组织时，请与网络、设施和 AV 团队协作，确保满足部署依赖项，并且每个站点和空间在电源、网络和显示方面已准备就绪。 此外，确保满足物理安装要求。 有关物理安装注意事项，请咨询供应商，并利用 AV 团队在安装和安装屏幕以及运行布线时的经验。

可以在下面的规划指导链接中找到有关这些依赖项的更多信息：

-   [检查网络可用性](rooms-prep.md#check-network-availability)
-   [证书](rooms-prep.md#certificates)
-   [代理](rooms-prep.md#proxy)

**Pro提示**- 如果必须使用代理服务器来提供对 Teams 的访问权限，请 [首先查看本文](../proxy-servers-for-skype-for-business-online.md)。 在通过代理服务器Microsoft Teams实时媒体流量时，建议完全绕过代理服务器。 Microsoft Teams流量已加密，因此代理服务器不会使其更安全，并且会为实时流量增加延迟。 作为更广泛部署的一部分，我们建议您遵循[为 Teams 准备网络](../prepare-network.md)以进行带宽规划和评估网络对实时流量的适用性中的指导。

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![确认网站。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>请确认你的网站满足 Microsoft Teams 会议室的关键要求。</li><li>请确认为每个网站提供了足够的带宽。</li></ul>| 
| ![计划设备部署。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署和配置。</li></ul>| 

## <a name="service-readiness"></a>服务就绪

要准备 Microsoft Teams 会议室部署，请执行以下关键的中心任务：

-   定义Microsoft Teams 会议室帐户。
-   如果加入 Teams Room Azure Active Directory，请准备具有动态成员身份Azure AD组，以保存所有 Teams 会议室 资源帐户。 这会简化将来的管理，例如应用条件访问策略。 为了最轻松地利用Azure AD组，请确定一个命名约定，用于唯一标识Teams 会议室帐户。
-   如果加入 Teams Room 到 Active Directory，请准备组织单位和 Active Directory 组来保存 Microsoft Teams 会议室 计算机和资源帐户，并（可选）准备组策略对象 (GPO) 以启用 PowerShell 远程处理。

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>定义Microsoft Teams 会议室帐户功能 

根据决定通过 Microsoft Teams 会议室 部署启用的协作方案，需要确定分配给每个 Microsoft Teams 会议室的功能。

| **应用场景** | **说明** | **Microsoft Teams 会议室服务帐户功能** |
|---------- |------------- | --- |
| 交互式会议            | 使用语音、视频和屏幕共享；使 Microsoft Teams 会议室成为可预订资源                     | 为资源Microsoft Teams或Skype for Business启用;Exchange (资源邮箱)  |
| 拨入式会议            | 在主机上点击"新建会议"时有音频会议电话号码 | 为音频会议启用                                          |
| 出站/入站 PSTN 呼叫 | 启用 Microsoft Teams 会议室控制台以拨打和接收 PSTN 呼叫                                         | 为电话系统启用                                                |

有关 Microsoft Teams 会议室帐户的详细信息，请参阅[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)。


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![方案支持。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定支持哪些方案，并确定资源帐户Microsoft Teams 会议室要求。</li></ul>| 
| ![准备主机。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备托管计算机和资源帐户。</li></ul>| 


_资源Microsoft Teams 会议室计划表的示例_

| **网站**  | **会议室名称** | **会议室类型** | **未来会议室容量**                                                 | **Microsoft Teams 会议室帐户功能**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| 伦敦总部 | Curie         | 中型        | 1 个屏幕、音频和视频以及演示文稿 <br>拨入式会议访问<br> PSTN 访问  | 为资源Exchange (启用)  <br>为音频会议启用 <br>为电话系统启用 |
| 悉尼总部 | Hill          | 大型         | 2 个屏幕、音频和视频以及演示文稿<br>拨入式会议访问<br> PSTN 访问  | 为Skype for Business <br>为资源Exchange (启用) <br> 为音频会议启用 <br>为电话系统启用 |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>准备托管Microsoft Teams 会议室和资源帐户 (可选) 

若要管理和报告本地Microsoft Teams 会议室帐户，请准备本地 Active Directory 或 Azure Active Directory (Azure AD) 。 

定义本地 Active Directory 或Azure Active Directory组，以Microsoft Teams 会议室所有资源帐户。 如果使用 Azure Active Directory，请考虑使用动态组自动在组中添加和删除资源帐户。

在本地 Active Directory 层次结构中定义一个组织单位，用于保存所有 Microsoft Teams 会议室 计算机帐户 (如果已加入域) ，则保留一个组织单位来保存所有 Microsoft Teams 会议室 用户帐户。 禁用组策略继承，以确保仅将要应用到已加入域的域的策略Microsoft Teams 会议室。

创建分配给组织单位的组策略对象，该组织单元包含 Microsoft Teams 会议室计算机帐户。 使用此选项可以： 

-   [设置电源和本地帐户设置](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)。
-   启用 Windows 更新。
-   启用 PowerShell 远程处理。 可以将启动脚本配置为运行脚本：Enable-PSRemoting -Force

可以使用 PowerShell 执行多个远程管理活动，包括获取和设置配置信息。 必须 *先* 启用 PowerShell 远程处理，然后才能进行任何 PowerShell 远程管理，并且应将其视为部署过程的一部分或通过组策略进行配置。 有关这些功能及其启用的更多信息，请参阅[维护和操作](rooms-operations.md#remote-management-using-powershell)。 


## <a name="configuration-and-deployment"></a>配置和部署 

配置和部署规划包括以下关键领域：

-   资源帐户预配
-   设备软件安装
-   设备部署
-   Microsoft Teams 会议室应用程序和外围设备配置
-   测试
-   资产管理

### <a name="resource-account-provisioning"></a>资源帐户预配 

每个Microsoft Teams 会议室设备都需要一个专用且唯一的资源帐户，必须同时为 Microsoft Teams 或 Skype for Business 启用Exchange。 此帐户必须具有托管在 Exchange 上的会议室Exchange。 必须配置日历处理，以便设备可以自动接受传入的会议请求。 有关创建这些帐户的详细信息，请参阅[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)。 

**专业提示** - 每个 Microsoft Teams 会议室必须在网络上有有效且唯一的计算机名称。 许多监视和警报系统将计算机名称显示为密钥标识符，因此为 Microsoft Teams 会议室部署开发命名约定非常重要，该约定允许支持人员轻松找到标记为需要操作的 Microsoft Teams 会议室。 例如，可以使用 MTR-*地点*-*会议室名称* (MTR-LON-CURIE) 模式。 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![确定命名约定。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定资源帐户的命名Microsoft Teams 会议室约定。</li><li>决定是创建单个帐户还是使用批量配置脚本。</li></ul>| 
| ![下一步。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署。</li></ul>| 


### <a name="device-software-installation"></a>设备软件安装 

Teams 会议室由原始设备制造商和 OEM (预) 。

我们提供有关如何使用 Microsoft Azure [Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor)监视 Microsoft Teams 会议室 部署并报告可用性、硬件/软件错误以及Microsoft Teams 会议室版本的指南。 如果决定使用 Microsoft Operations Management Suite，则应在软件安装过程中安装 Operations Management Suite 代理，并为工作区配置工作区连接信息。 

另一个需要考虑的问题是 Microsoft Teams 会议室是否加入域。 有关域加入的好处的信息，请参阅为用户配置[组Microsoft Teams 会议室。](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![决策点设备命名。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定Microsoft Teams 会议室部署期间使用的资源帐户命名约定。</li><li>决定是否将设备Microsoft Teams 会议室域。 </li><li>确定是否要使用 Azure Monitor 来监视 Microsoft Teams 会议室部署。</li> 
| ![接下来的步骤计划设备。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署方法。</li></ul>| 


### <a name="device-deployment"></a>设备部署

确定如何创建并管理 Microsoft Teams 会议室 资源帐户后，创建计划，将设备及其分配的外围设备运送到会议室，然后继续进行安装和配置。


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![管理站点到站点部署。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定管理站点到站点部署的人员。</li><li> 确定将现场安装Microsoft Teams 会议室执行配置和测试的资源。</li></ul>| 
| ![开始设备测试。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试.</li></ul>| 

_示例部署表_

| **网站**  | **会议室名称** | **会议室类型** | **Microsoft Teams 会议室系统**  | **外围设备**  | **Microsoft Teams 会议室计算机名称**  | **Microsoft Teams 会议室资源帐户**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| 伦敦总部 | Curie         | 中型        |                                   |                  |                                          |                                             |
| 悉尼总部 | Hill          | 大型         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams 会议室应用程序和外围设备配置 

在Microsoft Teams 会议室系统的物理部署并连接支持的外围设备后，需要将 Microsoft Teams 会议室 应用程序配置为分配 Microsoft Teams 会议室 资源帐户和密码，使 Teams 会议室 能够登录Microsoft Teams或Skype for Business，Exchange。

可手动配置每个 Microsoft Teams 会议室系统。 或者，可以使用集中存储的、按Teams 会议室 XML 配置文件来管理应用程序设置。

有关如何使用 XML 配置文件的详细信息，请参阅[使用 XML 配置文件远程管理 Microsoft Teams 会议室控制台设置](xml-config-file.md)。 

可使用[远程 PowerShell](rooms-operations.md#remote-management-using-powershell) 来拉取 Microsoft Teams 会议室配置以满足报告需要。 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![决策点配置。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是手动配置每个 Microsoft Teams 会议室系统还是使用中央 XML 文件（每个 Microsoft Teams 会议室设备一个）。</li></ul>| 
| ![接下来的步骤远程方法。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义远程管理方法。</li></ul>| 

### <a name="testing"></a>测试

部署Teams 会议室后，应进行测试。 检查 [Microsoft Teams 会议室帮助](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us)中列出的功能是否在部署的设备上正常工作。 我们强烈建议部署团队验证Microsoft Teams 会议室是否显示在Teams中心。 同样重要的是要做一些测试电话和会议来检查质量。 有关更多信息，请参阅此[有用的部署清单](console.md#microsoft-teams-rooms-deployment-checklist)。

我们建议作为常规 Teams 或 Skype for Business 推出的一部分，配置通话质量仪表板 (CQD) 的构建文件，监控质量趋势，并参与体验质量审查过程。 有关更多信息，请参阅[改善和监控 Teams 通话质量](../monitor-call-quality-qos.md)。 

### <a name="asset-management"></a>资产管理

在部署中，需要将资产注册更新为聊天室名称、Microsoft Teams 会议室名称、Microsoft Teams 会议室帐户和分配的外围设备。 

_资产表示例_

| **网站**  | **会议室名称** | **会议室类型** | **Microsoft Teams 会议室序列号**  | **外围设备/序列号/端口**  | **Microsoft Teams 会议室计算机名称**  | **Microsoft Teams 会议室服务帐户**  | **部署日期** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| 伦敦总部 | Curie         | 中型        |                                          |                                          |                                          |                                            |                   |
| 悉尼总部 | Hill          | 大型         |                                          |                                          |                                          |                                            |                   |
