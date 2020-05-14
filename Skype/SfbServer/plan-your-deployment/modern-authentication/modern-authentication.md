---
title: 在 Skype for Business 中规划新式验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 为 Skype for business Server 的身份验证和授权规划主题，包括与其他产品的集成
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221576"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>讨论 Skype for Business 中的身份验证和授权

身份验证和授权是相关的概念，但为你执行不同的工作（尽管这两个都是必需的）。 放入简单术语中，authenciation （身份验证）仅依赖于机密用户知道或拥有的密码，并且可以是密码、代码、指纹、证书、声明的用户的声明的组合，或者这些内容在一起使用的组合。 身份验证是一种证明你是你所说的用户的过程。

授权（AuthZ）与你验证你的身份后可以访问的内容相关。 它确定允许查看、编辑或以其他方式访问的内容。 例如，您可能具有对 SharePoint Online 的功能强大的网站集管理员访问权限，但如果您切换到另一个联机工作负载（如 Skype for Business Online），则可能有权解决用户问题，而不会更改服务器的配置。 在第三个工作负载（例如 Exchange Online）中，可能只有一般用户的访问权限。 AuthZ 检查您对服务/worloads、应用程序、文件和其他数据的访问权限。

我们的示例涉及 SharePoint 和 Exchange online 等联机属性，但身份验证和 AuthZ 的过程在本地和混合部署中的工作方式相同。 最终，在身份验证和 AuthZ 情景中，像 AAD Connect 和 ADFS 这样的工具可以通过将本地帐户和密码同步到云的 AD （Azure AD）或在 AuthZ 流中 intruding，使用户不会经常收到其凭据，例如，在云中的工作负载中切换时，创建单一登录方案。 但它们本身不是负责的身份验证或 AuthZ，只是这一机制的一部分。

目前，许多技术认为这些过程（身份验证和 AuthZ）是一种机制，您会听到许多对身份验证过程的引用，这些过程也在其中包含授权。 请务必记住，用户访问中的第一步是身份验证，证明您是您所说的人，并且，AuthZ 使用用户的知识来确定他或她有权访问的内容（如您将在打开授权或 OAuth 时看到的用户）。

  
## <a name="authentication-and-authorization-planning-topics"></a>身份验证和授权规划主题

[如何将新式身份验证（ADAL）用于 Skype for Business](plan-adal.md)

[新式验证支持的 Skype for business 拓扑](topologies-supported.md)

[规划在内部和外部将旧版身份验证方法关闭到网络中。](turn-on-modern-auth.md)

