---
title: Teams 可选连接体验
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: 本文简要介绍了 Microsoft Teams 中的可选连接体验。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396263"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Microsoft Teams 中的可选连接体验概述

如果你拥有工作或学校帐户，则组织的管理员可能已允许你在使用 Microsoft Teams 时使用一个或多个云端服务（也称为“**可选连接体验**”），如 GIPHY 和/或 URL 预览服务。 这些云端服务是可选服务。 你可以自行决定是否使用。 根据不同于 [Microsoft Online 服务条款](https://www.microsoft.com/licensing/product-licensing/products)的条款向你提供这些服务，如每个可选服务分别所述。 本文列出了我们的 Teams 云端服务。

如果管理员已让你在 Teams 中选择使用可选连接体验，可转到 Teams 中的 **设置** > **隐私**，选择是否要使用可选连接体验。

> [!NOTE]
> 如果你是管理员，可以授予或限制用户使用可选连接体验的能力。 为此，可使用 [Office 云策略服务](/deployoffice/overview-office-cloud-policy-service) 配置 *允许在 Office 中使用其他可选连接体验* 策略设置。 这是相同的策略设置，用于控制你的用户在 Microsoft 365企业应用版随附的 Office 应用（如 Word、Excel 和 PowerPoint）中是否可以使用可选的连接体验。

## <a name="giphy"></a>GIPHY

GIPHY 是一个可用于在 Teams 聊天中使用 GIF 的云端服务。 如果在 **Teams** > **GIF** > **搜索** 中，搜索词将发送到 GIPHY。 这些体验（如果你的管理员允许并且你已选择使用它们）将受 [GIPHY 隐私策略](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy)和[服务条款](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service)的约束。

:::image type="content" source="media/giphy-menu.png" alt-text="这是一个菜单，显示了 Giphy 选择按钮和可用于键入信息以检索一张或多张 Giphy 图像的文本框。":::

## <a name="url-preview-service"></a>URL 预览服务

URL 预览服务会自动生成预览片段并在用户发送 URL 字符串时将 URL 附加到该片段的下面。 此服务会在用户键入消息时向服务 URL 发出请求。 如果服务 URL 没有任何 schema.org 数据，它将向必应搜索发送请求，以获取生成预览代码片段所需的数据。 依赖必应的体验根据 [Microsoft 服务协议](https://www.microsoft.com/servicesagreement) 的条款获得许可，并由 [隐私声明](https://privacy.microsoft.com/privacystatement)涵盖。 使用这些服务时提供给 Microsoft Teams 的任何 URL 都可以发送到 Microsoft 必应。 必应组织不会将它们链接到你。

:::image type="content" source="media/url-preview.png" alt-text="显示文本框中的 Microsoft 主页 URL 预览示例的屏幕。":::

## <a name="teams-apps-link-previews"></a>Teams 应用链接预览

Teams 应用链接预览服务生成应用自适应卡片的预览片段，并在用户发送映射到 Teams 应用商店中的应用的 URL 字符串时将其附加到 URL 下。 此服务会在用户键入消息时向服务 URL 发出请求。

## <a name="teams-device-store-checkout"></a>Teams 设备存储签出  

Teams 设备存储位于 Teams 管理中心，它支持发现和购买 Teams 认证设备。 为了启用签出，Teams 设备存储使用 UnifiedCommunications.com 共享基本用户和公司信息，包括用户电子邮件地址、用户 GUID 和租户 GUID。 如果允许在 Office  策略设置 **中使用其他可选连接体验**，则此体验受服务条款和 UnifiedCommunications.com 隐私声明的约束。

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Teams 设备存储页面的一部分屏幕截图，其中包含由第三方公司 UnifiedCommunications.com 提供的签出选项，该公司支持从 Teams 管理中心购买设备。":::

若要了解有关 Teams 设备存储的详细信息，请查看： [在 Teams 设备存储中购买设备](devices/device-store.md)

## <a name="related-articles"></a>相关文章

- [Teams 策略控制概述](policy-control-overview.md)
- [隐私和 Microsoft Teams](teams-privacy.md)
- [Office 中的可选连接体验概述](/deployoffice/privacy/optional-connected-experiences)
- [Office 的必选服务数据](/deployoffice/privacy/required-service-data)
- [帐户隐私设置](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
