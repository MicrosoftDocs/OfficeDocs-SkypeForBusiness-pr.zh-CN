---
title: 添加 Office Web Apps 服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "\"定义新的 Office Web Apps Server\"向导在部署中定义新的 Office Web Apps Server。 请填写以下信息："
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828592"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps 服务器

" **定义新的 Office Web Apps Server"** 向导在部署中定义新的 Office Web Apps Server。 请填写以下信息：

 **Office Web Apps Server FQDN：** 键入将托管 Office Web Apps 服务器的服务器的完全限定域名

 **Office Web Apps Server 发现 URL：** 键入 Office Web Apps Server (URL) 统一资源定位器

> [!TIP]
> **Office Web Apps Server** 发现 URL 的默认行为是基于 Office Web Apps Server 的 FQDN 创建 URL，格式为： `https://<FQDN of the Office Web Apps Server/hosting/discovery` 在大多数情况下，不需要更改默认格式。 如果 Office Web Apps Server 和 Office Web Apps Server 发现 URL 必须不同，您可能需要更改默认格式。 例如，您的 Office Web Apps Server 位于外围网络中，并且将基于位置具有不同的 URL。

 Office Web Apps Server 部署在外部网络 (中，即外围 **/Internet) ：** 如果 Office Web Apps 服务器位于内部防火墙之外（如外围网络、外部网络或其他与内部网络不同的网络区域）之外，请选中该复选框。

## <a name="see-also"></a>另请参阅

[用于会议的组件和拓扑](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
