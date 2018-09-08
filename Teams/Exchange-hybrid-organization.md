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
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02d09e235872644355481f52be8764799ad32871
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881938"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>配置 Exchange 混合组织以配合使用 Microsoft Teams
======================================================================

通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。 但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。 这涉及在 Azure AD Connect 中启用组回写功能，以及执行各种初始化脚本：[为 Office 365 组配置本地 Exchange 混合](https://go.microsoft.com/fwlink/?linkid=854389)
