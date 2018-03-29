---
title: 将服务器对服务器身份验证证书分配给 Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要： 将分配用于业务服务器 2015 Skype 的服务器到服务器身份验证证书。
ms.openlocfilehash: 7bc697d9c45b55708ffb3fa20f04fbeb3eec9de9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server-2015"></a>将服务器对服务器身份验证证书分配给 Skype for Business Server 2015
**摘要：**为业务服务器 2015年的 Skype 分配的服务器到服务器身份验证证书。
  
若要确定服务器到服务器身份验证证书已被分配到 Skype 的业务服务器 2015年，请从 Skype 的业务服务器管理外壳程序运行下面的命令：
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。 作为一般规则，任何 Skype 业务服务器 2015年证书可作为 OAuthTokenIssuer 证书;例如，您的 Skype 业务服务器 2015年默认证书也可以用作 OAuthTokenIssuer 证书。 （OAUthTokenIssuer 证书还可以任意 Web 服务器证书的主题字段中包含 SIP 域的名称。这些用于服务器到服务器的身份验证的证书的主要两个要求是： 1) 相同的证书必须配置为 OAuthTokenIssuer 证书对所有您前端服务器;并且，2） 证书必须至少为 2048 位。
  
如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。 在请求和获取新的证书后可以再登录上的任何一种您前端服务器和使用与此类似的 Windows PowerShell 命令导入并分配该证书：
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。 应执行此过程只需一次： 业务服务器复制服务 Skype 然后将自动创建一套调度任务，它们将解密并部署到所有您前端服务器的证书。
  
您也可以使用现有证书作为服务器到服务器身份验证证书。 （如上所述，默认证书可作为服务器到服务器身份验证证书。）以下两个 Windows PowerShell 命令检索属性的值的默认证书指纹，则使用此值将作为默认证书的服务器到服务器身份验证证书：
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在上述命令中，检索到的证书配置为充当全球的服务器到服务器身份验证证书;这意味着将复制到中，并由所有您前端服务器证书。 同样，一次，并且只在一种您前端服务器应该只运行该命令。 尽管所有前端服务器必须使用相同的证书，则不应该在每个前端服务器上配置的 OAuthTokenIssuer 证书。 相反，一次，配置证书，然后让为业务服务器 2015年复制服务器负责将该证书复制到每个服务器的 Skype。
  
设置 CsCertificate cmdlet 采用证书问题，并立即配置该证书作为当前 OAuthTokenIssuer 证书。 (业务服务器 2015年的 Skype 保存的证书类型的两个副本： 当前的证书和以前的证书。)如果您需要立即开始充当 OAuthTokenIssuer 证书，则应使用组 CsCertificate cmdlet 的新证书。
  
您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2015 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

在 2015 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，“旧”OAuthTokenIssuer 证书将配置为上一个证书。
  
如果您不想使用 Windows PowerShell 您还可以使用证书的 MMC 控制台来从一个前端服务器中导出一个证书，然后将同一证书导入所有您其他前端服务器上。 如果执行此操作，请确保将私钥连同证书本身一起导出。
  
> [!CAUTION]
> 在这种情况下，必须在每个前端服务器上执行该过程。 当导出和导入证书以这种方式的业务服务器 2015 Skype 不会为每个前端服务器复制该证书。 
  
证书导入到所有您前端服务器后，然后可以通过 Skype 业务服务器部署向导，而不是 Windows PowerShell 分配该证书。 要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：
  
1. 单击开始，单击所有程序，都单击**业务服务器 2015年的 Skype**，，然后都单击**Skype 业务服务器部署向导**。
    
2. 在部署向导中，单击**安装或更新 Skype 业务服务器系统**。
    
3. 在 Skype 业务服务器 2015年页，在标题下单击**运行**按钮**第 3 步： 安装或分配证书请求**。 (注意： 如果本计算机上已安装的证书，然后将**再次运行**标记为**运行**按钮。)
    
4. 在证书向导中，选择 OAuthTokenIssuer**** 证书，然后单击“分配”****。
    
5. 在证书分配向导的“证书分配”****页上，单击“下一步”****。
    
6. 在“证书存储”****页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”****。
    
7. 在“证书分配摘要”页上，单击“下一步”****。
    
8. 在“正在执行命令”页上，单击“完成”****。
    
9. 关闭证书向导和部署向导。
    

