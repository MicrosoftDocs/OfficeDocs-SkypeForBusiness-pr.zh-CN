---
title: 导入证书（简介）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: 若要导入证书，必须提供证书文件的路径。 在 "选择证书文件" 文本框中，你可以键入完整路径和文件名，或单击 "浏览" 按钮并导航到路径位置和文件名（通常为. p7b、.pfx 或 .cer 文件）。
ms.openlocfilehash: 63420dad20e5174cb41f9fc00d63a1f7c25763a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823666"
---
# <a name="import-certificate-intro"></a>导入证书（简介）
 
若要导入证书，必须提供证书文件的路径。 在 "**选择证书文件**" 文本框中，你可以键入完整路径和文件名，或单击 "**浏览**" 按钮并导航到路径位置和文件名（通常为. p7b、.pfx 或 .cer 文件）。
  
如果证书包含私钥，请选中 "**证书文件包含证书的专用密钥**" 复选框。 选中此复选框后，将启用**密码**文本输入。 如果你有一个与私钥相关联的证书，则在创建证书时，通常会在私钥上放置一个密码。 输入私钥的密码，以允许证书和私钥导入到证书存储。 如果您提供了证书文件路径的信息，并且有必要输入私钥密码，请单击 "**下一步**"。
  
> [!IMPORTANT]
> 如果不知道私钥的密码，导入将失败。 
  

