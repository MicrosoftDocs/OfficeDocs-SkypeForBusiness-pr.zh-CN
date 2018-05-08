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
description: 摘要： 规划业务服务器 2015 Skype 时查看 Windows 客户端支持要求。
ms.openlocfilehash: 3dac3a8e15e53cec5605aa2b003150f491d8f2b5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 客户端要求和软件支持
 
**摘要：**规划业务服务器 2015 Skype 时查看 Windows 客户端支持要求。
  
本节概述了业务 2015年和 2016 Windows 客户端支持 Skype 所需软件。
  
Office 365 安装时，会安装这些客户端，也可以在[下载的 Skype for Business 跨所有设备](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> 联机会议外接程序 Skype for Business，支持会议管理的在 Outlook 消息和协作客户端中，将自动安装与 Skype 的业务。 
  
**有关业务和联机会议加载项的 Skype for Business 的 Skype 所需软件**


|**系统组件**|**受支持的版本**|
|:-----|:-----|
|Windows 操作系统  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8  <br/> Windows 7 操作系统  <br/> 最新 service pack 的 Windows Server 2008 R2  <br/> **注意：**在 Windows Vista 或 Windows XP （任何版本） 上不支持 for Business 的 Skype 和联机会议外接程序 for Business 的 Skype。 <br/> |
|安装和更新  <br/> |管理员权限  <br/> |
|浏览器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet 浏览器  <br/>  Internet Explorer 10 Internet 浏览器 <br/> Internet Explorer 9 Internet 浏览器  <br/> Internet Explorer 8 Internet 浏览器  <br/> Internet Explorer 7 Internet 浏览器  <br/> Mozilla Firefox Web 浏览器  <br/> **注意：**如果您使用的 Skype for Business 使用 Microsoft Exchange Online 和组织已经部署了身份验证 HTTP 代理，Internet Explorer 8 或更高版本，则需要。           |
|Microsoft Office 集成  <br/> |要获得全套集成功能：  <br/> • Outlook 2016 消息和协作客户端  <br/> • Outlook 2013 消息和协作客户端  <br/> • Outlook 2010 消息和协作客户端  <br/> |
|Microsoft Exchange 集成  <br/> |• Microsoft Exchange Server 2016  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2010  <br/> |
   
## <a name="hardware"></a>硬件

引用了运行业务客户端 Skype 所需的硬件的 Office 365[系统要求](https://products.office.com/en-us/office-system-requirements)。
  
## <a name="skype-for-business-web-app-browsers"></a>Skype 的业务 Web 应用程序浏览器

Skype 业务 Web app 支持操作系统和浏览器的特定的组合。 有关详细信息，请参阅[计划的会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)。 
  
## <a name="microsoft-office-supportability"></a>Microsoft Office 可支持性

Skype 业务服务器 2015年客户端支持与各种版本的 Microsoft Office 集成。
  
- Skype 的业务集成功能支持 Outlook 2016、 Outlook 2013 和 Outlook 2010。
    
- Microsoft Exchange Server 2016、 Microsoft Exchange Server 2013 和 Microsoft Exchange Server 2010 支持的业务集成功能的 Skype。
    
- 联机会议外接程序 for Business 的 Skype 支持与 Office 2016、 Office 2013 和 Microsoft Office 2010。
    
## <a name="using-mandatory-profiles"></a>使用必需的配置文件

如果您计划使用 Skype 业务会议功能，避免使用 Active Directory 域服务必需的配置文件登录到业务客户端 Skype。 必需的配置文件是只读的用户配置文件，因为所需的 Skype 业务会议的公钥基础结构 (PKI) 键无法保存到配置文件。 
  
## <a name="macintosh-operating-systems"></a>Macintosh 操作系统

[Skype for Mac 客户端要求 Business](mac-requirements.md)中详细 for Mac 支持要求的 Business Skype。
  
## <a name="see-also"></a>另请参阅

#### 

[规划会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)
  
[Skype for Business Mac 客户端要求](mac-requirements.md)
#### 

[下载 for Business 的 Skype 跨所有设备](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 系统要求](https://products.office.com/en-us/office-system-requirements)

