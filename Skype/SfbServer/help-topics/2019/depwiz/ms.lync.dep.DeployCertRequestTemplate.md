---
title: 证书请求（指定模板）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
ROBOTS: NOINDEX, NOFOLLOW
description: 通过"指定备用证书模板"页，您可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中"使用所选证书颁发机构的备用证书模板"复选框，然后在"证书模板名称"文本框中定义备用证书模板的名称。 必须使用在 CA 证书颁发机构中定义的模板 (名称) 。 单击“返回”返回到上一页。 单击“取消”将结束证书请求过程。
ms.openlocfilehash: e030882f44d4010049b12b69cc10d180225bf523
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801732"
---
# <a name="certificate-request-specify-termplate"></a>证书请求（指定模板）
 
通过 **"** 指定备用证书模板"页，您可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中"使用所选 **证书颁发** 机构的备用证书模板"复选框，然后在"证书模板名称"文本框中定义备用证书 **模板的名称**。 必须使用在 CA 证书颁发机构中定义的模板 (名称) 。 单击 **“返回”** 返回到上一页。 单击 **“取消”** 将结束证书请求过程。
  
> [!CAUTION]
> 只有在公共 CA 建议您使用其系统上定义的特定模板来颁发证书时，才应使用此选项。 如果证书是由您的内部 CA 颁发的，则 CA 管理员应告知您备用证书模板使用的名称。 如果您的组织已定义新的 WebServer 模板并已禁用默认的 WebServer 模板，则此选项非常有用。 
  

