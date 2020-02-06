---
title: 添加 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: "\"定义新的 Office Web Apps\" 向导在你的部署中定义新的 Office Web Apps 服务器。 请填写以下信息："
ms.openlocfilehash: 9ca5be070d4a79a2cb011a1e91bd0613f21e8700
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798449"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps Server

"**定义新的 Office Web apps** " 向导在你的部署中定义新的 Office Web apps 服务器。 请填写以下信息：

 **Office Web Apps 服务器 FQDN**：键入将承载 Office Web Apps 服务器的服务器的完全限定的域名

 **Office Web Apps 服务器发现 URL**：键入 Office Web apps 服务器的完整统一资源定位器（URL）

> [!TIP]
> **Office Web Apps 服务器发现 url**的默认行为是基于 Office Web apps 服务器的 FQDN 创建 URL，格式如下： `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多数情况下，不需要更改默认格式。 在 Office Web Apps 服务器和 Office Web Apps 服务器发现 URL 必须不同的情况下，可能需要更改默认格式。 例如，你的 Office Web Apps 服务器位于外围网络中，并且将具有基于该位置的其他 URL。

 **Office Web Apps 服务器部署在外部网络（即，圆周/Internet）中**：如果你的 Office Web apps 服务器位于内部防火墙之外（如外围网络、外部网络或与你的内部网络不同的其他网络区域），请选中该复选框。

## <a name="see-also"></a>另请参阅

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
