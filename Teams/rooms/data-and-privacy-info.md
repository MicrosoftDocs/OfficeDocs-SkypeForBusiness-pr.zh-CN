---
title: 数据和隐私信息
author: altsou
ms.author: altsou
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
ms.openlocfilehash: dd80718da862be02b42a5cf18334c89e86c3807c
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438423"
---
# <a name="approach"></a>方法

使用 Microsoft Teams 会议室 托管服务的客户将Microsoft委托为其最有价值的资产数据。 他们相信其隐私将受到保护，并且仅以符合其期望的方式使用。

该技术遵循隐私流程，以确保它遵守客户在有效运行服务时收集和使用数据的承诺。
## <a name="data-collection-and-privacy"></a>数据收集和隐私

 Microsoft Teams 会议室托管服务监视设备、收集客户内容数据，以及以管理员身份远程访问和管理设备。 收集的数据仅限于监视注册会议室中确定的运行状况、根本原因和缓解问题所需的信息。 收集的某些数据特定于会议室帐户，而不是单个用户。

> [!Note]
> 在使用设备期间，活动日志中可能会出现对单个用户的偶然引用。

## <a name="who-can-access-data"></a>谁可以访问数据

托管服务采取强有力的措施，帮助保护客户数据免受未经授权的人员不当访问或使用。 这些措施包括限制Microsoft人员和分包商的访问。

## <a name="zero-standing-access-data-storage"></a>零长期访问数据存储

托管服务通过零长期访问原则，缓解了与恶意参与者（包括组织内部和外部）具有特权访问的帐户相关的风险。 此原则使托管服务在默认情况下无需任何用户可用的特权即可运行。 结合实时和恰时访问的原则，它提供了一个可靠的框架，默认情况下是安全合规的。 诊断数据通过内部门户提供给Microsoft服务运营团队。

## <a name="data-handling"></a>数据处理

Microsoft受数据传输、存储、使用和保留的严格标准的约束。 Microsoft具有数据处理标准策略，这些策略根据数据分类来规范数据的处理方式。

## <a name="technology-description"></a>技术说明

托管服务将数据发送到 Microsoft，以便监视、诊断和缓解部署中的任何问题。 示例包括

- 确保设备是最新的 (包括应用、OS、驱动程序、F/W) 
- 确保设备已准备好使用 (登录、报告正常状态的所有外围设备等) 
- 确保环境准备就绪 (帐户预配、网络速度足够快等) 
- 确定是否存在硬件问题或安装问题 (，例如布线松动) 
- 用于确定问题 (过度重启等的启发式) 

托管服务通过以下操作管理设备：

- 更新软件
- 通过重新启动、重置 USB 连接&状态来缓解问题
- 收集特定日志以帮助诊断问题

托管服务不会监视或录制解决方案工具包中的音频、视频、媒体或会议内容。

### <a name="service-collected-data-categories"></a>服务收集的数据类别
 
|类别|详细信息|查询原因|
| :- | :- | :- |
|正在进行的数据收集和管理|IP 地址、会议室帐户的标识 (Exchange、Skype for Business和/或 Teams) 、位置坐标、门户中的电子邮件和Microsoft或软件通信|识别并连接到所管理的系统;识别、诊断和缓解故障;跟踪使用情况、分析和见解;查询和修复连接状态|
|临时数据收集和管理|事件日志信息、会议室用户登录日志文件中的用户活动/标识以及诊断信息、Windows 系统查询 (示例：USB 设备列表、电源状态等) |识别、诊断和缓解故障以及使用情况、分析和见解|

设备活动日志中的某些敏感数据在本地编修， (托管服务未收集) ：

- 会议主题和正文
- 会议与会者 (联系人卡片信息，例如职务、电话号码等) 
- 在会议 IM 消息内容中

> [!NOTE]
> 随着Microsoft托管服务的发展，特定数据可能会发生更改。

### <a name="enrollment"></a>注册

托管服务注册到联机门户，用于自动监视和支持服务，包括诊断和报告。 注册是通过使用设备的受信任平台模块加密的网络通信完成的， (TPM) 基于公钥。

### <a name="unenrollment"></a>取消注册

可以通过卸载托管服务来取消注册设备。 Microsoft还会在停用期间从后端监视中删除设备，并可以根据请求删除收集的数据。
## <a name="compliance"></a>合规性

所有从事产品工作的工程师都必须接受安全和隐私意识培训。 Microsoft还确保所有人员都证明他们接受隐私要求的责任。

托管服务通过欧洲 (欧盟) 、亚太地区 (亚太地区) 以及美国 (美国) 的数据中心提供区域数据驻留支持。 服务客户会将与组织相关的数据存储在其所选区域的数据中心。

## <a name="more-resources"></a>更多资源

有关 Windows 安全性的Microsoft Teams 会议室：[[Microsoft适用于 Windows 安全的 Teams](/microsoftteams/rooms/security-windows) \
有关 Android 安全性的Microsoft Teams 会议室：[Microsoft Android 安全性的 Teams](/microsoftteams/rooms/security-android) \
Microsoft隐私声明：https://aka.ms/privacy \
Microsoft 的数据管理：https://www.microsoft.com/trust-center/privacy/data-management \
托管服务服务说明：[Microsoft Teams 会议室托管服务](rooms-pro-management.md)
