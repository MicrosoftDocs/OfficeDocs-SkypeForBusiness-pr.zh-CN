---
title: 在 Skype for Business Server 2015 中为外部用户配置存档免责声明
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要： 阅读本主题，以了解如何配置存档放弃声明的 Skype 业务服务器 2015年。
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中为外部用户配置存档免责声明
 
**摘要：**阅读本主题，以了解如何配置存档放弃声明的 Skype 业务服务器 2015年。
  
如果您的组织与外部合作伙伴通信，您需要让他们知道，您会存档与他们之间的通信。 当您部署边缘服务器，并为您的组织中启用联盟时，会询问您是否要自动将存档放弃声明发送给外部合作伙伴。 
  
如果您需要更改此配置，您可以使用 Skype 业务服务器的控制面板或 Windows PowerShell**集 CsAccessEdgeConfiguration** cmdlet。 从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行 Cmdlet。
  
若要启用外部用户与您 Skype 业务服务器部署中的用户进行协作，还必须配置至少一个外部访问策略，以支持外部用户访问权限。 详细信息，请参阅您的组织的管理 XMPP 联合伙伴。 有关控制特定联盟域的访问的详细信息，请参阅“控制各个联盟域的访问”。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用控制面板启用或禁用存档免责声明

1. 使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。
    
4. 在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑访问边缘配置**”的“**启用联盟和公共 IM 连接**”下，选中或清除“**向联盟伙伴发送存档免责声明**”复选框以启用或禁用自动发送存档免责声明。
    
6. 单击“**提交**”。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>使用 Windows PowerShell 启用或禁用存档免责声明

要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


