---
title: 规划 Skype for Business 中的新式身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 规划身份验证和授权的 Skype 业务服务器，包括与其他产品集成的主题
ms.openlocfilehash: 1a7f20fe10a757001fb3eb819371b81f24d6901e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907155"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>讨论身份验证和授权的 Skype for Business

身份验证和授权是相关的概念，但是 （虽然两者都是必需的） 为您执行不同的工作。 将简单地说，authenciation （身份验证） 取决于机密仅而有效的用户了解或具有，这可能需要密码、 代码、 指纹、 证书、 为 true，则有关用户声明的组合或结合使用这些操作组合。 身份验证是一个过程出证明要所说的人。

使用何种您具有访问权限后经过您的身份验证而言授权 （身份验证）。 确定什么已被允许您查看、 编辑和否则访问。 例如，您可以对 SharePoint Online 功能强大的网站集管理员访问，但如果切换到另一个联机工作负荷，如 Skype 业务 online，您可能必须解决用户问题，未更改的配置的权限服务器或服务器。 在第三个工作负荷，例如 Exchange Online 中，您可能只有平均用户的访问权限。 身份验证检查哪些和多少您对访问服务/worloads、 应用程序、 文件和其他数据。

我们的示例涉及联机属性像 SharePoint 和 Exchange online，但身份验证和身份验证流程工作内部部署和混合部署中相同的方式。 最终，工具就像 AAD 连接和 ADFS 成为涉及身份验证和身份验证的文字部分中的同步的本地帐户和密码到云的 AD （这是 Office 365 或 Azure 对于 Azure AD），或 intruding 流中的身份验证，以便的用户不频繁时提示输入凭据，说之间创建单一登录方案，云中的工作负荷切换。 但它们不是本身，负责身份验证或身份验证的机制只一部分。

如今，许多技术考虑 （身份验证和身份验证） 是一种机制，这些过程，您会听到对身份验证过程许多在其中还包含授权的引用。 非常重要记住用户访问的第一步是身份验证，证明了您的身份，或者使用用户是谁确定哪些他/她与具有访问权限 （您将看到与 Open Authorization 或 OAuth） 的知识。

  
## <a name="authentication-and-authorization-planning-topics"></a>身份验证和授权规划主题

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[关闭旧身份验证方法内部和外部到您的网络规划。](turn-on-modern-auth.md)

