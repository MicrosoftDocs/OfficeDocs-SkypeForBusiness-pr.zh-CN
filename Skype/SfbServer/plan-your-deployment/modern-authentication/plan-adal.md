---
title: 使用 Skype for Business 规划新式验证（ADAL）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍了什么新式身份验证（基于 Active Directory 身份验证库（ADAL）和 OAuth 2.0）。
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046285"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式身份验证（ADAL）用于 Skype for Business
 
本文介绍了新式身份验证（基于 Active Directory 身份验证库（ADAL）和 OAuth 2.0），可在2006年3月2016累积更新中找到 skype for business Server 2015 或初始发布 Skype for business Server 2019。
  
## <a name="what-is-adal"></a>什么是 ADAL？

ADAL 是 "Active Directory 身份验证库" 的首字母缩写词，以及 OAuth 2.0，它是新式身份验证的基础。 此代码库旨在通过安全令牌将目录中的受保护资源提供给客户端应用程序（如 Skype for Business）。 ADAL 与 OAuth 2.0 结合使用，以启用更多身份验证和授权方案，如多重身份验证（MFA）和更多形式的 SAML Auth。
  
充当客户端的各种应用可以利用新式验证来帮助获取受保护的资源。 在 Skype for Business Server 中，在本地客户端和本地服务器之间使用此技术，以便为用户提供对资源的适当级别的授权。
  
新式身份验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。
  
- 有一个客户端发出对资源的请求，在这种情况下，客户端是 Skype for Business。
    
- 有一个资源，客户端需要特定级别的访问权限，并且该资源由目录服务保护，在这种情况下，该资源是 Skype for Business Server。
    
- 有一个 OAuth 连接，也就是说，专用于*授权*用户访问资源的连接。 （也可以使用更具描述性的名称 "服务器到服务器" 身份验证，并且通常缩写为 S2S。）
    
在 Skype for Business Server 新式验证（ADAL）对话中，Skype for Business Server 通过 ADFS （在 Windows Server 2012 R2 中为 ADFS 3.0）进行通信。 使用其他一些标识提供程序（IdP）可能会发生身份验证，但需要将 Skype for Business 服务器配置为直接与 ADFS 通信。 如果尚未将 ADFS 配置为与 Skype for Business Server 一起使用，请完成[ADFS 安装](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。
  
ADAL 包含在 Skype for business Server 2015 的2016年3月累积更新中，**必须**安装 skype for Business 的3月2016累积更新，才能成功配置。 对于 Skype for business Server 2019，可从产品的初始版本获取。
  
> [!NOTE]
> 在初始发布过程中，仅当没有涉及的混合 Skype 拓扑时，才支持在本地环境中进行新式身份验证。 例如，如果环境是纯 Skype for Business Server。 本声明可能会发生变化。 
  
必须下载包含. ps1 文件的 PowerShell 包，其中包含由 ADAL 使用的命令，才能成功配置。

若要了解如何在 Skype for Business 中实施新式验证，请参阅以下内容：[如何将新式身份验证（ADAL）用于 skype for](../../manage/authentication/use-adal.md) business
