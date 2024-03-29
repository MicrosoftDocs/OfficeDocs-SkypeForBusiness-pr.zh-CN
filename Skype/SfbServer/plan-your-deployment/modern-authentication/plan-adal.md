---
title: 规划使用新式验证 (ADAL) ADAL Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 本文介绍基于 Active Directory 身份验证库 (ADAL (和 OAuth 2.0) 新式验证) 是什么。
ms.openlocfilehash: ca029b4a1f93f5e498df902587bb754247193ab4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404594"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何将新式验证与 (ADAL) 一Skype for Business
 
本文介绍基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0) 的新式验证 (，可以在 Skype for Business for Skype for Business Server 2015 的 2016 年 3 月累积更新中或 Skype for Business Server 的初始版本中找到这些验证库。 2019.
  
## <a name="what-is-adal"></a>什么是 ADAL？

ADAL 是"Active Directory 身份验证库"的缩写，与 OAuth 2.0 一起是新式验证的基础。 此代码库旨在向客户端应用程序（如通过安全令牌 (Skype for Business) 目录中的安全资源。 ADAL 与 OAuth 2.0 一起支持更多身份验证和授权方案，如多重身份验证 (MFA) 和多种形式的 SAML 身份验证。
  
各种充当客户端的应用可以利用新式验证来帮助获取安全资源。 在Skype for Business Server中，在本地客户端和内部部署服务器之间使用该技术，以便为用户提供对资源的适当级别的授权。
  
基于 ADAL (OAuth 2.0 的新式身份验证对话) 一些共同的元素。
  
- 有一个客户端请求资源，在这种情况下，客户端将Skype for Business。
    
- 有一个资源，客户端需要特定级别的访问权限，并且此资源受目录服务保护，在这种情况下，该资源Skype for Business Server。
    
- 有一个 OAuth 连接，即专用于授权用户访问资源的连接。  (OAuth 也称作更具描述性的名称"服务器到服务器"身份验证，通常缩写为 S2S.) 
    
在Skype for Business Server新式验证 (ADAL) 对话中，Skype for Business Server通过 Windows Server 2012 R2) 中的 ADFS (ADFS 3.0 进行通信。 身份验证可能会使用 IdP (的其他一) ，Skype for Business服务器需要配置为直接与 ADFS 通信。 如果尚未将 ADFS 配置为与 Skype for Business Server请完成 [ADFS 安装](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。
  
ADAL 包含在 Skype for Business Server 2015 的 2016 年 3 月累积更新中，并且必须安装 Skype for Business 的 2016 年 3 月累积更新，并且该更新是成功配置所需的。 对于 Skype for Business Server 2019，该产品从产品的初始版本开始提供。
  
> [!NOTE]
> 在初始版本中，只有当没有涉及混合拓扑时，才支持本地Skype新式验证。 例如，如果环境完全在Skype for Business Server。 此声明可能会更改。 
  
必须下载 PowerShell .ps1文件以及 ADAL 使用的命令进行成功配置。

若要了解如何在 Skype for Business 中实现新式验证，请参阅：如何将新式验证与 ([ADAL) 一Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)