---
title: 为 Skype for Business Server 2015 部署客户端
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要： Skype 业务的企业客户端安装方法概述。
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 部署客户端
 
**摘要：**Skype 业务的企业客户端安装方法的概述。
  
如何向用户部署 Skype 业务取决于您是否购买 Skype 业务作为 Office 365 计划的一部分或购买业务的 Skype 卷许可的版。 
  
- **365 office**如果您拥有 Office 365 计划，包括业务的 Skype，使用的安装技术称为即点即用。 与 Office 365 可以让您的用户从 Office 365 提供门户网站自己安装 Skype 业务。 或者，您可以给您的用户通过将软件下载到您的本地网络并使用现有的软件部署工具，如使用 Microsoft 系统中心配置管理器部署 Skype 业务。 有关业务所附带 Office 365 的 Skype 的安装信息，请参见[部署 Office 365 中的业务客户端的 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **许可的卷**如果您有业务的 Skype 的批量许可版本，则使用的安装技术是 Windows 安装程序 (MSI)。 一个基于 Windows 安装程序的安装程序包包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。
    
本节中的主题介绍如何使用和自定义 Windows 安装程序将 Skype 业务客户端部署到您的用户通过您的正常过程。
  
> [!NOTE]
> 联机会议外接程序为 Skype 为会议从 Outlook 中的管理的支持消息传递和协作客户端会自动安装与 Skype 业务有关的业务。 
  
> [!NOTE]
> Office 365 提供安装程序不会卸载以前版本的 Lync 或 Office Communicator。 业务客户端的 Skype 与其他 Lync 或 Office Communicator 客户端安装并排比较。 
  
## <a name="installing-windows-clients"></a>安装 Windows 客户端

- [自定义 Windows 客户端安装在 Skype 业务服务器 2015](customize-windows-client-installation.md)
    
- [使用 Skype 业务配置的客户端体验](configure-the-client-experience.md)
    
- [在 Skype 为业务服务器配置智能联系人列表](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装客户端设备

- [安装并测试 Skype 业务为 Windows Phone](windows-phone.md)
    
- [安装和测试业务的 Skype 的 iOS](ios.md)
    
- [为业务服务器部署在 Skype 的 Skype 的空间系统](deploy-skype-room-system.md)
    
- [部署 Skype 的空间系统 v2](room-systems-v2.md)
    
- [插件使用 Skype Lync VDI 部署业务服务器 2015](deploy-the-lync-vdi-plug-in.md)
    
- [为业务服务器 2015年部署在 Skype 的 Web 下载客户端](deploy-web-downloadable-clients.md)
    
- [自定义业务的 Skype 的 Mac 客户端体验](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

#### 

[Skype 的为您的组织的业务客户端部署](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

