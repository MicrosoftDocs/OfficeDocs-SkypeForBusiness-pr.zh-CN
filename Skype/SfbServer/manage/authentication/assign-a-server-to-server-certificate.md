---
title: 为业务服务器分配 Skype 的服务器到服务器身份验证证书
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要： 分配服务器到服务器身份验证证书的 Skype 业务服务器。
ms.openlocfilehash: 9bf2cf1ceaa43d5471d699a44f3e965b1bc5eda8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993755"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>为业务服务器分配 Skype 的服务器到服务器身份验证证书
**摘要：** 为业务服务器的 Skype 分配的服务器到服务器身份验证证书。
  
若要确定的服务器到服务器身份验证证书已被分配到 Skype 业务服务器，请从 Skype 的业务 Server 命令行管理程序运行以下命令：
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。 一般来说，业务服务器证书任何 Skype 可用作 OAuthTokenIssuer 证书;例如，您 Skype Business Server 默认证书也可以用作 OAuthTokenIssuer 证书。 （OAUthTokenIssuer 证书也可以是在主题字段中包括您的 SIP 域的名称的任何 Web 服务器证书。）用于服务器到服务器身份验证的证书的主要两个要求如下： 1) 相同的证书必须配置为在所有前端服务器; OAuthTokenIssuer 证书以及 2） 的证书必须至少为 2048 位。
  
如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。 在请求并获得新证书之后可以然后登录到任意一个前端服务器和使用 Windows PowerShell 命令与此类似导入和分配该证书：
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。 此过程应该运行一次即可： 业务服务器复制服务 Skype 然后将自动创建一套将解密并部署到所有前端服务器的证书的计划任务。
  
您也可以使用现有证书作为服务器到服务器身份验证证书。 （如前所述，默认证书可为服务器到服务器身份验证证书。）以下两个 Windows PowerShell 命令检索默认证书的指纹属性的值，然后使用该值设置为默认证书的服务器到服务器身份验证证书：
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在上述命令中，检索的证书配置为充当全局服务器到服务器身份验证证书;这意味着将复制到，并使用所有前端服务器证书。 同样，只应一次，并仅在一台前端服务器运行此命令。 虽然所有前端服务器必须使用同一个证书，则不应该在每个前端服务器上配置 OAuthTokenIssuer 证书。 相反，一次，配置证书，然后让业务服务器复制服务器将该证书复制到每台服务器的 Skype。
  
Set-cscertificate cmdlet 将讨论的证书，并立即配置该证书用作当前 OAuthTokenIssuer 证书。 (业务服务器 Skype 保存证书类型的两个副本： 当前证书和以前的证书。)如果您需要立即开始充当 OAuthTokenIssuer 证书，则应使用 Set-cscertificate cmdlet 的新证书。
  
您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2015 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

在 2015 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，"旧"OAuthTokenIssuer 证书将配置为以前的证书。
  
如果您不希望使用 Windows PowerShell 您可以使用证书 MMC 控制台来从一台前端服务器导出证书，然后在所有其他前端服务器上导入的同一个证书。 如果执行此操作，请确保将私钥连同证书本身一起导出。
  
> [!CAUTION]
> 在这种情况下，必须在每个前端服务器上执行过程。 时导出和导入按照这种方式 Skype 业务服务器的证书不将将该证书复制到每个前端服务器。 
  
证书导入到所有前端服务器之后，然后可以使用 Skype 业务 Server 部署向导，而不是 Windows PowerShell 分配该证书。 要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：
  
1. 单击开始，单击所有程序、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server 部署向导**。
    
2. 在部署向导中，单击**安装或更新 Skype 业务 Server 系统**。
    
3. 在 Business Server 页 Skype，单击**运行**按钮标题下的**步骤 3： 请求、 安装或分配证书**。 (注意： 如果您已在此计算机上安装证书，则将**再次运行**标有**运行**按钮。)
    
4. 在证书向导中，选择 OAuthTokenIssuer**** 证书，然后单击“分配”****。
    
5. 在证书分配向导的“证书分配”**** 页上，单击“下一步”****。
    
6. 在“证书存储”**** 页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”****。
    
7. 在“证书分配摘要”页上，单击“下一步”****。
    
8. 在“正在执行命令”页上，单击“完成”****。
    
9. 关闭证书向导和部署向导。
    

