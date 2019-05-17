---
title: 配置 Exchange 混合组织以配合使用 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
description: 了解如何配置 Exchange 混合组织以配合使用 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3b41f0ae30fb0c21baab1f7e01b86e79300008e
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108633"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="73a32-103">配置 Exchange 混合组织以配合使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73a32-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="73a32-104">通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="73a32-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="73a32-105">但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。</span><span class="sxs-lookup"><span data-stu-id="73a32-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="73a32-106">此步骤需要在 Azure AD 连接以及各种初始化脚本组写回功能的启用：[配置 Office 365 组与本地 Exchange 混合部署](https://go.microsoft.com/fwlink/?linkid=854389)。</span><span class="sxs-lookup"><span data-stu-id="73a32-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
