---
title: 将服务器到服务器身份验证证书分配给 Skype for Business 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：为 Skype for business 服务器分配服务器到服务器身份验证证书。
ms.openlocfilehash: 0332ba66c1cad69470b0007c4d9524a3025e0be7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991767"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>将服务器到服务器身份验证证书分配给 Skype for Business 服务器
**摘要：** 为 Skype for business 服务器分配服务器到服务器身份验证证书。
  
若要确定服务器到服务器身份验证证书是否已分配给 Skype for business 服务器，请从 Skype for Business Server 命令行管理程序运行以下命令：
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。 作为一般规则，任何 Skype for business 服务器证书均可用作 OAuthTokenIssuer 证书;例如，您的 Skype for Business 服务器默认证书也可以用作 OAuthTokenIssuer 证书。 （OAUthTokenIssuer 证书也可以是任何 Web 服务器证书，其中包含 "主题" 字段中的 SIP 域的名称。）用于服务器到服务器身份验证的证书的主要要求如下：1）必须在所有前端服务器上将相同的证书配置为 OAuthTokenIssuer 证书;和2）证书必须至少为2048位。
  
如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。 在请求并获得新证书后，您可以登录到任何一个前端服务器，并使用类似于此的 Windows PowerShell 命令导入并分配该证书：
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。 此过程应仅运行一次：然后，Skype for business Server 复制服务将自动创建一组计划任务，这些任务将把证书解密并部署到所有前端服务器。
  
您也可以使用现有证书作为服务器到服务器身份验证证书。 （如所述，默认证书可用作服务器到服务器身份验证证书。）以下 Windows PowerShell 命令对检索默认证书的 Thumbprint 属性的值，然后使用该值将默认证书设置为服务器到服务器的身份验证证书：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在前面的命令中，检索到的证书被配置为充当全局服务器到服务器身份验证证书;这意味着证书将被复制到所有前端服务器并由所有前端服务器使用。 同样，此命令只应运行一次，并且只能在其中一个前端服务器上运行。 虽然所有前端服务器必须使用相同的证书，但不应在每个前端服务器上配置 OAuthTokenIssuer 证书。 相反，配置证书一次，然后让 Skype for Business 服务器复制服务器负责将该证书复制到每台服务器。
  
CsCertificate cmdlet 接受有问题的证书，并立即将该证书配置为充当当前的 OAuthTokenIssuer 证书。 （Skype for Business 服务器保留证书类型的两个副本：当前证书和以前的证书。）如果你需要新证书立即开始充当 OAuthTokenIssuer 证书，则应使用 CsCertificate cmdlet。
  
您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2015 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

2015年7月1日，新证书将配置为当前的 OAuthTokenIssuer 证书，"旧" OAuthTokenIssuer 证书将配置为以前的证书。
  
如果不想使用 Windows PowerShell，还可以使用证书 MMC 控制台从一个前端服务器导出证书，然后在所有其他前端服务器上导入该相同证书。 如果执行此操作，请确保将私钥连同证书本身一起导出。
  
> [!CAUTION]
> 在这种情况下，必须在每个前端服务器上执行该过程。 以这种方式导出和导入证书时，Skype for Business Server 不会将该证书复制到每个前端服务器。 
  
在将证书导入到所有前端服务器之后，可以使用 Skype for Business 服务器部署向导而不是 Windows PowerShell 来分配该证书。 要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：
  
1. 单击 "开始"，单击 "所有程序"，单击 "Skype for business**服务器**"，然后单击 " **Skype For Business 服务器部署向导**"。
    
2. 在 "部署向导" 中，单击 "**安装或更新 Skype for Business 服务器系统**"。
    
3. 在 "Skype for Business 服务器" 页面上，单击 "标题**步骤3：请求，安装或分配证书**" 下的 "**运行**" 按钮。 （注意：如果你已在此计算机上安装了证书，则 "**运行**" 按钮将被标记为 "已**再次运行**"。）
    
4. 在证书向导中，选择 OAuthTokenIssuer**** 证书，然后单击“分配”****。
    
5. 在证书分配向导的“证书分配”**** 页上，单击“下一步”****。
    
6. 在“证书存储”**** 页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”****。
    
7. 在“证书分配摘要”页上，单击“下一步”****。
    
8. 在“正在执行命令”页上，单击“完成”****。
    
9. 关闭证书向导和部署向导。
    

