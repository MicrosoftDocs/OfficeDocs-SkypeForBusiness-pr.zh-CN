---
title: 管理设备Teams运行状况
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文将指导你管理Teams设备、已安装Microsoft Teams设备的运行状况。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: fae26365a09cab2705d4c7fee5d57c2135203a65
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045808"
---
# <a name="manage-the-health-of-teams-devices"></a>管理设备Teams运行状况


管理员可以使用运行状况状态（指示问题的严重性）监视Microsoft Teams安装的设备运行状况。 若要检查设备的运行状况，可以转到管理中心"Teams **设备**"部分下的设备Teams列表。 此列表中的运行状况列指示设备的当前运行状况。 选择该状态会打开 **"运行状况"面板**，其中提供了有关运行状况问题的更多详细信息。

许多类型的问题都会导致设备运行状况，Teams管理中心系统会评估这些问题的严重性。

管理其Teams设备的管理员可能会决定其问题的严重性与系统提供的默认配置Teams相同。 管理员有一种方法可以自定义其设备运行状况的严重性和影响，以匹配其组织的优先级。

Teams 会议室设备附加了外围设备，可提供完整的会议体验，例如扬声器、麦克风、显示器、相机。 有关它们的详细信息，可在设备页面的"外围设备"和"运行状况"选项卡下查看。 这些外围设备的连接性会影响父设备的运行状况。

## <a name="feature-details"></a>功能详细信息

在设备页面上查看外围设备详细信息时，现在会看到"管理运行状况  **影响"** 选项。 此外，管理员还可以查看每个外围设备对设备运行状况的影响。

默认情况下，所有外围设备都设置为对 **设备运行状况** 有严重影响。 如果外围设备断开连接，父设备的运行状况将变为"严重"，此问题会显示在"运行状况"面板的"关键问题"下。

> [!NOTE]
> 外围类别 **HDMI ingest** 和 **Compute** 不可用于自定义，因为它们对父设备运行至关重要。

## <a name="how-does-this-work"></a>其工作方式如何？

1. 管理员可以选择要更改其运行状况影响的外围设备。 然后，他们可以选择"**管理运行状况影响"。** 或者，他们还可以在每个外围设备卡 **上的**"外围设备"选项卡下找到"管理运行状况影响"选项。
1. " **运行状况影响** "面板将打开，管理员可以为所选外围设备选择所需的影响级别并保存它。

| 设置选项 | 说明 |
|------------------|-------------|
| **非紧急** | 为外围设备类别设置 (如显示器或扬声器) 并且外围设备断开连接时，Teams 会议室 设备的运行状况状态将变为非紧急 (而不是严重) 。   新问题将在运行状况面板的" **非** 紧急"部分中进行分类。|
| **无影响** | 为外围设备类别设置并且外围设备断开连接时，Teams 会议室设备的运行状况状态将保持正常状态 (而不是) 。   此运行状况问题不会显示在运行状况面板中。|
| **严重** | 当为外围设备类别设置并且外围设备断开连接时，Teams 会议室设备的运行状况状态将变为"严重 **"。** 新的此类问题将在运行状况面板的 **"** 严重"部分中进行分类。|
| **重置为默认值** | 为外围设备类别设置时，该类别的运行状况影响将重置为"严重 **"。** 保存此选项后，将应用更改，运行状况影响将反映这些更改。|

## <a name="applicable-device-categories"></a>适用的设备类别

目前，此功能可用于管理与设备关联的外围设备的Microsoft Teams 会议室 (Windows) 影响。

## <a name="impact-on-other-workflows"></a>影响其他工作流

如果外围设备的运行状况影响严重性降低，则管理员可能不会注意到问题何时发生。 请注意需要密切监视的高优先级设备。

例如，如果警报的运行状况变为"严重"，则配置为为 ConfRoom1 **触发警报**。 管理员已减少该会议室的显示器和扬声器的运行状况影响，从默认的"严重"减少到"**非紧急"。** 现在，如果显示器断开连接，则 ConfRoom1 的运行状况将变为 **非紧急**。 在这种情况下，不会触发警报。
