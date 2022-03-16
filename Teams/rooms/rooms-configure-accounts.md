---
title: 为帐户配置Microsoft Teams 会议室
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 阅读本主题，了解如何为用户配置帐户Microsoft Teams 会议室 (包括Surface Hub) 和公用区域电话。
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514727"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>为帐户配置Microsoft Teams 会议室
 
本主题介绍了如何创建由 Microsoft Teams 会议室。 你的基础结构很可能属于以下配置之一：
  
- 联机部署：组织的环境完全部署在Microsoft 365 Office 365。
    
- 本地部署：组织有它控制的服务器，其中 Active Directory、Exchange和Skype for Business Server托管。 有关详细信息，请参阅使用 Microsoft Teams 会议室 [部署Skype for Business Server](with-skype-for-business-server-2015.md)
    
- 混合部署：组织混合了一些服务，其中一些托管在本地，一些通过本地或Microsoft 365联机Office 365。 使用Microsoft Teams 会议室，支持以下混合方案：
    
  - Exchange Online本地Skype for Business Server部署。
    
  - Exchange本地部署Microsoft Teams。
    
你所拥有的配置类型将影响设备设置的准备方式。
  
Microsoft Teams 会议室 Active Directory 中具有"资源帐户"，Exchange， (创建) Skype for Business。 该帐户用于访问会议日历并建立Microsoft Teams和/或Skype for Business连接。 用户可通过使用此帐户安排会议来预订此帐户。 Microsoft Teams 会议室能够加入该会议，并为与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有资源帐户，这些功能都不起作用。
  
每个资源帐户对于单个资源Microsoft Teams 会议室唯一。
  
- 必须正确配置资源帐户。
    
- 必须将基础结构配置为允许Microsoft Teams 会议室资源帐户并访问相应的Microsoft 服务。

> [!NOTE] 
> 如果使用Microsoft Teams面板，Teams 会议室资源帐户将同时登录Teams 会议室和关联的Teams面板。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。
> 
在未使用 Skype for Business混合环境中，强烈建议在 Azure Active Directory 中本机创建帐户。 如果必须使用本地 Active Directory 创建帐户，则必须在 Azure Active Directory (AAD) 连接 同步中启用密码同步，因为Microsoft Teams 会议室身份验证Microsoft 365 Office 365身份验证。 设置帐户时，请确保帐户的电子邮件地址与帐户中的 UPN 帐户的用户主体名称 (UPN) AAD。 
  
您可以将资源帐户视为用户识别为会议室或共享空间名称的帐户。 当你想要使用该空间安排会议时，你邀请资源帐户加入该会议。
  
如果已针对要安装 Exchange 的空间设置了一个资源邮箱帐户Microsoft Teams 会议室，可以将该帐户更改为 Teams 会议室 资源帐户。 完成后，只需使用该帐户登录Microsoft Teams 会议室帐户。
  
## <a name="basic-configuration"></a>基本配置

这些属性表示资源帐户使用资源帐户的最低Microsoft Teams 会议室。 资源帐户可能需要进一步设置。
  
|**属性**|**用途**|
|:-----|:-----|
|Exchange 2013 SP1 (Exchange更高版本的邮箱，或 Exchange Online)   <br/> |Exchange邮箱使资源帐户能够接收和发送邮件和会议请求，以及向用户显示会议日历Microsoft Teams 会议室。 Microsoft Teams 会议室邮箱必须是类型为"room"的资源邮箱。  <br/> |
|Skype for Business已启用  <br/> |Skype for Business启用此功能，以便使用各种Skype for Business功能，例如视频呼叫、IM 和屏幕共享。  <br/> |
|已启用密码  <br/> |必须使用密码启用资源帐户，否则它无法使用 Microsoft Teams、Exchange 或 Skype for Business Server。 必须在所有资源帐户上禁用Teams 会议室过期。   <br/> |
   
## <a name="advanced-configuration"></a>高级配置

尽管基本配置的属性允许在简单环境中设置资源帐户，但环境可能对必须满足的帐户有其他限制，Microsoft Teams 会议室才能成功使用资源帐户。
  
|**属性**|**用途**|
|:-----|:-----|
|基于证书的身份验证  <br/> |证书可能需要用于Exchange Skype for Business Server。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |

## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
