---
title: Microsoft Teams实时事件使用情况报告
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: 了解如何使用 Microsoft Teams 管理中心Teams实时事件使用情况报告，Teams组织中实时事件活动的概述。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2b9d4a9f60b905e03ee27397e24feb74ac3c17
ms.sourcegitcommit: b3b295557d494f77a7ebd9f49ec55f2507da956c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2021
ms.locfileid: "61135225"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams实时事件使用情况报告

Teams管理中心中的实时Microsoft Teams报表显示组织中举行实时事件的活动概述。 可以查看使用情况信息，包括每个事件的事件状态、开始时间、视图和生产类型。 你可以深入了解使用趋势，并查看组织中谁安排、展示和制作实时事件。

## <a name="view-the-live-event-usage-report"></a>查看实时事件使用情况报告

1. 在管理中心的左侧导航Microsoft Teams，单击 **"分析&报告**  >  **"。** 在"**查看报表"** 选项卡上的"报表 **"** 下，Teams **实时事件使用情况"。**
2. 在 **"日期范围**"下，选择预定义区域或设置自定义范围。 您可以设置一个范围以显示一年的数据，即当前日期之前和之后六个月。
3.  (") "下，您可以选择只显示由特定用户组织的实时事件。
4. 单击"**运行报表"。**  

   :::image type="content" alt-text="屏幕截图：Teams管理中心内具有标注Teams实时事件使用情况报表。" source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看Teams事件报告，了解过去 7 天、28 天或设置的自定义日期范围的趋势。 |
|**2**   |每个报表都有一个生成日期。 刷新页面时，报表反映近实时活动。 |
|**3**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴是总视图计数。</li> </ul>将鼠标悬停在给定日期的点上，以查看该日期所有实时事件的视图数。|
|**4**   |下表提供了每个实时事件的细分。 <ul><li>**事件** 是显示名称事件的事件。 单击事件名称 [，获取有关事件的](#view-event-details) 更多详细信息。 </li> <li>**开始时间** 是指事件的开始日期和时间。</li> <li>**事件** 状态显示事件是否已发生。  </li><li>**组织者** 是活动组织者的名称。</li> <li>**演示** 者是事件演示者的名称。</li><li>**生成** 者是事件生成者的名称。</li><li>**视图** 是事件完成后的唯一视图数。</li><li>**录制** 显示录制设置是打开还是关闭。</li><li>**"生产** 类型"显示事件是在 Teams还是由外部应用程序或设备生成。</li></li> </ul>请注意，如果用户帐户不再存在于Azure AD，则用户名在表中显示为"--"。 <br><br>要查看希望在表格中显示的信息，请确保向表格添加了相关列。 |
|**5**   |选择“**编辑列**”可在表格中添加或删除列。|

## <a name="notes"></a>注释
我们最多显示 100 个与当前报告条件匹配的实时事件。 若要查看更多实时事件，请应用日期筛选器来减小列表大小。

报告中不包括匿名演示者。

观看事件或按需事件录制的任何人都不会包括在视图计数中。 

## <a name="view-event-details"></a>查看事件详细信息

实时事件详细信息页提供实时事件详细信息的摘要，并列出与事件关联的所有文件，包括脚本和录制。 单击文件名以查看或下载文件。

:::image type="content" alt-text="显示实时事件详细信息的屏幕截图。" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

如果您的组织已启用 [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 或 [Kollective](https://kollective.com) eCDN，您可以通过单击合作伙伴报告链接获取其他与会者分析。

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
- [什么是 Teams 直播活动？](../teams-live-events/what-are-teams-live-events.md)
