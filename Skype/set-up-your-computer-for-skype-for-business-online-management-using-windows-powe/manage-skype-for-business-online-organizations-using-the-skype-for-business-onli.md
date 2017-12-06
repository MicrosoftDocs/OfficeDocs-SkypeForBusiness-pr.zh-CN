---
title: "管理 Skype for Business Online 的组织使用 for Business Online 连接器的 Skype"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
description: "Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant."
---

# 管理 Skype for Business Online 的组织使用 for Business Online 连接器的 Skype

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a) 中查找本文的英文版本以便参考。
  
您可以通过使用 **Get-CsTenant** 和 **Get-CsTenantLicensingConfiguration** cmdlet 来查找有关Skype for Business Online租户的信息。
  
## 管理 Skype for Business Online 租户

若要返回Skype for Business Online租户的信息，请致电[获取 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet 不带任何其他参数。
  
```
Get-CsTenant
```

要返回只需租户，名称和 ID，请使用此命令。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

运行 cmdlet[设置 CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[设置 CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602)等时需要 _TenantID_参数的值。
  
若要查找有关在Skype for Business Online管理中心中指定的租户的许可信息是否可用的信息，请使用[获取 CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

