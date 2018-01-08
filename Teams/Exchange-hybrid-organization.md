---
title: "配置 Exchange 混合组织以配合使用 Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何配置 Exchange 混合组织以配合使用 Microsoft Teams。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 95b891394584d457f16a25b86d24614883443f9f
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="55bd4-103">配置 Exchange 混合组织以配合使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55bd4-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="55bd4-104">通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="55bd4-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="55bd4-105">但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="55bd4-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="55bd4-106">这涉及在 Azure AD Connect 中启用组回写功能，以及执行各种初始化脚本：[为 Office 365 组配置本地 Exchange 混合](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="55bd4-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
