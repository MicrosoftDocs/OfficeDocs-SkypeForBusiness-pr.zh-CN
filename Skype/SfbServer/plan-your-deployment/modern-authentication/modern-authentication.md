---
title: 规划 Skype for Business 中的新式身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 适用于 Skype for Business 服务器的身份验证和授权的计划主题, 包括与其他产品的集成
ms.openlocfilehash: 922b53b26bd77be4f7d49e7c594d337f7961703d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297300"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>在 Skype for Business 中讨论身份验证和授权

身份验证和授权是相关的概念, 但为你执行不同的工作 (尽管这两者都是必需的)。 放入简单的术语中, authenciation (AuthN) 仅依赖于机密用户知道或拥有的有效用户, 并且可以是密码、代码、指纹、证书、声明有关用户的情况的组合, 或者结合使用这些内容。 AuthN 是一种证明你所说的人的过程。

授权 (AuthZ) 在您验证您的身份后, 与您有权访问的内容相关。 它确定您允许查看、编辑和以其他方式访问的内容。 例如, 你可能拥有 SharePoint Online 的功能强大的网站集管理员访问权限, 但是如果你切换到另一个联机工作负载 (如 Skype for Business Online), 你可能有权解决用户问题, 而不是更改配置服务器或服务器。 在第三个工作负荷 (如 Exchange Online) 中, 你可能只有一般用户的访问权限。 AuthZ 检查你对服务/worloads、应用程序、文件和其他数据的访问权限。

我们的示例涉及 SharePoint 和 Exchange online 等联机属性, 但 AuthN 和 AuthZ 的流程在本地以及在混合场所中均以相同的方式工作。 最终, 诸如 AAD Connect 和 ADFS 之类的工具通过将本地帐户和密码同步到云的广告 (即 Office 365 或 Azure 中的 Azure AD) 或在 AuthZ 流中 intruding, 在 AuthN 和 AuthZ 情景中参与。用户不会经常收到其凭据的提示, 例如, 当在云中的工作负载之间切换时, 创建单一登录方案。 但它们本身并不是责任的 AuthN 或 AuthZ, 只是这种机制的一部分。

如今, 许多技术将这些流程 (AuthN 和 AuthZ) 视为一种机制, 并且你将听到许多对身份验证过程的引用, 其中还包括授权。 请务必记住, 用户访问中的第一步是 AuthN, 证明你是你所说的人员, 并且该 AuthZ 使用用户的知识来确定他或她有权访问的内容 (如你将通过开放授权或 OAuth 看到的那样)。

  
## <a name="authentication-and-authorization-planning-topics"></a>身份验证和授权计划主题

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[计划在内部和外部关闭旧版身份验证方法。](turn-on-modern-auth.md)

