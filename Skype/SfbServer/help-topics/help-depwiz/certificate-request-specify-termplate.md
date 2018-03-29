---
title: 证书请求（指定模板）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: 指定备用证书模板页使您能够定义而不使用默认的 web 服务器证书模板的证书模板。 选择所选的证书颁发机构，复选框使用备用的证书模板，然后在文本框的证书模板名称定义备用的证书模板的名称。 必须使用在证书颁发机构 (CA) 中定义的模板名称。 单击后可返回到前一页。 单击取消结束证书请求过程。
ms.openlocfilehash: 856ad66b4bf2974e43e8684ca6016494df26019f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-specify-termplate"></a>证书请求（指定模板）
 
通过“**指定替代证书模板**”页，可以定义默认情况下使用的 WebServer 证书模板之外的证书模板。选中“**对选定的证书颁发机构使用替代证书模板**”复选框，然后在“**证书模板名称**”文本框中定义替代证书模板的名称。必须使用在证书颁发机构 (CA) 中定义的模板名称。单击“**上一步**”返回到上一页。单击“**取消**”将结束证书请求过程。
  
> [!CAUTION]
> 应仅在公共 CA 建议您使用其系统上定义的特定模板来颁发证书时使用此选项。如果证书是由您的内部 CA 颁发的，则 CA 管理员应告知您替代证书模板使用的名称。如果您的组织已定义新的 WebServer 模板并已禁用默认的 WebServer 模板，则此选项非常有用。 
  

