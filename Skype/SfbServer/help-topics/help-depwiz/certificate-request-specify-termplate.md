---
title: 证书请求（指定模板）
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: 通过"指定备用证书模板"页，可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中"为选定的证书颁发机构使用备用证书模板"复选框，然后在"证书模板名称"文本框中定义备用证书模板的名称。 必须使用 CA 证书颁发机构中定义的模板名称 (模板) 。 单击“返回”返回到上一页。 单击“取消”将结束证书请求过程。
ms.openlocfilehash: 4ae4f34b1fb994119637e3c2066b7cf0982216fa
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388520"
---
# <a name="certificate-request-specify-termplate"></a>证书请求（指定模板）
 
通过 **"指定备用证书模板** "页，可以定义默认使用的 WebServer 证书模板外的其他证书模板。 选中 **"为选定的** 证书颁发机构使用备用证书模板"复选框，然后在"证书模板名称"文本框中定义备用 **证书模板的名称**。 必须使用 CA 证书颁发机构中定义的模板名称 (模板) 。 单击 **“返回”** 返回到上一页。 单击 **“取消”** 将结束证书请求过程。
  
> [!CAUTION]
> 只有当公共 CA 建议您使用在颁发证书的系统中定义的特定模板时，才应使用此选项。 如果证书是由您的内部 CA 颁发的，则 CA 管理员应告知您备用证书模板使用的名称。 如果您的组织已定义新的 WebServer 模板并已禁用默认的 WebServer 模板，则此选项非常有用。 
  

