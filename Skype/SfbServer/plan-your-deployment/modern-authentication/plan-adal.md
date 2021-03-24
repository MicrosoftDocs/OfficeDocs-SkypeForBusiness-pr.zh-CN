---
title: 规划使用 Skype for Business (ADAL) 新式验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文介绍基于 Active Directory 身份验证库 (ADAL (和 OAuth 2.0) 新式验证) 是什么。
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096608"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何使用 Skype for Business (ADAL) 新式验证
 
本文介绍了基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0) 的新式验证 (，可在 Skype for Business for Skype for Business Server 2015 的 2016 年 3 月累积更新或 Skype for Business Server 2019 的初始版本中找到。
  
## <a name="what-is-adal"></a>什么是 ADAL？

ADAL 是"Active Directory 身份验证库"的缩写，与 OAuth 2.0 一起是新式验证的基础。 此代码库旨在向客户端应用程序（如 Skype for Business (通过安全令牌) 目录中的安全资源。 ADAL 与 OAuth 2.0 一起支持更多身份验证和授权方案，如多重身份验证 (MFA) 以及更多形式的 SAML 身份验证。
  
各种充当客户端的应用可以利用新式验证来帮助获取安全资源。 在 Skype for Business Server 中，此技术在本地客户端和本地服务器之间使用，以便为用户提供适当级别的资源授权。
  
基于 ADAL (OAuth 2.0 的新式身份验证对话) 一些共同的元素。
  
- 有一个客户端请求资源，在这种情况下，客户端是 Skype for Business。
    
- 有一个资源，客户端需要特定级别的访问权限，此资源受目录服务保护，在这种情况下，资源是 Skype for Business Server。
    
- 有一个 OAuth 连接，即专用于授权用户访问资源的连接。   (OAuth 也称作更具描述性的名称"服务器到服务器"身份验证，通常缩写为 S2S.) 
    
在 Skype for Business Server 新式验证 (ADAL) 对话中，Skype for Business Server 通过 Windows Server 2012 R2 (ADFS 3.0 中的 ADFS) 通信。 身份验证可能会使用 IdP (的其他一) ，但 Skype for Business 服务器需要配置为直接与 ADFS 通信。 如果你尚未将 ADFS 配置为与 Skype for Business Server 一起运行，请完成 [ADFS 安装](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。
  
ADAL 包含在 Skype for Business Server 2015 的 2016 年 3 月累积更新中，并且必须安装 Skype for **Business** 的 2016 年 3 月累积更新，并且该更新是成功配置所需的。 对于 Skype for Business Server 2019，它可从产品的初始版本提供。
  
> [!NOTE]
> 在初始版本中，只有在未涉及混合 Skype 拓扑时，才支持内部部署环境中的现代身份验证。 例如，如果环境完全为 Skype for Business Server。 此声明可能会更改。 
  
必须下载 PowerShell 程序包（包括 .ps1 文件以及 ADAL 使用的命令）以成功配置。

若要了解如何在 Skype for Business 中实现新式验证，请参阅：如何将新式验证 ([ADAL](/microsoft-365/enterprise/hybrid-modern-auth-overview)) Skype for Business