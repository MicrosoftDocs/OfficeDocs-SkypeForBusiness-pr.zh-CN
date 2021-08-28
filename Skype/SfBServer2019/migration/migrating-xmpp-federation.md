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
ms.localizationpriority: medium
description: 早期版本提供了可扩展消息传递和状态协议 (XMPP) 网关，该网关可以部署为单独的服务器角色，以允许与 XMPP 部署联盟。 XMPP 功能在 2019 &不再Skype for Business Server弃用。 如果要继续使用 XMPP 功能，可在与旧版本 (Skype for Business Server 2015/ Lync Server 2013) 共存环境中使用。 XMPP 功能分两部分安装：作为在旧版边缘服务器上运行的 XMPP 代理和在旧版前端服务器上运行的 XMPP 网关。
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580126"
---
# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

早期版本提供了可扩展消息传递和状态协议 (XMPP) 网关，该网关可以部署为单独的服务器角色，以允许与 XMPP 部署联盟。 XMPP 功能不再可用，2019 年 10 月Skype for Business Server弃用。 如果要继续使用 XMPP 功能，可以在与旧版 (Skype for Business Server 2015 或 Lync Server 2013) 共存环境中执行。 XMPP 功能分两部分安装：作为在旧版边缘服务器上运行的 XMPP 代理和在旧版前端服务器上运行的 XMPP 网关。 
  
从迁移的角度来看，希望使用 XMPP 功能的用户应保留在旧服务器中，不应移至 Skype for Business Server 2019 池，而是继续使用旧的 XMPP 网关。 只有在 Skype for Business Server 2015 或 Lync Server 2013 中配置 XMPP 联盟伙伴时，才能这样做。 如果要继续使用 XMPP 功能，则不应将旧边缘服务器Skype for Business Server 2019。 但是，可以将旧版边缘服务器与 XMPP (与) 2019 边缘Skype for Business共存。
  

    

