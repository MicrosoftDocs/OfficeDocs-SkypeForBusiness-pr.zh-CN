---
title: 证书请求（证书颁发机构）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 在“选择证书颁发机构 (CA)”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：
ms.openlocfilehash: b7e3c3b230376dbb289b526d112440ce69eb574b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302111"
---
# <a name="certificate-request-certificate-authority"></a>证书请求（证书颁发机构）
 
在“**选择证书颁发机构 (CA)**”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：
  
1. 从在您的环境中检测到的列表中选择一个 CA。
    
2. 指定其他证书颁发机构。
    
如果您选择第一个选项, 您将看到一个下拉列表, 其中包含在您的环境中检测到的所有基于 Windows 服务器的证书颁发机构。 选择证书相应的证书颁发机构。 您可能需要咨询 CA 管理员以了解应选择哪个 CA。
  
如果选择第二个选项，则需键入要用于证书的证书颁发机构的完全限定域名 (FQDN) 以及 CA 实例。如果要使用的 CA 不是基于 Windows Server 的 CA，但适用于基于 Windows Server 的 CA，则此选项适用。
  
> [!IMPORTANT]
> 应首先确认所需的组成员身份以确保证书请求能够成功。 通常, 证书颁发机构对在服务器上安装 Skype for Business 服务器的要求具有不同的权限要求。 请与 CA 管理员确认请求证书的要求。 
  

