---
title: 添加 Office Web Apps 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 定义新的 Office Web Apps Server 向导在您的部署中定义新的 Office Web Apps 服务器。 请填写以下信息：
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218723"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps 服务器

**定义新的 Office Web Apps server**向导在您的部署中定义新的 Office Web apps 服务器。 请填写以下信息：

 **Office Web Apps SERVER FQDN**：键入将承载 Office Web apps server 的服务器的完全限定的域名称

 **Office Web Apps server 发现 URL**：键入 Office Web apps SERVER (URL) 的完全统一资源定位器

> [!TIP]
> **Office Web Apps server 发现 URL**的默认行为是创建基于 Office Web apps SERVER 的 FQDN 的 URL，格式为： `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多数情况下，不需要更改默认格式。 当 Office Web Apps Server 和 Office Web Apps Server 发现 URL 必须不同时，您可能需要更改默认格式。 例如，您的 Office Web Apps Server 放置在外围网络中，并且将具有一个基于该位置的不同 URL。

 **Office Web Apps server 部署在外部网络中 (即外围/Internet) **：如果您的 Office Web apps Server 位于内部防火墙之外（如外围网络、外部网络或其他与内部网络不同的网络区域），请选中此复选框。

## <a name="see-also"></a>另请参阅

[用于会议的组件和拓扑](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
