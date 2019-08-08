---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '以前的版本提供了可扩展消息和状态协议 (XMPP) 网关, 可将其部署为单独的服务器角色, 以便允许与 XMPP 部署进行联盟。 XMPP 功能在 Skype for Business Server 2019 中不再可用 & 已弃用。 如果您想要继续处理 XMPP 功能, 可通过旧版版本 (Skype for business Server 2015/Lync Server 2013) 在 coexitence 环境中 availed。 XMPP 功能安装在两个部分中: 作为在旧版 Edge 服务器上运行的 XMPP 代理, 以及在旧前端服务器上运行的 XMPP 网关。'
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237791"
---
# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

以前的版本提供了可扩展消息和状态协议 (XMPP) 网关, 可将其部署为单独的服务器角色, 以便允许与 XMPP 部署进行联盟。 在 Skype for Business Server 2019 中, XMPP 功能不再可用且已弃用。 如果你想要继续使用 XMPP 功能, 可以在具有旧版版本 (Skype for business Server 2015 或 Lync Server 2013) 的共存环境中执行此操作。 XMPP 功能安装在两个部分中: 作为在旧版 Edge 服务器上运行的 XMPP 代理, 以及在旧前端服务器上运行的 XMPP 网关。 
  
从迁移的角度看, 想要使用 XMPP 功能的用户应保留在旧服务器中, 并且不应移动到 Skype for business Server 2019 池, 但继续使用旧版 XMPP 网关。 仅当在 Skype for Business Server 2015 或 Lync Server 2013 中配置了 XMPP 联盟伙伴时, 才可以这样做。 如果要继续 XMPP 功能, 则不应将旧式边缘服务器迁移到 Skype for business Server 2019。 但是, 你可以使用旧版 Edge 服务器 (使用 XMPP 代理) 和 Skype for business 2019 Edge 服务器共存。
  

    

