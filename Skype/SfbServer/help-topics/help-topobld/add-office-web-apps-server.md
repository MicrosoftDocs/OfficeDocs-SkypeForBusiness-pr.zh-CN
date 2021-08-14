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
description: "\"定义新的 Office Web Apps Server\"向导定义部署Office Web Apps Server 的新应用程序。 请填写以下信息："
ms.openlocfilehash: e72ff910b0ad299de9bbd5599aa64c338531024d0c1a41182567a67c8373ec3d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343596"
---
# <a name="add-office-web-apps-server"></a>添加 Office Web Apps 服务器

"**定义新的 Office Web Apps Server"** 向导定义部署Office Web Apps Server 的新应用程序。 请填写以下信息：

 **Office Web Apps 服务器 FQDN：** 键入将承载 Web Apps Server Office的完全限定域名

 **Office Web Apps Server 发现 URL：** 键入 (Web Apps Server) 的完整统一Office URL

> [!TIP]
> Web Apps Server Office **URL** 的默认行为是基于 Office Web Apps Server 的 FQDN 创建 URL，格式为 `https://<FQDN of the Office Web Apps Server/hosting/discovery` ： 。 在大多数情况下，不需要更改默认格式。 如果 Web Apps Server 和 Office Web Apps Server 发现 URL 必须Office，您可能需要更改默认格式。 例如，Office Web Apps Server 放置在外围网络中，并且根据位置将具有不同的 URL。

 Office Web Apps 服务器部署在外部网络 (中，即外围 **/Internet) ：** 如果您的 Office Web Apps 服务器位于内部防火墙外部（如外围网络、外部网络或其他与内部网络不同的网络区域）之外，请选中此复选框。

## <a name="see-also"></a>另请参阅

[用于会议的组件和拓扑](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)