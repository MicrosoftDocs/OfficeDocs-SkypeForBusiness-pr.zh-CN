---
title: Microsoft Teams 实时事件使用情况报告
author: CarolynRowe
ms.author: crowe
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
description: 了解如何在 Microsoft Teams 管理中心使用 Teams 实时事件使用情况报告来获取组织中的 Teams 实时事件活动的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29a255c9248f07db00d4295e99d4062116ca4e76
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794090"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams 实时事件使用情况报告

Microsoft Teams 管理中心中的 Teams 实时事件使用情况报告显示组织中举行的实时事件的活动概述。 可以查看使用情况信息，包括每个事件的事件状态、开始时间、视图和生产类型。 你可以深入了解使用趋势，并查看组织中的谁计划、呈现和生成实时事件。

## <a name="view-the-live-event-usage-report"></a>查看实时事件使用情况报告

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“分析”&报告** > **使用情况报告**。 在 **“查看报表** ”选项卡上的 **“报** 表”下，选择 **Teams 实时事件使用情况**。
2. 在 **“日期”范围** 下，选择预定义的范围或设置自定义范围。 可以设置一个范围，以显示当前日期之前和之后长达一年、六个月的数据。
3.  (可选) 在 **“组织者**”下，可以选择仅显示由特定用户组织的实时活动。
4. 单击 **“运行”报表**。  

   :::image type="content" alt-text="Teams 管理中心中带有标注的 Teams 实时事件使用情况报告的屏幕截图。" source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 实时事件报告，了解过去 7 天、28 天或你设置的自定义日期范围的趋势。 |
|**2**   |每个报表都有生成日期。 刷新页面时，报表将反映近实时活动。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴是总视图计数。</li> </ul>将鼠标悬停在给定日期上的点上，以查看该日期的所有实时事件的视图数。|
|**4**   |该表提供每个实时事件的细目。 <ul><li>**事件** 是实时事件的显示名称。 单击事件名称可获取有关事件的 [更多详细信息](#view-event-details) 。 </li> <li>**开始时间** 是指事件的开始日期和时间。</li> <li>**事件状态** 显示事件是否已发生。  </li><li>**组织者** 是事件组织者的名称。</li> <li>**演示者** 是事件演示者的姓名。</li><li>**制作者** 是事件生成者的名称。</li><li>**视图** 是完成事件后的唯一视图数。</li><li>**录制** 显示录制设置是打开还是关闭。</li><li>**生产类型** 显示事件是在 Teams 中还是由外部应用程序或设备生成的。</li></li> </ul>请注意，如果 Azure AD 中不再存在用户帐户，则该用户名在表中显示为“--”。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。|

## <a name="notes"></a>注释
我们最多显示 100 个符合当前报表条件的实时事件。 若要查看更多实时事件，请应用日期筛选器来减小列表大小。

匿名演示者不会包含在报表中。

观看事件录制或按需事件的任何人都不会包括在视图计数中。 

## <a name="view-event-details"></a>查看事件详细信息

实时事件详细信息页提供实时事件的详细信息摘要，并列出与事件关联的所有文件，包括脚本和录音。 单击文件名以查看或下载文件。

:::image type="content" alt-text="显示实时事件详细信息的屏幕截图。" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

如果为组织启用 [了 Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 或 [Kollective](https://kollective.com) eCDN，则可以通过单击合作伙伴报表链接获取其他与会者分析。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
- [什么是 Teams 直播活动？](../teams-live-events/what-are-teams-live-events.md)
