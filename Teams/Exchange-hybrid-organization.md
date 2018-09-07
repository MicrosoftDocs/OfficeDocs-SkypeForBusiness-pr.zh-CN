---
title: 配置 Exchange 混合组织以配合使用 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: 了解如何配置 Exchange 混合组织以配合使用 Microsoft Teams。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 046b7ab0381391b16a306d36322086882c03f18a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849816"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="3b233-103">配置 Exchange 混合组织以配合使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b233-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="3b233-104">通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="3b233-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="3b233-105">但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="3b233-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="3b233-106">这涉及在 Azure AD Connect 中启用组回写功能，以及执行各种初始化脚本：[为 Office 365 组配置本地 Exchange 混合](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="3b233-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
