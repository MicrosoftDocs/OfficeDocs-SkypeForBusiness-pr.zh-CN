---
title: 数据和隐私信息
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 数据和隐私信息
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757087"
---
# <a name="approach"></a>方法

使用托管服务的客户将 Microsoft 委托其最有价值的资产 — 数据。 他们相信其隐私将受到保护，并且仅以符合其期望的方式使用。

该技术遵循隐私流程，以确保它遵守客户在收集和使用具有有效运行服务的数据方面的承诺。

## <a name="data-collection"></a>数据采集

技术收集的数据仅限于监视运行状况、根本原因和缓解已注册会议室中识别的问题所需的信息。

该技术将监视设备、收集遥测数据，并允许 Microsoft 以管理员身份远程访问和管理设备。

收集的遥测数据特定于会议室帐户，而不是单个用户。 在使用设备期间，活动日志中可能存在对单个用户的附带引用。

### <a name="who-can-access-your-data"></a>Who可以访问数据

技术服务采取有力措施，帮助保护客户数据免受未经授权人员的不当访问或使用。 这包括限制 Microsoft 人员和分包商的访问。

### <a name="zero-standing-access-data-storage"></a>零常用访问数据存储

该技术通过“零常用访问”原则，缓解了与具有特权访问的帐户相关的风险，这些帐户来自组织内部和外部的恶意行为者。 这使服务能够运行，默认情况下没有任何用户可用的权限。 结合实时和公正访问的原则，它提供了一个可靠的框架，在默认情况下是安全的和合规的。 诊断数据可通过内部门户提供给我们的服务运营团队。

## <a name="data-handling"></a>数据处理

Microsoft 受数据传输、存储、使用和保留的严格标准约束。 Microsoft 具有数据处理标准策略，这些策略应根据数据分类处理数据。

Microsoft 将一般数据保护条例 (GDPR) 数据保护权扩展到全球所有客户，而不仅仅是欧洲。

## <a name="data-classification"></a>数据分类

数据分类可用于遵守安全性、合规性和隐私要求以及收集、存储和使用用户个人信息的过程。


|分类|说明|示例|
| :- | :- | :- |
|客户内容|由管理员和用户直接提供/创建的内容。|<p>- 客户生成的 BLOB 或结构化存储数据</p><p>- 客户拥有/提供的机密 (密码、证书、加密密钥、存储密钥) </p>|
|最终用户身份信息 (EUII) |用于标识或可用于标识 Microsoft 服务用户的数据。 EUII 不包含客户内容。|<p>- 用户名或显示名称 (DOMAIN\UserName) </p><p>- 用户主体名称 (name@company.com) </p><p>- 用户特定的 IP 地址</p>|
|帐户数据|<p>客户计费信息和付款方式信息，包括管理员联系信息，如租户</p><p>管理员的名称、地址或</p><p>电话号码。</p>|<p>- 租户管理员联系信息 (例如，</p><p>租户管理员的姓名、地址、电子邮件地址、电话号码) </p><p>- 客户的预配</p><p>信息</p>|
|最终用户假名标识符 (EUPI) |<p>由 Microsoft 创建的标识符，绑定到 Microsoft 服务的用户。 当 EUPI 与其他信息（例如映射表）结合使用时，它将标识最终用户。 EUPI 不包含客户上传或创建的信息</p><p> (客户内容或 EUII) </p>|<p>- 用户 GUID、PUID 或 SID</p><p>- 会话 ID</p>|
|组织可识别信息 (OII) |可用于标识租户的数据，通常配置或使用情况数据。 此数据无法链接到用户，并且不包含客户内容。|<p>- 租户 ID (非 GUID) </p><p>- 电子邮件地址中的域名 (xxx@contoso.com) 或其他特定于租户的域</p><p>信息</p>|
|系统元数据|运行无法链接到用户或租户的服务或程序时生成的数据。|<p>- 事件日志</p><p>- 使用情况数据</p><p>- 配置数据</p>|

技术说明

为了监视、诊断和缓解部署中的任何问题，该技术会将数据发送到 Microsoft。 示例包括

1. 确保设备是最新的 (包括应用、OS、驱动程序、F/W) 
1. 确保设备已准备好使用登录 (、报告正常状态的所有外围设备等) 
1. 确保环境已就绪 (预配帐户、网络速度足够快等) 
1. 确定是否有硬件问题或安装问题 (如松散布线) 
1. 确定过度重启 (问题等的启发式)  

技术将使用操作（如操作）管理设备

1. 更新软件
1. 通过重启、重置 USB 连接&状态来缓解问题
1. 收集特定日志以帮助诊断问题

该技术不监视或录制解决方案工具包中的音频、视频、媒体或会议内容。 

### <a name="service-collected-data-categories"></a>服务收集的数据类别
 
|类别|详细信息|查询原因|
| :- | :- | :- |
|正在进行的数据收集&管理|IP 地址、会议室帐户的标识 (Exchange、Skype for Business和/或Teams) 、位置坐标、电子邮件以及门户中与 Microsoft 或软件的通信|标识并连接到管理下的系统;识别、诊断和缓解故障;跟踪使用情况、分析和Insights;查询&修复连接状态|
|临时数据收集&管理|<p>事件日志信息、会议室用户的用户活动/标识以及诊断信息\*、Windows系统查询 (示例：USB 设备列表、</p><p>电源状态等) </p>|识别、诊断和缓解故障以及使用情况、分析和Insights|
|<p>试用注册和</p><p>设置</p>|<p>Windows系统查询</p><p>示例：USB 设备列表、电源状态等。</p>|<p>注册、载入、订单和交付所必需，</p><p>并设置试用版。</p>|

\* 设备活动日志中的敏感 PII 在本地进行修订 (技术) 未收集：

1. 会议主题&正文
1. 会议与会者 (（如标题、电话号码等）的联系人卡片信息) 
1. 在会议 IM 消息内容中

>> [!NOTE]
>随着 Microsoft 技术的发展，特定数据可能会发生变化。 

### <a name="agent-data-classification"></a>代理数据分类

**MTRP 代理在持续监视期间收集的所有数据的详细说明**
|收集的数据说明|分类|
| :- | :- |
|共享设备的标识|OII|
|客户 ID|OII|
|MMR 代理目录位置|系统元数据|
|MTR 应用日志目录位置|系统元数据|
|设备序列号|系统元数据|
|设备生物信息|系统元数据|

|MMR 代理的版本|系统元数据|
| :- | :- |
|MTR 应用的版本|系统元数据|
|Teams应用的版本|系统元数据|
|MTR 应用的夜间维护作业时间|系统元数据|
|MMR 代理更新 URL|系统元数据|
|MMR 代理环|系统元数据|
|Windows OS 版本|系统元数据|
|当前登录用户|系统元数据|
|MMR 代理会话 GUID|系统元数据|
|域名|系统元数据|
|上次 OS 重启以来的时间|系统元数据|
|自上次 MMR 代理启动以来的时间|系统元数据|
|MTR 设备的制作和建模|系统元数据|
|设备正在使用状态|系统元数据|
|设备载入类型|系统元数据|
|连接的监视器数|系统元数据|
|MTR 扬声器详细信息|系统元数据|
|MTR 麦克风详细信息|系统元数据|
|MTR 默认扬声器详细信息|系统元数据|
|MTR 应用自动屏幕共享设置|系统元数据|
|MTR 应用蓝牙广告设置|系统元数据|
|上次更改密码的日期|系统元数据|
|MTR 密码轮换设置|系统元数据|
|MTR 应用Teams/Skype for Business设置|系统元数据|
|MTR 应用更新环|系统元数据|
|MTR 应用内容相机设置|系统元数据|
|MTR 应用会议名称设置|系统元数据|
|会议室前面的 MTR 应用显示设置|系统元数据|
|MTR 应用 GUID|系统元数据|
|代理地址和端口|系统元数据|
|MTR 设备的运行状况|系统元数据|
|MTR 会议室帐户的详细信息|OII|
|IPV4 地址和 IPV6 地址|OII|
|经度和纬度|OII|
|MTR 设备主机名|OII|
|MTR 设备时区|系统元数据|
|MTR 应用的状态|系统元数据|
|Crestron 服务详细信息|系统元数据|
|Logitech 固件版本和 Logitech 同步版本|系统元数据|
|正在使用的 CPU 总百分比|系统元数据|
|正在使用的 RAM 总数|系统元数据|
|MTR Skype或Teams应用使用的 CPU|系统元数据|
|MTR 设备温度|系统元数据|
|内部磁盘驱动器的状态|系统元数据|
|任何 MTR 应用崩溃的详细信息|系统元数据|
|设备上应用导致的任何检测到的内存泄漏的详细信息|系统元数据|

|<p>已在其中发生的任何设备蓝屏错误的详细信息</p><p>过去 24 小时</p>|系统元数据|
| :- | :- |
|<p>MTR 应用在会议期间检测到的任何错误的详细信息</p><p>设备</p>|系统元数据|
|已安装的软件详细信息|系统元数据|
|已安装/挂起/缺少热修补程序详细信息|系统元数据|
|识别的硬件详细信息|系统元数据|
|设备上所有驱动程序的详细信息|系统元数据|
|任何 MMR 设备修正的详细信息|系统元数据|
|过去 24 小时内会议室使用情况、会议时间和计数的详细信息|系统元数据|
|自动Windows存储更新的详细信息|系统元数据|
|Windows OS 更新的详细信息|系统元数据|
|MMR 代理粉碎详细信息|系统元数据|
|MMR 代理连接错误详细信息|系统元数据|
|有关是否启用 TPM 安全性的详细信息|系统元数据|
|MTR 设备连接状态的详细信息|系统元数据|

**数据 MTRP 代理收集事件诊断和修正**
|收集的数据说明|分类|
| :- | :- |
|<p>事件日志：系统、应用程序、Skype会议室系统、Microsoft-Windows-AppXDeploymentServer%4Operational、Microsoft-Windows- PowerShell%4Operational、Microsoft-Windows- AppXDeployment%4Operational、Microsoft-Windows- AppXDeploymentServer%4Operational、Microsoft-Windows- TWinUI%4Operational、Microsoft 托管会议室、Microsoft-Windows-</p><p>TaskScheduler%4Operational，安全性</p>|系统元数据|
|已编辑的 MTR 应用日志\*|系统元数据|
|Microsoft 团队日志|系统元数据|
|MMR 代理 sqlLitedb|系统元数据|
|设备电源状态信息的详细信息|系统元数据|
|设备组策略信息|系统元数据|
|审核所有 MMR 代理操作的跟踪|系统元数据|
\* 在本地编辑设备活动日志中的敏感 PII。

### <a name="enrollment"></a>注册


此技术将注册到联机门户，用于自动监视和支持服务，包括诊断和报告。 注册是通过使用设备的受信任平台模块 (基于 TPM) 公钥加密的网络通信完成的。

### <a name="un-enrollment"></a>取消注册

可以通过卸载技术来取消注册设备。 Microsoft 还将在解除授权期间从后端监视中删除设备，并可在请求时删除收集的数据。

### <a name="data-flow"></a>数据流

该技术会将代理中的数据流添加到 MTR 托管服务。

![从代理到 MTR 托管服务的数据流](../media/data-and-privacy-info-005.png)

启用Microsoft Defender for Endpoint集成将引入从 MDE 代理到 Microsoft Defender 基础结构的其他数据流。

![从 MDE 代理到 Defender 的其他数据流](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>合规性

生产该产品的所有工程师都必须接受安全和隐私意识培训。 Microsoft 还确保所有人员都认证接受隐私要求的责任。

该技术通过欧洲的数据中心 (欧盟) 、亚太地区 (APAC) 和美国 美国 () 的数据中心提供区域数据驻留支持。 这意味着服务客户将具有与其所选区域的数据中心中存储的组织相关的数据。

## <a name="additional-resources"></a>其他资源

Microsoft Teams 会议室安全：/microsoftteams/rooms/security Microsoft 隐私声明： https://aka.ms/privacyMicrosoft 的数据管理：https://www.microsoft.com/trust-center/privacy/data-management技术服务说明：[Microsoft Teams会议室托管服务](microsoft-teams-rooms-premium.md)
