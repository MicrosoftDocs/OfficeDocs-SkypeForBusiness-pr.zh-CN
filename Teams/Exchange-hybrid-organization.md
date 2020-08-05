---
title: 配置 Exchange 混合组织
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 了解如何配置与 Microsoft 团队配合使用的 Exchange 混合组织，以确保组成员身份同步。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551958"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="d8337-103">配置 Exchange 混合组织以配合使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8337-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="d8337-104">通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="d8337-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="d8337-105">但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="d8337-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="d8337-106">这涉及在 Azure AD Connect 中启用组写回功能以及各种初始化脚本：[配置包含本地 Exchange 混合的 Microsoft 365 组](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="d8337-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>
