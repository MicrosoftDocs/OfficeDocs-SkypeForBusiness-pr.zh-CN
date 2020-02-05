---
title: 为 Skype for Business Server 中的外部用户配置存档免责声明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：阅读本主题，了解如何配置 Skype for Business 服务器的存档免责声明。
ms.openlocfilehash: a9ffece1cefbf58b5731ce37f209733454ed1eee
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769035"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>为 Skype for Business Server 中的外部用户配置存档免责声明
 
**摘要：** 阅读本主题，了解如何配置 Skype for Business 服务器的存档免责声明。
  
如果您的组织与外部合作伙伴通信，您需要让他们知道，您会存档与他们之间的通信。 当你部署边缘服务器并为你的组织启用联盟时，系统会询问你是否要将存档免责声明自动发送给外部合作伙伴。 
  
如果需要更改此配置，您可以使用 Skype for Business 服务器控制面板或 Windows PowerShell **CsAccessEdgeConfiguration** cmdlet。 可以从 Skype for Business Server management shell 或 Windows PowerShell 的远程会话运行 cmdlet。
  
若要使外部用户能够与 Skype for Business Server 部署中的用户协作，还必须至少配置一个外部访问策略以支持外部用户访问。 有关详细信息，请参阅管理你的组织的 XMPP 联盟合作伙伴。 有关控制特定联盟域的访问的详细信息，请参阅“控制各个联盟域的访问”。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用控制面板启用或禁用存档免责声明

1. 使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。
    
4. 在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑访问边缘配置**”的“**启用联盟和公共 IM 连接**”下，选中或清除“**向联盟伙伴发送存档免责声明**”复选框以启用或禁用自动发送存档免责声明。
    
6. 单击“**提交**”。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>使用 Windows PowerShell 启用或禁用存档免责声明

要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


