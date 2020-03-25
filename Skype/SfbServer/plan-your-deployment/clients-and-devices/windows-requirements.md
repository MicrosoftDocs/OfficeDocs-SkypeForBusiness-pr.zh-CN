---
title: Windows 客户端要求和软件支持
ms.author: v-lanac
author: lanachin
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
description: 摘要：在规划 Skype for Business Server 时，请查看 Windows 客户端支持要求。
ms.openlocfilehash: 39f9efcd2008dacb653538b56f2aff3fcb8b7887
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928235"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 客户端要求和软件支持
 
**摘要：** 在规划 Skype for Business Server 时，请查看 Windows 客户端支持要求。
  
本节概述了支持 Skype for Business Windows 客户端所需的软件。  这些客户端是在安装 Office 365 时安装的，也可用于在[所有设备上下载 Skype For business](https://products.office.com/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> 适用于 Skype for Business 的联机会议外接程序（它支持从 Outlook 消息传递和协作客户端中进行会议管理）通过 Skype for Business 自动安装。 
  
**Skype for Business 客户端和联机会议外接程序所需的软件**

|**系统组件**|**支持的版本**|
|:-----|:-----|
|Windows 操作系统  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 或更高版本（带最新 service pack）  <br/> **注意：** 适用于 Skype for business 的 skype for Business 和联机会议外接程序在 Windows Vista 或 Windows XP （任何版本）上不受支持。 <br/> |
|安装和更新  <br/> |管理员权限  <br/> |
|浏览器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet 浏览器  <br/>  Internet Explorer 10 Internet 浏览器 <br/> Internet Explorer 9 Internet 浏览器  <br/> Internet Explorer 8 Internet 浏览器  <br/> Internet Explorer 7 Internet 浏览器  <br/> Mozilla Firefox Web 浏览器  <br/>  Google Chrome web 浏览器  <br/>**注意：** 如果你正在使用 Skype for Business 与 Microsoft Exchange Online，并且你的组织已部署了身份验证 HTTP 代理，则需要 Internet Explorer 8 或更高版本。           |
|Microsoft Office 集成  <br/> | Outlook 2010 或更高版本 |
|Microsoft Exchange 集成  <br/> | Microsoft Exchange Server 2010 或更高版本  | 
   
## <a name="hardware"></a>硬件

有关运行 Skype for Business 客户端所需的硬件，请参阅 Office 365[系统要求](https://products.office.com/office-system-requirements)。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会议应用和 Skype for Business Web 应用 

Skype 会议应用和 Skype for Business Web 应用支持特定的操作系统和浏览器组合。 有关详细信息，请参阅[Plan For meeting 客户端（Web 应用程序和会议应用程序）](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>使用必需的配置文件

如果您计划使用 Skype for Business 会议功能，请避免使用 Active Directory 域服务强制配置文件登录 Skype for Business 客户端。 由于强制配置文件是只读用户配置文件，因此不能将 Skype for business 会议所需的公钥基础结构（PKI）密钥保存到配置文件中。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>适用于 Windows Phone 的 Skype for Business 的系统要求
 
 
适用于 Windows 的 Microsoft Skype for Business Phone 为组织中的用户提供即时消息（IM）、增强状态和电话服务，这些用户是从智能手机或 Windows 专业移动设备进行连接。 移动设备使用户能够扩展 Skype for Business 的范围。 本主题介绍了适用于 Windows Phone 的 Skype for business 的规划注意事项，其中包括确定先决条件和技术要求、必需的组件以及部署指南。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>适用于 Windows Phone 的 Skype for Business 先决条件

以下是适用于 Windows Phone 的 Skype for Business 先决条件。
  
- Windows Phone 8.1 或更高版本。
    
- Windows Phone 设备必须具有 Microsoft 提供的最新更新。 有关详细信息，请参阅[Windows phone 8 更新历史记录](https://go.microsoft.com/fwlink/p/?LinkID=281961)中的 windows phone 8.1 一节。
    
- 设备必须具有 22 MB 的可用磁盘空间。
    
- 用户必须具有来自运营商的语音和数据计划。


## <a name="see-also"></a>另请参阅

[规划会议客户端（Web 应用程序和会议应用程序）](meetings-clients.md)
  
[Skype for business on Mac 客户端要求](mac-requirements.md)

[在所有设备上下载 Skype for Business](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 系统要求](https://products.office.com/office-system-requirements)
