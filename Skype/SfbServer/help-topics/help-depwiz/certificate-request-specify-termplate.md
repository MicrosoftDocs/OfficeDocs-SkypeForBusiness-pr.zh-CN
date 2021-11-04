---
title: 证书请求（指定模板）
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: 通过"指定备用证书模板"页，可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中"为选定的证书颁发机构使用备用证书模板"复选框，然后在"证书模板名称"文本框中定义备用证书模板的名称。 必须使用在 CA 证书颁发机构中定义的模板 (名称) 。 单击“返回”返回到上一页。 单击“取消”将结束证书请求过程。
ms.openlocfilehash: e55647821e3c2793ca1b6f7f1ecbf85912406906
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740938"
---
# <a name="certificate-request-specify-termplate"></a>证书请求（指定模板）
 
通过 **"指定备用证书模板** "页，可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中 **"为选定的** 证书颁发机构使用备用证书模板"复选框，然后在"证书模板名称"文本框中定义 **备用证书模板的名称**。 必须使用在 CA 证书颁发机构中定义的模板 (名称) 。 单击 **“返回”** 返回到上一页。 单击 **“取消”** 将结束证书请求过程。
  
> [!CAUTION]
> 只有当公共 CA 建议您使用在颁发证书的系统中定义的特定模板时，才应使用此选项。 如果证书是由您的内部 CA 颁发的，则 CA 管理员应告知您备用证书模板使用的名称。 如果您的组织已定义新的 WebServer 模板并已禁用默认的 WebServer 模板，则此选项非常有用。 
  

