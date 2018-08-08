---
title: Windows 客户端要求和软件支持
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 摘要： 规划业务 Server Skype 时查看 Windows 客户端支持要求。
ms.openlocfilehash: 161933f5982919376dd6c9610d47c78866316cdc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984951"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 客户端要求和软件支持
 
**摘要：** 规划 Business Server Skype 时查看 Windows 客户端支持要求。
  
本节概述了业务 Windows 客户端支持 Skype 所需软件。  Office 365 安装时，会安装这些客户端，也可以在[下载的 Skype for Business 跨所有设备](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> 联机会议外接程序 Skype for Business，支持会议管理的在 Outlook 消息和协作客户端中，将自动安装与 Skype 的业务。 
  
**Skype 业务客户端和联机会议加载项所需的软件**

|**系统组件**|**受支持的版本**|
|:-----|:-----|
|Windows 操作系统  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 操作系统  <br/> Windows Server 2008 R2 或更高版本，最新 service pack  <br/> **注意：** 在 Windows Vista 或 Windows XP （任何版本） 上不支持 for Business 的 Skype 和联机会议外接程序 for Business 的 Skype。 <br/> |
|安装和更新  <br/> |管理员权限  <br/> |
|浏览器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet 浏览器  <br/>  Internet Explorer 10 Internet 浏览器 <br/> Internet Explorer 9 Internet 浏览器  <br/> Internet Explorer 8 Internet 浏览器  <br/> Internet Explorer 7 Internet 浏览器  <br/> Mozilla Firefox Web 浏览器  <br/>  Google Chrome web 浏览器  <br/>**注意：** 如果您使用的 Skype for Business 使用 Microsoft Exchange Online 和组织已经部署了身份验证 HTTP 代理，Internet Explorer 8 或更高版本，则需要。           |
|Microsoft Office 集成  <br/> | Outlook 2010 或更高版本 |
|Microsoft Exchange 集成  <br/> | Microsoft Exchange Server 2010 或更高版本  | 
   
## <a name="hardware"></a>硬件

引用了运行业务客户端 Skype 所需的硬件的 Office 365[系统要求](https://products.office.com/en-us/office-system-requirements)。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 会议应用程序和 Skype 业务 Web 应用程序 

Skype 会议应用程序和 Skype 业务 Web app 支持操作系统和浏览器的特定的组合。 有关详细信息，请参阅[计划的会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>使用必需的配置文件

如果您计划使用 Skype 业务会议功能，避免使用 Active Directory 域服务必需的配置文件登录到业务客户端 Skype。 必需的配置文件是只读的用户配置文件，因为所需的 Skype 业务会议的公钥基础结构 (PKI) 键无法保存到配置文件。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版 Skype for Business 的系统要求
 
 
业务的 Windows Phone 的 Microsoft Skype 的组织中从 smartphone 或 Windows Professional 移动设备进行连接的用户提供即时消息 (IM)、 增强的状态和电话服务。 移动设备，用户可以扩大 for Business 的 Skype。 本主题介绍规划的注意事项的 Skype 业务的 Windows Phone 其中包括确定先决条件和技术要求、 所需的组件和部署指南。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 版 Skype for Business 先决条件

以下是业务的 Windows Phone 先决条件 Skype。
  
- Windows Phone 8.1 或更高版本。
    
- Windows Phone 设备必须已安装 Microsoft 发布的最新更新。 有关详细信息，请参阅处[更新历史记录的 Windows Phone 8](https://go.microsoft.com/fwlink/p/?LinkID=281961)的 Windows Phone 8.1 一节。
    
- 该设备必须有 22 MB 的可用磁盘空间。
    
- 用户必须从运营商处开通了语音和数据资费套餐。


## <a name="see-also"></a>另请参阅

[规划会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)
  
[Skype for Business Mac 客户端要求](mac-requirements.md)

[下载 for Business 的 Skype 跨所有设备](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 系统要求](https://products.office.com/en-us/office-system-requirements)