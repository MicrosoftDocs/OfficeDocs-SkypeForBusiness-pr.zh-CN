---
title: 添加 Office Web Apps Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 定义新 Office Web Apps Server 向导定义新的 Office Web Apps Server 部署中。 请填写以下信息：
ms.openlocfilehash: d83e9313aa1f6d868c3ac8557e87fe53f9b86d9c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257499"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps Server

**定义新 Office Web Apps Server**向导定义新的 Office Web Apps Server 部署中。 请填写以下信息：

 **Office Web Apps 服务器 FQDN**： 键入将承载 Office Web Apps Server 的服务器的完全限定的域名

 **Office Web Apps 服务器发现 URL**： 键入 Office Web Apps Server 的完全统一资源定位器 (URL)

> [!TIP]
> **Office Web Apps 服务器发现 URL**的默认行为是创建基于格式的 Office Web Apps Server 的 FQDN 的 URL: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多数情况下，不需要更改默认格式。 您可能需要更改默认格式中的 Office Web Apps Server 和 Office Web Apps 服务器发现 URL 必须不同。 例如，您的 Office Web Apps Server 位于外围网络中，并将具有不同基于位置的 URL。

 **在外部网络 (即，外围 /internet) 中部署 office Web Apps Server**： 如果您的 Office Web Apps Server 发出您的内部防火墙，如外围网络、 外部网络或其他网络区域之外选中复选框这不是内部网络相同。

## <a name="see-also"></a>另请参阅

[会议的组件和拓扑](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)