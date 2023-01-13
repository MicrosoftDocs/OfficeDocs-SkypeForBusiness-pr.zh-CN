---
title: Teams 会议的自定义会议背景
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: 使用批准的公司资产（如背景）为组织中的 Teams 会议创建自定义背景。
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800220"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Teams 会议的自定义会议背景

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>概述

Teams 会议中的自定义允许组织在整个会议体验中扩展其视觉标识。 使用自定义会议背景有助于促进内部公司文化建设，并提高内部和外部会议参与者的整体品牌认知度。 借助组织的品牌管理和公司通信团队，管理员可以轻松地为单个租户中的各种业务部门和部门设置和创建自定义会议背景。

默认情况下，作为管理员或已分配有会议自定义策略的 Teams 高级许可用户可以创建具有自定义会议背景的会议。 这些自定义背景将仅适用于组织中拥有Teams 高级版许可证的最终用户。

## <a name="prerequisites"></a>先决条件

在为 Teams 会议设置自定义会议背景之前，请检查以确保具有以下项：

- 访问Teams 高级版 SKU
- 你是有权访问 Teams 管理中心的管理员，或者你已获得自定义策略
- 你已启用 [自定义后台策略](#enabling-the-custom-background-policy)
- 背景图像符合 [所需的规范](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>设置自定义会议背景

管理员可以在 Teams 管理中心上传和管理 Teams 会议的自定义会议背景。

### <a name="enabling-the-custom-background-policy"></a>启用自定义后台策略

作为管理员，若要创建自定义背景，需要创建新的会议自定义策略或修改组织全局默认策略。
若要启用自定义后台策略，管理员将执行以下步骤：

1. 打开 Teams 管理中心
2. 从导航窗格中选择“ **会议** ”
3. 在“会议”下，可通过两种方式访问自定义后台策略。 可以选择“ **自定义策略** ”以选择现有策略或创建新策略。 或者，可以选择“ **会议策略** ”，然后选择右上角的“ **自定义会议图像** ”按钮。
4. 在所选策略中，导航到 **“自定义会议背景** ”部分
5. 将 **“自定义背景”** 设置从“关闭”切换为“打开”以启用设置
6. 选择“ **保存”**

### <a name="adding-custom-background-images"></a>添加自定义背景图像

启用自定义背景策略后，可以上传自定义背景图像。 这些图像将显示在最终用户的界面上，按上传时间排序。

上传必须遵循以下参数。 管理员可以上传：

- 其图像的 PNG 和 JPEG 图像格式
- 最小尺寸为 360 像素 X 360 像素的图像
- 最小尺寸为 3840 像素 X 2160 像素的图像
- 最多 50 个自定义背景图像

若要上传图像，请导航到 **“会议** > **自定义策略”** ，并从上一步中选择策略。 向下滚动到 **“自定义会议背景** ”部分，在具有自定义背景切换开关的表格下，选择“ **+添加**”。 选择“+添加”后，将打开一个名为 **“管理背景”的** 窗格，允许添加图像。

> [!NOTE]
> 只有拥有Teams 高级版许可证的最终用户才会在其“后台设置”面板中看到这些图像。

### <a name="saving-custom-background-images"></a>保存自定义背景图像

可以在 **“自定义会议背景** ”部分下的新表中找到已上传图像的预览。 此表还显示图像的名称和分辨率。 确认所选上传的图像后，选择预览表下方的“ **保存** ”按钮。 选择“保存”后，上传的背景对具有Teams 高级版许可证的最终用户可见。

## <a name="where-are-custom-backgrounds-visible"></a>自定义背景可见的位置

以下列表显示了自定义背景可见的受支持客户端：

- Web 客户端
- 桌面客户端
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>谁可以选择和应用自定义会议背景

只有Teams 高级版许可用户才能在其“后台设置”面板中使用会议背景。

> [!NOTE]
> 外部用户或匿名用户无法使用自定义会议背景。

### <a name="who-can-view-custom-meeting-backgrounds"></a>谁可以查看自定义会议背景

虽然只有许可的最终用户可以选择他们选择上传的背景，但任何人都可以查看应用于会议的背景。 这些用户包括：

- 租户内、Teams 高级版许可用户
- 租户内非许可用户
- 外部用户
- 匿名用户
