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
description: 本文介绍更新 Microsoft Teams 桌面客户端的过程。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119241"
---
# <a name="teams-update-process"></a>Teams 更新过程

Teams Web 应用每周更新一次。

通过 TAP 技术采用计划进行严格的内部测试和验证后，Teams 桌面客户端更新每两周发布 (一) 。 更新通常在星期二进行。 如果需要关键更新，Teams 将绕过此计划，在更新可用时立即发布。

桌面客户端会自动更新自身。 Teams 每隔几小时在后台检查更新，下载更新，然后等待计算机处于空闲状态，然后以无提示方式安装更新。

用户还可通过在应用右上方的"配置文件"下拉菜单上选择"检查更新"来手动下载更新。 如果有可用的更新，则当计算机空闲时，将下载更新并静默安装。

用户需要登录，以便下载更新。

从 2019 年 7 月 31 日开始，Teams 客户端更新在更新期间使用较低的网络带宽。 此更新默认打开，不需要管理员或用户执行任何操作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>适用于企业的 Microsoft 365 应用更新怎么样？

Teams 默认安装有新安装的 Microsoft 365 企业版应用，如使用 [适用于企业的 Microsoft 365](/DeployOffice/teams-install)应用部署 Microsoft Teams 中所述。

团队遵循其更新过程，如上所述。 Teams 不遵循其他办公室应用（如 Word 和 Excel）的更新过程。 有关详细信息，请阅读适用于企业的 [Microsoft 365 应用更新频道概述](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上的 Teams 更新怎么样？


虚拟桌面基础结构 (VDI) 上的 Teams 客户端不会以非 VDI Teams 客户端的方式自动更新。 必须按照在 VDI 上安装 Teams 的说明中的说明，通过安装新的 MSI [来更新 VM 映像](teams-for-vdi.md)。 必须卸载当前版本，以更新到较新版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理员能否部署更新而不是 Teams 自动更新？

Teams 不会向管理员提供通过任何传送机制部署更新的能力。

## <a name="servicing-agreement"></a>服务协议

作为新式联机服务，Teams 客户端每两周自动更新一次。 由于 Teams 受新式生命周期策略约束，因此用户应保持使用桌面客户端的最新版本。 自动更新可确保用户具有最新功能、性能增强功能、安全性和服务可靠性。

若要确定桌面客户端何时过期，如果用户的当前版本为 1 个月到 3 个月，并且是否有可用的新版本，则会显示应用内警报。 此应用内消息传送鼓励用户更新到最新版本的 Teams，或者在必要时与 IT 管理员联系以这样做。 超过三个月的 Teams 桌面客户端上的用户将看到阻止页面，该页面提供选项用于现在更新、联系 IT 管理员或继续访问 Teams 网页版。

首次安装和/或首次运行 Teams 时超过三个月的桌面客户端版本在遇到上述服务信息之前有 28 天的宽限期。 在此期间，自动更新过程将更新 Teams 客户端。 如果未更新，用户将看到一个应用内警报，鼓励他们手动更新到最新版本的 Teams。 系统可能会提示用户联系其 IT 管理员以执行更新。 这包括使用 Teams 桌面客户端作为 Microsoft 365 企业版应用捆绑包的一部分的用户。

在进一步通知之前，政府云上的 Teams 桌面客户端当前对本服务协议有例外。

有关新版本的信息，请查看消息 [中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或转到帮助  >  **客户端** 中的新增功能。
