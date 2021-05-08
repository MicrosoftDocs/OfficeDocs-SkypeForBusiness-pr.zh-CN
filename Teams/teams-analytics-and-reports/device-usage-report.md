---
title: Microsoft Teams 设备使用情况报告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams 管理中心中的Microsoft Teams设备使用情况报告来查看组织中用户如何连接到 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478352"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 设备使用情况报告

Teams管理中心中的Microsoft Teams使用情况报告提供了用户如何连接到 Teams。 可以使用报表查看整个组织使用的设备，包括Teams移动设备使用的设备数。  

## <a name="view-the-device-usage-report"></a>查看设备使用情况报告

1. 在管理中心的左侧导航Microsoft Teams，单击 **"分析**"&  >  **报告使用情况报告"。** 在"**查看报表"** 选项卡上的"报表 **"** 下 **，Teams设备使用情况"。**
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![屏幕截图：Teams管理中心中的设备使用情况Teams标注](../media/teams-reports-device-usage-with-callouts.png "屏幕截图：Teams管理中心中的设备使用情况Teams标注")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看Teams使用情况报表，了解过去 7 天或 30 天的趋势。  |
|**2**   |每个报表都有一个生成报告的日期。 报告通常反映活动时间延迟 24 小时。 |
|**3**   |<ul><li>图表上的 X 轴表示用于 (Windows、Mac、Linux、iOS、Android **电话、Web**) 设备Teams。  </li><li>Y 轴表示所选时段内使用设备的用户数。</li> </ul>将鼠标悬停在表示设备的栏上，以查看使用该设备连接到 Teams。|
|**4**   |下表按用户提供了设备使用情况的细分。 <ul><li>**用户名** 是显示名称的用户名。 可以单击显示名称转到管理中心中的用户设置Microsoft Teams页面。 </li><li>**Windows** 在基于计算机的 Teams 桌面客户端中处于活动状态，则Windows选择。</li><li>**如果用户在 macOS** 计算机上在 Teams桌面客户端中处于活动状态，则选择 Mac。 </li> <li>**如果用户** 在 Linux 计算机上在 Teams桌面客户端中处于活动状态，则选择 Linux。 </li> <li>**如果用户在 iOS** 的移动客户端上处于活动状态，Teams iOS。</li><li>**如果用户在 Android** 的移动客户端上处于活动状态，Teams Android 手机。 <li><li>**如果用户** 在 Web 客户端上处于活动状态，则Teams Web。 <li>**"上次** 活动"是用户 (上次) UTC 时间Teams的日期。</li> </ul> 请注意，如果 Azure AD 中不再存在用户帐户，则用户名在表中显示为"--"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**6**   |可以将报表导出到 CSV 文件进行脱机分析。 单击 **"导出Excel"，** 然后在"下载"选项卡上，单击"下载"，在报表准备就绪后下载报表。 <br><br>![显示导出报表的"下载"选项卡的屏幕截图](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使设备使用情况Teams数据匿名，您必须是全局管理员。 这会在报表及其导出中隐藏显示名称、电子邮件和 AAD ID 等可识别信息。

1. 在Microsoft 365管理中心，转到"设置 Org设置"，在"服务" \> **选项卡** 下，选择"报表 **"。**
    
2. 选择 **"报告**"，然后选择"**显示匿名标识符"。** 此设置既应用于管理中心中的使用情况Microsoft 365，也适用于Teams中心。
  
3. 选择"**保存更改"。**

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
