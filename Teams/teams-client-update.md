---
title: Teams 更新
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文介绍了更新 Microsoft Teams 桌面客户端的过程。
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0aa6a64b799f3d00262ab8a086d477bda482ac40
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784147"
---
# <a name="teams-update-process"></a>Teams 更新过程

Teams Web 应用更新通常在每月第 4 个星期一发布。

在通过我们的技术采用计划 (TAP) 进行严格的内部测试和验证后，Teams 桌面客户端更新每月发布一次。 桌面客户端更新通常从该月的第 4 个星期一开始，并在该周剩余时间内逐步向客户推出。 如果需要的是关键更新，Teams 将不采用此计划，而是在更新可用时立即发布。

The desktop client updates itself automatically. Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.

用户还可以手动下载更新，方法是在应用右上角“**个人资料**”图标旁边的“**...**”下拉菜单中选择“**检查更新**”。 如果更新可用，则将在计算机处于空闲状态时下载并以无提示方式安装更新。

用户需要登录才能下载更新。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版更新怎么样？

默认情况下，Teams 随新安装的 Microsoft 365 企业应用版一起安装，如[使用 Microsoft 365 企业应用版部署 Microsoft Teams](/DeployOffice/teams-install) 中所述。

Teams 遵循其自己的更新过程，如上所述。 Teams 不遵循其他 Office 应用（如 Word 和 Excel）的更新过程。 若要了解详细信息，请阅读 [Microsoft 365 应用版更新频道概述](/DeployOffice/overview-update-channels)。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理员能否部署更新而不是 Teams 自动更新？

Teams 不向管理员提供通过任何传递机制部署更新的功能。

## <a name="servicing-agreement"></a>服务协议

作为新式联机服务的一部分，Teams 客户端每月大约更新一次。 当更新可供该客户端使用时，客户端会自动安装更新。 由于我们错开了全球更新的可用性，因此组织中的某些客户端可能会先于其他客户端收到新的更新。 由于 Teams 受新式生命周期策略的约束，因此用户应使用桌面客户端的最新版本。 自动更新可确保用户具有最新功能、性能增强、安全性和服务可靠性。

为确定桌面客户端何时过期，如果用户的当前版本介于 1 到 3 个月之间，以及有新版本可用，则会显示应用内警报。 此应用内消息传送鼓励用户更新到最新版本的 Teams，或者在必要时联系 IT 管理员以执行此操作。 使用超过三个月的 Teams 桌面客户端的用户将看到阻止页面，该页面提供了立即更新、联系 IT 管理员或继续访问 Teams 网页版等选项。

政府云上的 Teams 桌面客户端目前对此服务协议有例外，请等待另行通知。

有关新版本发布的信息，请查看“[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)”或转到客户端中的“**帮助**” > “**新增功能**”。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的 Teams 更新怎么样？

虚拟桌面基础结构 (VDI) 上的 Teams 客户端不会像非 VDI Teams 客户端那样自动更新。 必须按照有关[在 VDI 上安装 Teams](teams-for-vdi.md) 的说明所述，通过安装新的 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。
