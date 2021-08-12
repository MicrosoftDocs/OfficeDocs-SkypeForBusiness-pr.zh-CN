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
description: 了解如何配置一个Exchange组织，用于Microsoft Teams组成员身份同步。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284472"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>配置 Exchange 混合组织以配合使用 Microsoft Teams
======================================================================

通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。 但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。 这包括在 Azure AD 连接中启用组写回功能以及各种初始化脚本：使用本地 Microsoft 365 混合[配置Exchange组](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。