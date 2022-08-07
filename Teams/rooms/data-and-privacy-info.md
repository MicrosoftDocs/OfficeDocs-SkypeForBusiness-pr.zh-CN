---
title: 数据和隐私信息
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 数据和隐私信息
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 5799288005a5d30152a6f810c0aa40d451198390
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270297"
---
# <a name="approach"></a>方法

使用Microsoft Teams 会议室托管服务的客户将 Microsoft 委托其最有价值的资产数据。 他们相信其隐私将受到保护，并且仅以符合其期望的方式使用。

该技术遵循隐私流程，以确保它遵守客户在收集和使用有效运行服务的数据方面的承诺。
## <a name="data-collection-and-privacy"></a>数据收集和隐私

 Microsoft Teams 会议室托管服务监视设备、收集客户内容数据，以及以管理员身份远程访问和管理设备。 收集的数据仅限于监视已注册会议室中标识的运行状况、根本原因和缓解问题所需的信息。 收集的某些数据特定于会议室帐户，而不是单个用户。

> [!Note]
> 在使用设备期间，活动日志中可能存在对单个用户的附带引用。

## <a name="who-can-access-data"></a>谁可以访问数据

托管服务采取有力措施，帮助保护客户数据免受未经授权人员的不当访问或使用。 这些措施包括限制 Microsoft 人员和分包商的访问。

## <a name="zero-standing-access-data-storage"></a>零常用访问数据存储

托管服务通过“零常用访问”原则，缓解与具有来自组织内部和外部恶意执行组件的特权访问权限的帐户相关的风险。 此原则使托管服务能够在默认情况下运行，而不向任何用户提供任何权限。 结合实时和公正访问的原则，它提供了一个可靠的框架，在默认情况下是安全的和合规的。 可通过内部门户向 Microsoft 服务运营团队提供诊断数据。

## <a name="data-handling"></a>数据处理

Microsoft 受数据传输、存储、使用和保留的严格标准约束。 Microsoft 具有数据处理标准策略，这些策略根据数据分类来规范数据的处理方式。



## <a name="technology-description"></a>技术说明

托管服务将数据发送到 Microsoft，以便监视、诊断和缓解部署中的任何问题。 示例包括

- 确保设备是最新的 (包括应用、OS、驱动程序、F/W) 
- 确保设备已准备好使用登录 (、报告运行状况的所有外围设备等) 
- 确保环境已就绪 (预配帐户、网络速度足够快等) 
- 确定是否有硬件问题或安装问题 (如松散布线) 
- 确定过度重启 (问题等的启发式) 

托管服务使用以下操作管理设备：

- 更新软件
- 通过重启、重置 USB 连接&状态来缓解问题
- 收集特定日志以帮助诊断问题

托管服务不监视或录制解决方案工具包中的音频、视频、媒体或会议内容。

### <a name="service-collected-data-categories"></a>服务收集的数据类别
 
|类别|详细信息|查询原因|
| :- | :- | :- |
|正在进行的数据收集和管理|IP 地址、会议室帐户的标识 (Exchange、Skype for Business和/或 Teams) 、位置坐标、电子邮件以及门户中与 Microsoft 或软件的通信|标识并连接到管理下的系统;识别、诊断和缓解故障;跟踪使用情况、分析和见解;查询和修复连接状态|
|临时数据收集和管理|事件日志信息、来自登录日志文件的会议室用户的活动/标识以及诊断信息、Windows 系统查询 (示例：USB 设备列表、电源状态等) |识别、诊断和缓解故障以及使用情况、分析和见解|

设备活动日志中的某些敏感数据在本地进行编辑 (托管服务未收集) ：

- 会议主题和正文
- 会议与会者的联系卡片信息 (，如标题、电话号码等) 
- 在会议 IM 消息内容中

> [!NOTE]
> 随着 Microsoft 托管服务的发展，特定数据可能会发生变化。

### <a name="enrollment"></a>注册

托管服务已注册到联机门户，用于自动监视和支持服务，包括诊断和报告。 注册是通过使用设备的受信任平台模块 (基于 TPM) 公钥加密的网络通信完成的。

### <a name="unenrollment"></a>取消注册

可以通过卸载托管服务来取消注册设备。 Microsoft 还会在解除授权期间从后端监视中删除设备，并可在请求时删除收集的数据。
## <a name="compliance"></a>合规性

所有在产品上工作的工程师都必须接受安全和隐私意识培训。 Microsoft 还确保所有人员都认证接受隐私要求的责任。

托管服务通过欧洲的数据中心提供区域数据驻留支持， (欧盟) 、亚太地区 (APAC) 以及美国 (美国) 。 服务客户将具有与其所选区域的数据中心中存储的组织相关的数据。

## <a name="more-resources"></a>更多资源

Microsoft Teams 会议室安全：/microsoftteams/rooms/security Microsoft 隐私声明： https://aka.ms/privacyMicrosoft 的数据管理：https://www.microsoft.com/trust-center/privacy/data-management托管服务服务说明：[Microsoft Teams 会议室托管服务](microsoft-teams-rooms-premium.md)
