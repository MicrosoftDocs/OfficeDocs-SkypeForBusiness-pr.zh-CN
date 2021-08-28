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
description: 了解如何将混合Exchange配置为与 Microsoft Teams一起使用，以确保同步组成员身份。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ef36b7bc50d21131dd10294566549bb8b642600
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632646"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>配置 Exchange 混合组织以配合使用 Microsoft Teams
======================================================================

通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。 但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。 这包括在 Azure AD 连接中启用组写回功能，以及各种初始化脚本：使用本地 Microsoft 365 混合 配置Exchange[组](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。