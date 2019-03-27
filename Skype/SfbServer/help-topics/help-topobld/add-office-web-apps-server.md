---
title: 添加 Office Web Apps Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 定义新 Office Web Apps Server 向导定义新的 Office Web Apps Server 部署中。 请填写以下信息：
ms.openlocfilehash: 79f07ab88f62ba9b7e886b06b6d7c89143cd7380
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873317"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps Server

**定义新 Office Web Apps Server**向导定义新的 Office Web Apps Server 部署中。 请填写以下信息：

 **Office Web Apps 服务器 FQDN**： 键入将承载 Office Web Apps Server 的服务器的完全限定的域名

 **Office Web Apps 服务器发现 URL**： 键入 Office Web Apps Server 的完全统一资源定位器 (URL)

> [!TIP]
> **Office Web Apps 服务器发现 URL**的默认行为是创建基于格式的 Office Web Apps Server 的 FQDN 的 URL: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多数情况下，不需要更改默认格式。 您可能需要更改默认格式中的 Office Web Apps Server 和 Office Web Apps 服务器发现 URL 必须不同。 例如，您的 Office Web Apps Server 位于外围网络中，并将具有不同基于位置的 URL。

 **在外部网络 (即，外围 /internet) 中部署 office Web Apps Server**： 如果您的 Office Web Apps Server 发出您的内部防火墙，如外围网络、 外部网络或其他网络区域之外选中复选框这不是内部网络相同。

## <a name="see-also"></a>另请参阅

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
