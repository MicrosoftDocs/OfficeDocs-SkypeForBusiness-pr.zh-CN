---
title: 在 Skype for Business Server 中为外部用户配置存档免责声明
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
description: 摘要：阅读本主题，了解如何为 Skype for Business Server 配置存档免责声明。
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820662"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>在 Skype for Business Server 中为外部用户配置存档免责声明
 
**摘要：** 阅读本主题，了解如何为 Skype for Business Server 配置存档免责声明。
  
如果您的组织与外部合作伙伴通信，则需要让他们知道您正在存档与外部合作伙伴的通信。 为组织部署边缘服务器并启用联盟时，会询问您是否要自动向外部合作伙伴发送存档免责声明。 
  
如果需要更改此配置，可以使用 Skype for Business Server 控制面板或 Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet。 可以从 Skype for Business Server 命令行管理程序或远程会话运行 cmdlet Windows PowerShell。
  
若要使外部用户能够与 Skype for Business Server 部署中的用户进行协作，还必须配置至少一个外部访问策略以支持外部用户访问。 有关详细信息，请参阅"管理组织的 XMPP 联盟伙伴"。 有关控制特定联盟域的访问的详细信息，请参阅"控制单个联盟域的访问"。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用控制面板启用或禁用存档免责声明

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击“联盟和外部访问”，然后单击“访问边缘配置”。
    
4. 在“访问边缘配置”选项卡上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"编辑访问边缘** 配置"中的"启用联盟和公共 **IM** 连接"下，选中或清除"向联盟伙伴发送存档免责声明"复选框以启用或禁用自动发送存档免责声明。
    
6. 单击“提交”。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>启用或禁用存档免责声明Windows PowerShell

要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


