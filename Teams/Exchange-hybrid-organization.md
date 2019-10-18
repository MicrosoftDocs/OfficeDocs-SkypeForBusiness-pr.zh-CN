---
title: 配置 Exchange 混合组织以配合使用 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 了解如何配置 Exchange 混合组织以配合使用 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd18381a8d889a1cebad04234e56bf11def9197e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563892"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>配置 Exchange 混合组织以配合使用 Microsoft Teams
======================================================================

通常，不必配置任何 Exchange Online 功能即可使用 Microsoft Teams。 但对于 Exchange 混合方案，为了确保在 Exchange Server（本地）与 Exchange Online 之间同步组成员身份，需要执行一些步骤。 这涉及在 Azure AD Connect 中启用组写回功能以及各种初始化脚本：[配置本地 Exchange 混合的 Office 365 组](https://go.microsoft.com/fwlink/?linkid=854389)。
