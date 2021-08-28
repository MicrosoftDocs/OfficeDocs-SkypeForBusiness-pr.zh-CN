---
title: 规划新式验证Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 有关身份验证和授权 for Skype for Business Server的规划主题，包括与其他产品的集成
ms.openlocfilehash: a0d9e8dff4a08c670ce2af0b6eb9399146cef006
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632676"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>讨论身份验证和授权Skype for Business

身份验证和授权是相关概念，但需要执行不同的 (尽管这两种操作) 。 简单地说，身份验证 (AuthN) 仅依赖于有效用户知道或拥有的密码，它可以是密码、代码、指纹、证书、有关真正用户声明的组合，或结合使用这些功能。 AuthN 是一个证明您说出您是谁的过程。

授权 (AuthZ) 在证明你是谁后，你有权访问哪些项目。 它确定允许查看、编辑或以其他方式访问哪些内容。 例如，您可能具有对 SharePoint Online 的强大网站集管理员访问权限，但如果切换到其他联机工作负载（如 Skype for Business Online），您可能有权解决用户问题，而不是更改服务器的配置。 第三个工作负荷（Exchange Online）可能只有平均用户的访问权限。 AuthZ 检查对服务/worloads、应用程序、文件和其他数据具有的访问量和访问权限。

我们的示例涉及联机属性SharePoint和 Exchange Online，但 AuthN 和 AuthZ 的过程在本地和混合部署中以相同方式工作。 最后，将本地帐户和密码同步到云的 AD (即 Azure AD) 中，或者为了不经常提示用户输入凭据（例如，在云中的工作负载之间切换、创建单一 Sign-On 方案）而将 AAD 连接 和 ADFS 等工具纳入 AuthN 和 AuthZ 情景中。 但它们本身不是负责的 AuthN 或 AuthZ，而只是机制的一部分。

如今，许多技术认为这些 (AuthN 和 AuthZ) 是一种机制，并且你将听到许多对身份验证过程的引用，其中也包含授权。 切记，用户访问的第一步是 AuthN，证明你是说自己是谁，并且 AuthZ 使用用户是谁的知识来确定他/她有权访问 (，就像使用 Open Authorization 或 OAuth) 一样。

  
## <a name="authentication-and-authorization-planning-topics"></a>身份验证和授权规划主题

[如何将新式验证与 (ADAL) 一Skype for Business](plan-adal.md)

[新式验证支持的 Skype for Business 拓扑](topologies-supported.md)

[计划在网络内部和外部关闭旧式身份验证方法。](turn-on-modern-auth.md)

