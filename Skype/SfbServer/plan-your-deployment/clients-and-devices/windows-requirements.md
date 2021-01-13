---
title: Windows 客户端要求和软件支持
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 摘要：在规划 Skype for Business Server 时查看 Windows 客户端支持要求。
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816062"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 客户端要求和软件支持
 
**摘要：** 在规划 Skype for Business Server 时查看 Windows 客户端支持要求。
  
本部分总结了支持 Skype for Business Windows 客户端所需的软件。 这些客户端在安装 Microsoft 365 或 Office 365 时安装，也可在所有设备上下载[Skype for Business。](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
> [!NOTE]
> Skype for Business 联机会议外接程序支持从 Outlook 消息和协作客户端内管理会议，它随 Skype for Business 一起自动安装。 
  
**Skype for Business 客户端和联机会议外接程序所需的软件**

|**系统组件**|**支持的版本**|
|:-----|:-----|
|Windows 操作系统  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 或更高版本（最新 Service Pack）  <br/> **注意：** Skype for Business 和 Skype for Business 联机会议外接程序在任何版本的 Windows Vista 或 Windows XP (都) 。 <br/> |
|安装和更新  <br/> |管理员权限  <br/> |
|浏览器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet 浏览器  <br/>  Internet Explorer 10 Internet 浏览器 <br/> Internet Explorer 9 Internet 浏览器  <br/> Internet Explorer 8 Internet 浏览器  <br/> Internet Explorer 7 Internet 浏览器  <br/> Mozilla Firefox Web 浏览器  <br/>  Google Chrome Web 浏览器  <br/>**注意：** 如果你将 Skype for Business 与 Microsoft Exchange Online 组织部署了身份验证 HTTP 代理，Internet Explorer 8或更高版本。           |
|Microsoft Office 集成  <br/> | Outlook 2010 或更高版本 |
|Microsoft Exchange 集成  <br/> | Microsoft Exchange Server 2010 或更高版本  | 
   
## <a name="hardware"></a>硬件

请参阅 Microsoft 365 和 Office [System](https://products.office.com/office-system-requirements) 要求，了解运行 Skype for Business 客户端所需的硬件。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会议应用和 Skype for Business Web App 

Skype 会议应用和 Skype for Business Web App 支持操作系统和浏览器的特定组合。 有关详细信息，请参阅 ["规划 Web 应用和 (会议应用程序的会议 ](meetings-clients.md)客户端) 。 
  
## <a name="using-mandatory-profiles"></a>使用必需的配置文件

如果计划使用 Skype for Business 会议功能，请避免使用 Active Directory 域服务强制配置文件登录到 Skype for Business 客户端。 由于必需的配置文件是只读用户配置文件，因此 (Skype for Business) 所需的公钥基础结构) PKI 基础结构密钥无法保存到配置文件中。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>适用于 Windows Phone 的 Skype for Business 的系统要求
 
 
Microsoft Skype for Business for Windows Phone 为组织中从智能手机或 Windows Professional 移动设备 (的用户提供即时消息、即时消息) 、增强状态和电话服务。 移动设备使用户能够扩展 Skype for Business 的覆盖范围。 本主题介绍适用于 Windows Phone 的 Skype for Business 的规划注意事项，其中包括确定先决条件和技术要求、所需组件和部署指南。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>适用于 Windows Phone 先决条件的 Skype for Business

以下是适用于 Windows Phone 的 Skype for Business 先决条件。
  
- Windows Phone 8.1 或更高版本。
    
- Windows Phone 设备必须具有 Microsoft 提供的最新更新。 有关详细信息，请参阅 Windows Phone 8 更新历史记录中的 [Windows Phone 8.1 部分](https://go.microsoft.com/fwlink/p/?LinkID=281961)。
    
- 设备必须具有 22 MB 的可用磁盘空间。
    
- 用户必须具有运营商的语音和数据计划。


## <a name="see-also"></a>另请参阅

[规划 Web 应用和 (会议应用程序的会议) ](meetings-clients.md)
  
[Mac 上的 Skype for Business 客户端要求](mac-requirements.md)

[在所有设备上下载 Skype for Business](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 和 Office 系统要求](https://products.office.com/office-system-requirements)
