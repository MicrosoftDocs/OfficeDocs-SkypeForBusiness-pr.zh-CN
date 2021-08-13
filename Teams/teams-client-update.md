---
title: Teams 更新
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文介绍了更新 Microsoft Teams 桌面客户端的过程。
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 96077e5b50dff12f29f6e1ccf903cd0f7de96352dacf0d8b3c2cc7406750737e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321134"
---
# <a name="teams-update-process"></a>Teams 更新过程

Teams Web 应用每周更新一次。

在通过我们的技术采用计划 (TAP) 进行严格的内部测试和验证后，Teams 桌面客户端更新每两周发布一次。 更新通常在星期二进行。 如果需要的是关键更新，Teams 将不采用此计划，而是在更新可用时立即发布。

桌面客户端会自动更新。Teams 每隔几个小时在后台检查更新，下载更新，然后等待计算机处于空闲状态，然后再无提示安装更新。

用户还可以通过在应用右上角的“**个人资料**”下拉菜单上选择“**检查更新**”手动下载更新。 如果更新可用，则将在计算机处于空闲状态时下载并以无提示方式安装更新。

用户需要登录才能下载更新。

从 2019 年 7 月 31 日开始，Teams 客户端更新在更新期间使用较低的网络带宽。 此更新默认处于打开状态，不需要管理员或用户执行任何操作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版更新怎么样？

默认情况下，Teams 随新安装的 Microsoft 365 企业应用版一起安装，如[使用 Microsoft 365 企业应用版部署 Microsoft Teams](/DeployOffice/teams-install) 中所述。

Teams 遵循其自己的更新过程，如上所述。 Teams 不遵循其他 Office 应用（如 Word 和 Excel）的更新过程。 若要了解详细信息，请阅读 [Microsoft 365 企业应用版更新频道概述](/DeployOffice/overview-of-update-channels-for-office-365-proplus)。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的 Teams 更新怎么样？


虚拟桌面基础结构 (VDI) 上的 Teams 客户端不会像非 VDI Teams 客户端那样自动更新。 必须按照有关[在 VDI 上安装 Teams](teams-for-vdi.md) 的说明所述，通过安装新的 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理员能否部署更新而不是 Teams 自动更新？

Teams 不向管理员提供通过任何传递机制部署更新的功能。

## <a name="servicing-agreement"></a>服务协议

作为新式在线服务，Teams 客户端每隔两周自动更新一次。 由于 Teams 受新式生命周期策略的约束，因此用户应使用桌面客户端的最新版本。 自动更新可确保用户具有最新功能、性能增强、安全性和服务可靠性。

为确定桌面客户端何时过期，如果用户的当前版本介于 1 到 3 个月之间，以及有新版本可用，则会显示应用内警报。 此应用内消息传送鼓励用户更新到最新版本的 Teams，或者在必要时联系 IT 管理员以执行此操作。 使用超过三个月的 Teams 桌面客户端的用户将看到阻止页面，该页面提供了立即更新、联系 IT 管理员或继续访问 Teams 网页版等选项。

政府云上的 Teams 桌面客户端目前对此服务协议有例外，请等待另行通知。

有关新版本发布的信息，请查看“[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)”或转到客户端中的“**帮助**” > “**新增功能**”。
