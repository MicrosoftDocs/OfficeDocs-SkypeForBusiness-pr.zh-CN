---
title: 团队更新
author: SerdarSoysal
ms.author: serdars
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
description: 在本文中，你将了解更新 Microsoft 团队桌面客户端背后的过程。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfe9a7b8878481ccdad3b1d390dc35923987e105
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583269"
---
# <a name="teams-update-process"></a>团队更新流程

每周更新团队 web 应用。

团队桌面客户端更新将在通过我们的技术采纳计划进行严格内部测试和验证（ (点击) ）后每隔两周发布。 这通常发生在星期二。 如果需要关键更新，团队将绕过此计划，并在更新推出后立即发布更新。

桌面客户端会自动更新。 团队会在后台每隔几小时检查一次更新，下载它，然后等待计算机处于空闲状态，然后再进行无提示安装更新。

用户还可以通过在应用的右上角的 "**配置文件**" 下拉菜单上单击 "**检查更新**"，手动下载更新。 如果有可用更新，则会在计算机空闲时下载并自动安装该更新。

用户需要登录才能下载更新。 

从2019年7月31日开始，团队客户端更新在更新期间使用显著降低网络带宽。 默认情况下，此项处于打开状态，不需要管理员或用户执行任何操作。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>对企业的 Microsoft 365 应用的更新有何更新？

默认情况下，团队与 microsoft 365 应用的新安装一起安装，如在[适用于企业的 microsoft 365 应用中部署 Microsoft 团队](https://docs.microsoft.com/DeployOffice/teams-install)中所述。 

团队关注其自己的更新过程（如上文所述），而不是其他分支应用（如 Word 和 Excel）的更新过程。 若要了解详细信息，请阅读适用[于企业的 Microsoft 365 应用的更新频道概述](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>对 VDI 的团队更新有何区别？

 (VDI) 的虚拟桌面基础结构上的团队客户端不会自动更新非 VDI 团队客户端的方式。 你必须通过安装新 MSI 来更新 VM 映像，如在[VDI 上安装团队](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)的说明中所述。 必须卸载当前版本才能更新到较新版本。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理员是否可以部署更新，而不是团队自动更新？

团队不会授予管理员通过任何交付机制部署更新的能力。

## <a name="servicing-agreement"></a>服务协议

作为现代联机服务，团队客户端每两周自动更新一次。 由于团队由新式生命周期策略管理，因此，预计用户仍可使用最新版本的桌面客户端。 这可确保用户具有最新的功能、性能增强、安全性和服务可靠性。

若要开始帮助确定桌面客户端何时过期，如果用户的当前版本介于1到3个月之间，并且有新版本可用，则会显示应用内警报。 此应用内消息鼓励用户更新到最新版本的团队，如有必要，可与 IT 管理员联系。 超过三个月的团队桌面客户端用户将看到一个阻止页面，该页面提供了立即更新、与 IT 管理员联系或继续使用 web 上的团队的选项。

首次安装和/或首次运行团队后的桌面客户端版本超过了3个月，则在遇到上述服务信息之前将有28天的宽限期。 在此期间，自动更新过程将更新团队客户端。 如果未更新，用户将看到应用内警报鼓励他们手动更新到最新版本的团队，如有必要，请与 IT 管理员联系。 这包括使用团队桌面客户端的用户作为适用于企业捆绑包的 Microsoft 365 应用的一部分。

团队桌面客户在政府群上的桌面客户当前对此服务协议有例外，直到进一步通知。

有关新版本版本的信息，请查看[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或转**到**  >  客户端中**的新增功能**。
