---
title: Windows客户端要求和软件支持
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 摘要：在规划Windows时查看客户端支持Skype for Business Server。
ms.openlocfilehash: 50b0583e55c872e15e59c8510503b5b11ffc8714
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395004"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows客户端要求和软件支持
 
**摘要：** 在规划Windows时查看客户端支持Skype for Business Server。
  
本节总结了支持客户端客户端所需的Skype for Business Windows软件。 这些客户端在安装Microsoft 365或Office 365安装时安装，也可在所有设备上Skype for Business[下载客户端](https://products.office.com/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> Skype for Business 联机会议外接程序（支持从 Outlook 消息和协作客户端中管理会议）将自动随 Skype for Business。 
  
**客户端Skype for Business联机会议外接程序所需的软件**

|**系统组件**|**支持的版本**|
|:-----|:-----|
|Windows操作系统  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Service Pack 的 Windows Server 2008 R2 或更高版本  <br/> **注意** Skype for Business Vista 或 Windows XP Skype for Business版本上不支持 Windows 联机会议 (for) 。 <br/> |
|安装和更新  <br/> |管理员权限  <br/> |
|浏览器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet 浏览器  <br/>  Internet Explorer 10 Internet 浏览器 <br/> Internet Explorer 9 Internet 浏览器  <br/> Internet Explorer 8 Internet 浏览器  <br/> Internet Explorer 7 Internet 浏览器  <br/> Mozilla Firefox Web 浏览器  <br/>  Google Chrome Web 浏览器  <br/>**注意：** 如果要将 Skype for Business与 Microsoft Exchange Online，并且您的组织已部署身份验证 HTTP 代理，Internet Explorer 8或更高版本。           |
|Microsoft Office 集成  <br/> | Outlook 2010 或更高版本 |
|Microsoft Exchange 集成  <br/> | Microsoft Exchange Server 2010 或更高版本  | 
   
## <a name="hardware"></a>硬件

请参阅Microsoft 365 Office客户端所需的硬件的 Skype for Business 和 Skype for Business 要求。 [](https://products.office.com/office-system-requirements)
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype会议应用和Skype for Business Web应用 

会议Skype应用Skype for Business Web应用支持操作系统和浏览器的特定组合。 有关详细信息，请参阅 [Plan for Meetings clients (Web App and Meetings App) ](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>使用必需的配置文件

如果计划使用 Skype for Business 会议功能，请避免使用 Active Directory 域服务强制配置文件登录到 Skype for Business 客户端。 由于必需的配置文件是只读用户配置文件，因此 (会议所需的公钥基础结构) PKI Skype for Business密钥无法保存到配置文件中。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>系统要求Windows Phone版Skype for Business
 
 
Microsoft Windows Phone版Skype for Business 为通过智能手机或) 移动设备进行连接的组织用户提供即时消息 (IM) Windows Professional、增强状态和电话服务。 利用移动设备，用户可以扩展移动设备Skype for Business。 本主题介绍规划规划注意事项Windows Phone版Skype for Business包括确定先决条件和技术要求、所需组件和部署指南。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone版Skype for Business先决条件

以下是Windows Phone版Skype for Business先决条件。
  
- Windows Phone 8.1 或更高版本。
    
- Windows Phone设备必须具有 Microsoft 提供的最新更新。 有关详细信息，请参阅 Windows Phone 8 更新历史记录Windows Phone [8.1 部分](https://go.microsoft.com/fwlink/p/?LinkID=281961)。
    
- 设备必须具有 22 MB 的可用磁盘空间。
    
- 用户必须具有运营商的语音和数据计划。


## <a name="see-also"></a>另请参阅

[Plan for Meetings clients (Web App and Meetings App) ](meetings-clients.md)
  
[Skype for Business Mac 客户端要求](mac-requirements.md)

[在所有Skype for Business下载设备](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365和Office系统要求](https://products.office.com/office-system-requirements)
