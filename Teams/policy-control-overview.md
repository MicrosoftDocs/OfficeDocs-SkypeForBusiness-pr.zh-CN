---
title: Microsoft Teams 的策略控制概述
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 的策略控制概述。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135991"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Microsoft Teams 的策略控制概述

Microsoft 致力于为你提供所需的信息和控件，可让你在使用作为 Microsoft 365 一部分的 Microsoft Teams 时选择收集和使用数据的方式。

本文旨在向你提供有关以下区域的隐私控制信息：

- 所收集并向 Microsoft 发送的**诊断数据**，这些数据与在组织内运行 Windows 的计算机上使用的 Teams 和 Office 软件相关。
- **连接体验**，它使用基于云的功能为你和用户提供增强的 Teams 和 Office 功能。

作为这些更改的一部分，我们将提供全新和更新的用户界面 (UI) 元素和策略设置

> [!IMPORTANT]
> 有关进一步阅读，请查看 M365 的“[策略控制概述](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls)”内容。

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>从 Microsoft 365 企业应用版发送到 Microsoft 的诊断数据

诊断数据用于：

- 使 Teams 保持安全和最新状态。
- 检测、诊断和资政问题。
- 做出产品改进。

某些收集数据的示例包括：

- 应用程序语言
- 用户类型
- 操作系统的内部版本

## <a name="clients-that-adhere-to-diagnostic-controls"></a>遵循诊断控制的客户端

以下遵循诊断控制的客户端将提交数据：

- iOS
- Android
- 桌面（仅使用 win32 API 的组件）

有关所需移动数据诊断的信息，请参阅“[移动设备的策略控制诊断数据](policy-control-diagnostic-data-mobile.md)”。

有关所需桌面数据诊断的信息，请参阅“[台式机的策略控制诊断数据](policy-control-diagnostic-data-desktop.md)”。

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>从 Teams 应用发送到 Microsoft 的诊断数据

该诊断数据将会收集并发送给 Microsoft，这些数据与在组织内运行 Windows 的计算机上使用的 Teams 软件相关。

Teams 软件有三个级别的诊断数据可供你选择：

- **必需** 有助于让 Office 保持安全和最新并在安装设备上按预期运行所需的最少数据。
- **可选** 有助于我们改进产品并提供增强的信息来帮助检测、诊断和修复问题的附加数据。
- **两者都不** 不收集有关在用户设备上运行的 Teams 软件的诊断数据，并且不向我们发送该数据。 但是，此选项将严重限制我们对用户在使用 Teams 时可能遇到的问题进行检测、诊断和修复的能力。

例如，必需的诊断数据可能包括有关设备上安装的 Teams 客户端版本的信息，或者包含用于指示 Teams 应用程序在尝试加入会议时崩溃的信息。 可选的诊断数据可能包括有关启动通话所用时间的信息，它可能会指明与连接或网络性能有关的问题。

如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。

作为组织的管理员，你能够使用策略设置来选择要向我们发送哪种级别的诊断数据。 除非你更改设置，否则将向 Microsoft 发送可选诊断数据。 通过提供可选诊断数据，Microsoft 的 Office 工程团队可以更好地检测、诊断和缓解问题，从而降低对组织的影响。

如果用户使用其组织凭据（有时称为工作或学校帐户）登录 Teams，则他们将无法更改其设备的诊断数据级别。

此诊断数据不包括用户的姓名、电子邮件地址或 Office 文件的内容。 我们的系统会创建一个与用户诊断数据相关联的唯一 ID。 当我们收到显示 Teams 应用崩溃 100 次的诊断数据时，此唯一 ID 可让我们确定是单个用户崩溃了 100 次，还是 100 个不同的用户分别崩溃了一次。 我们不会使用此唯一 ID 来标识特定用户。

## <a name="required-service-data-for-connected-experiences"></a>连接体验的所需服务数据

必需服务数据是一种数据，它使我们能够提供这些基于云的连接体验并让这些体验保持安全并按预期运行。 必需服务数据包含三种类型的信息。

- **客户内容**，这是你使用 Office 创建的内容，例如在 Word 文档中键入的文本。
- **功能数据**，包括连接体验执行其任务所需的信息，例如有关应用的配置信息。
- **服务诊断数据**，它是让服务保持安全和最新并按预期运行所需的数据。 由于此数据与连接体验严格相关，因此它与必需或可选的诊断数据级别分开。

可选择不向用户提供此功能，在这种情况下，不会向 Microsoft 提供此信息以支持连接体验的功能。 可了解有关[所需服务数据](https://docs.microsoft.com/deployoffice/privacy/required-service-data)的详细信息。

## <a name="essential-services-for-microsoft-teams"></a>Microsoft Teams 的基本服务

还有一组服务对于 Microsoft 365 企业应用版的工作方式至关重要，用户无法禁用该服务。 例如，用于确认你已获得使用 Microsoft 365 企业应用版的正确许可的许可服务。 无论你配置了何种其他策略设置，都会收集有关这些服务的必需服务数据并将其发送给 Microsoft。

有关详细信息，请参阅 “[Office 的基本服务](https://docs.microsoft.com/deployoffice/privacy/essential-services)”。