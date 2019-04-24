---
title: 规划现代身份验证 (ADAL) Skype for Business
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文说明什么是现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0）。
ms.openlocfilehash: 0c3aeef2480494e45a4d18589b3e3cdc6d9c5357
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213905"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证 (ADAL) 与 Skype for Business 配合使用
 
本文介绍现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的 Skype 业务服务器 2015，或从初始 Skype 的累积更新业务服务器 2019 Skype 的的发行版。
  
## <a name="what-is-adal"></a>什么是 ADAL？

ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。 此代码库旨在使您目录中的安全的资源 （如 for Business 的 Skype) 通过安全令牌的客户端应用程序。 ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。
  
充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。 Skype 业务服务器，在这种技术以便为用户提供适当级别的资源授权使用内部部署客户端和内部部署服务器之间。
  
新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。
  
- 客户端进行资源的请求，在这种情况下，客户端是 for Business 的 Skype。
    
- 没有向其客户端需要特定的访问级别的资源和此资源安全的目录服务，在这种情况下该资源是 Skype 业务服务器。
    
- OAuth 连接，换句话说，连接的专用于*授权*用户访问资源。 （OAuth 通过更具描述性的名称、 服务器到服务器身份验证，也称为和通常缩写为 S2S）
    
在业务服务器现代身份验证 (ADAL) 对话的 Skype，Skype 业务服务器通过 ADFS (在 Windows Server 2012 R2 ADFS 3.0) 进行通信。 可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。 如果尚未配置 ADFS 业务服务器处理 Skype 请完成[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。
  
ADAL 中包含年 3 月 2016年业务服务器 2015年的 Skype 的累积更新和年 3 月 2016年安装累积更新的业务**必须**Skype 和所需的成功配置。 对于业务服务器 2019年的 Skype，它是可从该产品的初始版本。
  
> [!NOTE]
> 在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。 例如，如果环境纯粹 Skype 业务服务器。 此陈述可能会发生更改。 
  
必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。

有关如何在 Skype for Business 中实现现代身份验证的信息，请参考：[如何使用现代身份验证 (ADAL) 与 Skype for Business](../../manage/authentication/use-adal.md)
