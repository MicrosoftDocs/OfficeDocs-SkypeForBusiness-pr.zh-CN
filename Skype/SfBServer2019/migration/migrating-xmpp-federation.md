---
title: 迁移 XMPP 联盟
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 早期版本提供的可扩展消息和状态协议 (XMPP) 网关无法作为允许与 XMPP 部署联盟的单独的服务器角色部署。 不再可用和 Skype 的业务服务器 2019年中已弃用的 XMPP 功能。 如果您想要继续使用 XMPP 功能，可以将的适用 coexitence 环境与旧版本中 (业务服务器 2015年的 Skype / Lync Server 2013)。 XMPP 功能安装在两个部分： 为 XMPP 代理运行旧边缘服务器和 XMPP 网关的旧前端服务器上运行。
ms.openlocfilehash: c1c189d8d4b2e4fcd75b3d00d9789736f5bafc6a
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839536"
---
# <a name="migrating-xmpp-federation"></a>迁移 XMPP 联盟

早期版本提供的可扩展消息和状态协议 (XMPP) 网关无法作为允许与 XMPP 部署联盟的单独的服务器角色部署。 XMPP 功能不再可用，并在 Skype 中的业务服务器 2019年已弃用。 如果您想要继续使用 XMPP 功能，您可以这样在共存环境中使用旧版本 (Skype 业务服务器 2015年或 Lync Server 2013)。 XMPP 功能安装在两个部分： 为 XMPP 代理运行旧边缘服务器和 XMPP 网关的旧前端服务器上运行。 
  
从迁移的角度看，希望获得 XMPP 功能的用户应保留在旧服务器不应移动到 Skype 业务服务器 2019年池但继续使用旧的 XMPP 网关。 这是可能的仅当在 Skype 业务服务器 2015年或 Lync Server 2013 配置 XMPP 联盟的伙伴时。 您应不迁移旧边缘服务器到 Skype 业务服务器 2019年如果您想要继续使用 XMPP 功能。 但是，您可以旧边缘服务器 （与 XMPP 代理） 和 Skype 业务 2019年边缘服务器共存。
  

    

