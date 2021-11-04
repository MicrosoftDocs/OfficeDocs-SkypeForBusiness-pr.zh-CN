---
title: 证书请求（证书颁发机构）
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
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 在“选择证书颁发机构(CA)”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：
ms.openlocfilehash: 226a653c08a176e64b0b908d0276549e62c00273
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741028"
---
# <a name="certificate-request-certificate-authority"></a>证书请求（证书颁发机构）
 
在“选择证书颁发机构(CA)”页面上向联机证书颁发机构 (CA)（通常是内部网络中的服务器）发出证书请求时，将看到两个选项：
  
1. 从在您的环境中检测到的列表中选择一个 CA。
    
2. 指定其他证书颁发机构。
    
如果选择第一个选项，你将看到一个下拉列表，其中包含Windows检测到的所有基于服务器的证书颁发机构。 选择证书相应的证书颁发机构。 您可能需要咨询 CA 管理员以了解应选择哪个 CA。
  
如果选择第二个选项，则需键入要用于证书的证书颁发机构的完全限定域名 (FQDN) 以及 CA 实例。如果要使用的 CA 不是基于 Windows Server 的 CA，但适用于基于 Windows Server 的 CA，则此选项适用。
  
> [!IMPORTANT]
> 应首先确认所需的组成员身份以确保证书请求能够成功。 通常，证书颁发机构的权限要求与服务器上安装证书颁发Skype for Business Server要求不同。 请与 CA 管理员确认请求证书的要求。 
  

