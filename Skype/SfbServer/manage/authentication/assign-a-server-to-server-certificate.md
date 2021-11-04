---
title: 将服务器到服务器身份验证证书分配给Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：为用户分配服务器到服务器身份验证Skype for Business Server。
ms.openlocfilehash: b36db3956dc801d4874a13033bba60917b7112af
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754875"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>将服务器到服务器身份验证证书分配给Skype for Business Server
**摘要：** 为用户分配服务器到服务器身份验证Skype for Business Server。
  
若要确定是否已经将服务器到服务器身份验证证书分配给 Skype for Business Server，请从命令行管理程序运行Skype for Business Server命令：
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。 一般而言，任何Skype for Business Server证书都可以用作 OAuthTokenIssuer 证书;例如，您的Skype for Business Server证书也可以用作 OAuthTokenIssuer 证书。  (OAUthTokenIssuer 证书还可以是"主题"字段中包含 SIP 域名称的任何 Web 服务器证书。) 用于服务器到服务器身份验证的证书的主要两个要求如下：1) 必须在所有前端服务器上将同一证书配置为 OAuthTokenIssuer 证书;和 2) 证书必须至少为 2048 位。
  
如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。在请求并获取新证书后，可以登录到任一前端服务器并使用类似如下的 Windows PowerShell 命令导入和分配该证书：
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。 此过程应只运行一次：然后，Skype for Business Server复制服务将自动创建一组计划任务，这些任务将解密证书并部署到所有前端服务器。
  
您也可以使用现有证书作为服务器到服务器身份验证证书。（如前所述，默认证书可用作服务器到服务器身份验证证书。）以下 Windows PowerShell 命令对可检索默认证书的 Thumbprint 属性的值，然后使用该值使默认证书成为服务器到服务器身份验证证书：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在上述命令中，所检索的证书配置为用作全局服务器到服务器身份验证证书；这意味着该证书将被复制到所有前端服务器并被这些服务器使用。 再强调一次，此命令只应在其中一台前端服务器上运行一次。 尽管所有前端服务器都必须使用相同证书，但您不应在每台前端服务器上都配置 OAuthTokenIssuer 证书。 相反，配置证书一次，然后让Skype for Business Server复制服务器负责将证书复制到每个服务器。
  
该Set-CsCertificate cmdlet 获取该证书并立即配置该证书以用作当前的 OAuthTokenIssuer 证书。  (Skype for Business Server保留证书类型的两个副本：当前证书和上一个证书。) 如果需要新证书立即开始用作 OAuthTokenIssuer 证书，则应该使用 Set-CsCertificate cmdlet。
  
您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。 “滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。 例如，以下命令检索默认证书，然后将该证书配置为自 2015 年 7 月 1 日起作为当前 OAuthTokenIssuer 证书接管：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

2015 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，"旧"OAuthTokenIssuer 证书将配置为上一个证书。
  
如果不想使用 Windows PowerShell，还可以使用证书 MMC 控制台从一台前端服务器中导出证书，然后在所有其他前端服务器上导入相同证书。如果执行此操作，请确保将私钥连同证书本身一起导出。
  
> [!CAUTION]
> 在这种情况下，必须在每台前端服务器上执行该过程。 当通过此方式导出和导入证书Skype for Business Server不会将证书复制到每个前端服务器。 
  
将证书导入到所有前端服务器后，可以使用部署向导而不是 Skype for Business Server 分配该证书Windows PowerShell。 要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：
  
1. 单击"开始"，单击"所有程序"，Skype for Business Server"，然后单击"Skype for Business Server **部署向导"。**
    
2. 在部署向导中，单击 **"安装或更新Skype for Business Server系统"。**
    
3. 在"Skype for Business Server页上，单击"步骤3： 请求、安装或分配证书"标题 **下的"运行"按钮**。  (注意：如果已在此计算机上安装证书，则 **"** 运行"按钮将标记为"再次运行 **.)**
    
4. 在证书向导中，选择 OAuthTokenIssuer 证书，然后单击“分配”。
    
5. 在证书分配向导的“证书分配”页上，单击“下一步”。
    
6. 在“证书存储”页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”。
    
7. 在“证书分配摘要”页上，单击“下一步”。
    
8. 在“正在执行命令”页上，单击“完成”。
    
9. 关闭证书向导和部署向导。
    

