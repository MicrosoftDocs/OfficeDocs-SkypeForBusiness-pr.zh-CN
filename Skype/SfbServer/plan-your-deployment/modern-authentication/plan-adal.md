---
title: 通过 Skype for Business 规划新式验证 (ADAL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍了什么新式身份验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0)。
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297293"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证 (ADAL) 与 Skype for Business 配合使用
 
本文介绍了新式验证 (基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0), 可在2016年3月累积更新中找到 skype for business Server 2015 的 skype for business 累积更新或初始验证发布 Skype for business Server 2019。
  
## <a name="what-is-adal"></a>什么是 ADAL？

ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。 此代码库旨在通过安全令牌使你的目录中的安全资源可供客户端应用程序 (如 Skype for Business) 使用。 ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。
  
充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。 在 Skype for Business 服务器中, 将在本地客户端和本地服务器之间使用此技术, 以便为用户提供适当级别的资源授权。
  
新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。
  
- 客户端正在请求资源, 在这种情况下, 客户端是 Skype for business。
    
- 客户端需要具有特定级别的访问权限的资源, 并且此资源由目录服务保护, 在这种情况下, 资源是 Skype for business 服务器。
    
- 有一个 OAuth 连接, 换言之, 即专用于*授权*用户访问资源的连接。 (OAuth 也可以通过更具描述性的名称 "服务器到服务器" 身份验证来识别, 并且通常缩写为 S2S。)
    
在 Skype for business Server 新式验证 (ADAL) 对话中, Skype for business 服务器通过 ADFS (在 Windows Server 2012 R2 中是 ADFS 3.0) 进行通信。 可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。 如果尚未配置 ADFS 使用 Skype for Business 服务器, 请完成[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。
  
ADAL 已包含在 skype for business Server 2015 的2016年3月累积更新中, 并且必须安装 2006 2016 年3月的 skype for business 累积更新, 并且需要成功配置。 对于 Skype for business Server 2019, 可从产品的初始版本获取。
  
> [!NOTE]
> 在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。 例如, 如果环境是纯 Skype for business 服务器。 此陈述可能会发生更改。 
  
必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。

有关如何在 Skype for Business 中实施新式身份验证的信息, 请参阅:[如何将新式身份验证 (ADAL) 用于 skype for](../../manage/authentication/use-adal.md) business
