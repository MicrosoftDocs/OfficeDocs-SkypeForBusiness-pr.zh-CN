---
title: 导入证书（简介）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: 若要导入证书, 必须提供证书文件的路径。 在 "选择证书文件" 文本框中, 你可以键入完整路径和文件名, 或单击 "浏览" 按钮并导航到路径位置和文件名 (通常为. p7b、.pfx 或 .cer 文件)。
ms.openlocfilehash: b04f8a2ca2e6d3104f4b36e4bc04b6cdd3c61940
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275550"
---
# <a name="import-certificate-intro"></a>导入证书（简介）
 
若要导入证书, 必须提供证书文件的路径。 在 "**选择证书文件**" 文本框中, 你可以键入完整路径和文件名, 或单击 "**浏览**" 按钮并导航到路径位置和文件名 (通常为. p7b、.pfx 或 .cer 文件)。
  
如果证书包含私钥, 请选中 "**证书文件包含证书的专用密钥**" 复选框。 选中此复选框后, 将启用**密码**文本输入。 如果你有一个与私钥相关联的证书, 则在创建证书时, 通常会在私钥上放置一个密码。 输入私钥的密码, 以允许证书和私钥导入到证书存储。 如果您提供了证书文件路径的信息, 并且有必要输入私钥密码, 请单击 "**下一步**"。
  
> [!IMPORTANT]
> 如果不知道私钥的密码, 导入将失败。 
  

