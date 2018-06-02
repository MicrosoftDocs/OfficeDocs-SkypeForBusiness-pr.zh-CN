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
description: 摘要： 企业客户端安装方法的 Skype for Business 的概述。
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546467"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 部署客户端
 
**摘要：** Overview of for Business 的 Skype 的企业客户端安装方法。
  
如何向用户部署 for Business 的 Skype 取决于是否购买 Office 365 计划的一部分的业务的 Skype 或购买 for Business 的 Skype 的批量许可的版本。 
  
- **365 office**如果您有包含 for Business 的 Skype 的 Office 365 计划，使用的安装技术称为单击即点即用。 与 Office 365，您可以让您从 Office 365 门户安装自己的 Skype for Business 的用户。 或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具，如使用 Microsoft System Center Configuration Manager 向用户部署 for Business 的 Skype。 有关 Office 365 附带的业务的 Skype 安装信息，请参阅[部署 Office 365 中的商业客户端 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **批量许可**如果您有 for Business 的 Skype 的批量许可版本，使用的安装技术是 Windows Installer (MSI)。 基于 Windows Installer 的安装包包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。
    
本节中的主题介绍如何使用和自定义 Windows Installer 部署到您的用户通过您的常规过程的业务客户端 Skype。
  
> [!NOTE]
> 联机会议外接程序的业务，支持会议管理的在 Outlook 消息和协作客户端，将自动安装与 for Business 的 Skype 的 Skype。 
  
> [!NOTE]
> Office 365 安装程序不会卸载早期版本的 Lync 或 Office Communicator。 业务客户端 Skype 与其他 Lync 或 Office Communicator 客户端安装并行。 
  
## <a name="installing-windows-clients"></a>安装 Windows 客户端

- [自定义 Windows 客户端安装中 Skype 业务服务器 2015](customize-windows-client-installation.md)
    
- [使用 for Business 的 Skype 配置客户端体验](configure-the-client-experience.md)
    
- [在 Skype for Business Server 中配置智能联系人列表](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装客户端设备

- [安装和测试业务的 Windows Phone Skype](windows-phone.md)
    
- [安装和测试适用于 iOS 的 Skype for Business](ios.md)
    
- [为业务服务器部署中 Skype 的 Skype 会议室系统](deploy-skype-room-system.md)
    
- [部署 Skype 会议室系统 v2](room-systems-v2.md)
    
- [部署 Lync VDI 插件与 Skype 业务服务器 2015](deploy-the-lync-vdi-plug-in.md)
    
- [部署业务服务器 2015 Skype Web 可下载客户端](deploy-web-downloadable-clients.md)
    
- [自定义中的业务的 Skype 的 Mac 客户端体验](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

[部署 Office 365 中的商业客户端 Skype](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)