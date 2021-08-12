---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 早期版本提供了可扩展消息传递和状态协议 (XMPP) 网关，该网关可以部署为单独的服务器角色，以允许与 XMPP 部署联盟。 XMPP 功能在 2019 &不再Skype for Business Server弃用。 如果要继续使用 XMPP 功能，可在与旧版本 (Skype for Business Server 2015/ Lync Server 2013) 共存环境中使用。 XMPP 功能分两部分安装：作为在旧版边缘服务器上运行的 XMPP 代理和在旧版前端服务器上运行的 XMPP 网关。
ms.openlocfilehash: f1dc49a9f93d87bf2b253963cf0955594b337f9bd186c3034ac7780cb50ccddb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303426"
---
# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

早期版本提供了可扩展消息传递和状态协议 (XMPP) 网关，该网关可以部署为单独的服务器角色，以允许与 XMPP 部署联盟。 XMPP 功能不再可用，2019 年 10 月Skype for Business Server弃用。 如果要继续使用 XMPP 功能，可以在与旧版本 (Skype for Business Server 2015 或 Lync Server 2013) 共存环境中执行。 XMPP 功能分两部分安装：作为在旧版边缘服务器上运行的 XMPP 代理和在旧版前端服务器上运行的 XMPP 网关。 
  
从迁移的角度来看，希望使用 XMPP 功能的用户应保留在旧服务器中，不应移至 Skype for Business Server 2019 池，而是继续使用旧的 XMPP 网关。 只有在 2015 或 Lync Server 2013 Skype for Business Server XMPP 联盟伙伴时，才能这样做。 如果要继续使用 XMPP 功能，则不应将旧边缘Skype for Business Server迁移到 2019。 但是，可以将旧版边缘服务器与 XMPP (2019 边缘) 与 Skype for Business 共存。
  

    

