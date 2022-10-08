---
title: Microsoft Teams 设备使用情况报告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 设备使用情况报告，了解组织中的用户如何连接到 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033800"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 设备使用情况报告

Microsoft Teams 管理中心的 Teams 设备使用情况报告提供有关用户如何连接到 Teams 的信息。 可以使用报表查看整个组织使用的设备，包括在外出时从其移动设备使用 Teams 的设备数量。  

## <a name="view-the-device-usage-report"></a>查看设备使用情况报告


必须是全局管理员、全局读者或 Teams 服务管理员才能在 Teams 管理中心查看报表。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。


1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报表**”下，选择 **Teams 设备使用情况**。
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![Teams 管理中心中带有标注的 Teams 设备使用情况报告的屏幕截图。](../media/teams-reports-device-usage-with-callouts.png "Teams 管理中心中带有标注的 Teams 设备使用情况报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 设备使用情况报告，了解过去 7 天、30 天、90 天和 180 天的趋势。  |
|**2**   |每个报表都有生成报表的日期。 报表通常反映活动时间的 24-48 小时延迟。 |
|**3**   |<ul><li>图表上的 X 轴表示用于连接到 Teams 的 **Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android Phone**、 **Web**)  (不同设备。 </li><li>Y 轴是所选时间段内使用设备的用户数。</li> </ul>将鼠标悬停在表示设备的栏上，查看使用设备连接到 Teams 的用户数。|
|**4**   |该表按用户提供设备使用情况的细目。 <ul><li>**用户名** 是用户的显示名称。 可以单击显示名称，转到 Microsoft Teams 管理中心的用户设置页面。 </li><li>如果用户在基于 Windows 的计算机上的 Teams 桌面客户端中处于活动状态，则选择 **Windows**。</li><li>如果用户在 macOS 计算机上的 Teams 桌面客户端中处于活动状态，则会选择 **Mac**。 </li> <li>如果用户在 Linux 计算机上的 Teams 桌面客户端中处于活动状态，则选择 **Linux**。 </li> <li>如果用户在适用于 iOS 的 Teams 移动客户端上处于活动状态，则会选择 **iOS**。</li><li>如果用户在适用于 Android 的 Teams 移动客户端上处于活动状态，则选择 **Android 手机**。</li><li>如果用户在 ChromeOS 计算机上的 Teams 桌面客户端中处于活动状态，则选择 **Chrome OS**。</li><li>如果用户在 Teams Web 客户端上处于活动状态，则选择 **Web**。 <li>**最后一个活动** 是用户参与 Teams 活动的最后一个日期 (UTC) 。</li> </ul> 请注意，如果 Azure AD 中不再存在用户帐户，则该用户名在表中显示为“--”。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |将报表导出到 CSV 文件以进行脱机分析。 选择 **“导出到 Excel”** 图标，报表将在浏览器中下载。|
|**7** |顶部图中表示的时序数据显示为整个租户聚合的不同使用指标|
|**8** |botton 半部分中表示的表格数据显示每个用户聚合的不同使用指标|


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使 Teams 用户活动报告中的数据匿名，必须是全局管理员。 全局管理员可以使用 MD5 哈希 (隐藏可识别信息) ，例如报表中的显示名称、组名称、电子邮件和 AAD ID 及其导出。

1. 在Microsoft 365 管理中心中，转到 **“设置** \> **组织设置”**，然后在 **“服务”** 选项卡下选择 **“报表**”。
    
2. 选择 **“报** 表”，然后在 **所有报表中选择“显示隐藏的用户、组和网站名称**”。 此设置同时应用于Microsoft 365 管理中心和 Teams 管理中心的使用情况报告。
  
3. 选择 **“保存更改**”。

> [!NOTE]
> 启用此设置将取消识别 [Teams 用户活动报表](user-activity-report.md)、 [Teams 设备使用情况报告](device-usage-report.md)和 [Teams 使用情况报](teams-usage-report.md)表中的用户、组和站点名称信息。 从 2021 年 9 月 1 日开始，默认情况下，我们为每个人启用此设置，作为我们持续承诺的一部分，以帮助保护重要信息并使公司能够支持其本地隐私法。 
>
>此设置也适用于 Microsoft 365 管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用情况报告。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
