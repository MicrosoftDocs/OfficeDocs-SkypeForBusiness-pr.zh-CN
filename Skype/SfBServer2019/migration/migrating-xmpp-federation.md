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
description: 以前的版本提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。 XMPP 功能不再可用 & 在 Skype for business Server 2019 中已弃用。 如果要继续使用 XMPP 功能，可以使用旧版版本（Skype for Business Server 2015/Lync Server 2013）在 coexitence 环境中 availed。 XMPP 功能安装在两个部分中：作为运行在旧版边缘服务器上的 XMPP 代理，以及在旧版前端服务器上运行的 XMPP 网关。
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752644"
---
# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

以前的版本提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。 XMPP 功能不再可用，在 Skype for Business Server 2019 中已弃用。 如果要继续使用 XMPP 功能，可以在具有旧版版本（Skype for Business Server 2015 或 Lync Server 2013）的共存环境中执行此操作。 XMPP 功能安装在两个部分中：作为运行在旧版边缘服务器上的 XMPP 代理，以及在旧版前端服务器上运行的 XMPP 网关。 
  
从迁移的角度来看，需要 XMPP 功能的用户应保留在旧版服务器中，并且不应移动到 Skype for Business Server 2019 池，但继续使用旧版 XMPP 网关。 仅当在 Skype for business Server 2015 或 Lync Server 2013 中配置了 XMPP 联盟伙伴时，才可以这样做。 如果要继续使用 XMPP 功能，则不应将旧版边缘服务器迁移到 Skype for business Server 2019。 但是，您可以将旧版边缘服务器（使用 XMPP 代理）和 Skype for Business 2019 边缘服务器共存。
  

    

