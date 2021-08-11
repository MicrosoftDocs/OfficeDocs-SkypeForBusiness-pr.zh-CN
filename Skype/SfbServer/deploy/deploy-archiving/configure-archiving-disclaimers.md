---
title: 为外部用户配置存档免责声明Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：阅读本主题，了解如何配置存档Skype for Business Server。
ms.openlocfilehash: 1afacace566cc75659e5b53e05346461b99f0cb888497f79da6340130585c959
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312140"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>为外部用户配置存档免责声明Skype for Business Server
 
**摘要：** 阅读本主题，了解如何配置存档Skype for Business Server。
  
如果您的组织与外部合作伙伴通信，您需要让他们知道您正在存档与外部合作伙伴的通信。 为组织部署边缘服务器并启用联盟时，会询问您是否要自动向外部合作伙伴发送存档免责声明。 
  
如果需要更改此配置，可以使用 Skype for Business Server 控制面板或 Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet。 Cmdlet 可以从命令行管理程序Skype for Business Server或远程会话运行Windows PowerShell。
  
若要使外部用户能够与 Skype for Business Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持外部用户访问。 有关详细信息，请参阅管理组织的 XMPP 联盟伙伴。 有关控制特定联盟域的访问的详细信息，请参阅控制单个联盟域的访问。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用控制面板启用或禁用存档免责声明

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击“联盟和外部访问”，然后单击“访问边缘配置”。
    
4. 在“访问边缘配置”选项卡上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"编辑访问边缘配置**"中的"启用联盟和公共 **IM** 连接"下，选中或清除"向联盟伙伴发送存档免责声明"复选框以启用或禁用自动发送存档免责声明。
    
6. 单击“提交”。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>使用存档规则启用或禁用存档Windows PowerShell

要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


