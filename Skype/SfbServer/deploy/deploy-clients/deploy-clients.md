---
title: 为业务 Server 部署 Skype 客户的端
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要： 企业客户端安装方法的 Skype for Business 的概述。
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985685"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>为业务 Server 部署 Skype 客户的端
 
**摘要：** Overview of for Business 的 Skype 的企业客户端安装方法。
  
如何向用户部署 for Business 的 Skype 取决于是否购买 Office 365 计划的一部分的业务的 Skype 或购买 for Business 的 Skype 的批量许可的版本。 
  
- **365 office**如果您有包含 for Business 的 Skype 的 Office 365 计划，使用的安装技术称为单击即点即用。 与 Office 365，您可以让您从 Office 365 门户安装自己的 Skype for Business 的用户。 或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具，如使用 Microsoft System Center Configuration Manager 向用户部署 for Business 的 Skype。 有关 Office 365 附带的业务的 Skype 安装信息，请参阅[部署 Office 365 中的商业客户端 Skype](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **批量许可**如果您有业务 2015年或 2016年客户端 Skype 的批量许可的版本，使用的安装技术是 Windows Installer (MSI)。 基于 Windows Installer 的安装包包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。 业务 2019年客户端 Skype 使用单击即点即用安装程序。
    
本节中的主题介绍如何使用和自定义 Windows Installer 部署到您的用户通过您的常规过程的业务客户端 Skype。
  
> [!NOTE]
> Skype 会议外接程序 Microsoft Office，支持会议管理的在 Outlook 消息和协作客户端中，将自动安装与 Skype 的业务客户端。 
  
> [!NOTE]
> Office 365 安装程序不会卸载早期版本的 Lync。 业务客户端 Skype 与其他 Lync 客户端安装并行。 
  
## <a name="installing-windows-clients"></a>安装 Windows 客户端

- [自定义 Windows 客户端中 Skype 业务服务器安装](customize-windows-client-installation.md)
    
- [配置 Skype for Business 的客户端体验](configure-the-client-experience.md)
    
- [在 Skype for Business Server 中配置智能联系人列表](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装客户端设备

- [Skype for Business Server 2015：安装和测试 Windows Phone 版 Skype for Business](windows-phone.md)
    
- [安装并测试 Skype for Business for iOS](ios.md)
    
- [在 Skype for Business Server 中部署 Skype 会议室系统](deploy-skype-room-system.md)
    
- [部署 Skype 会议室系统 v2](room-systems-v2.md)
    
- [部署 Lync VDI 插件与 Skype 业务服务器](deploy-the-lync-vdi-plug-in.md)
    
- [为业务服务器部署中 Skype Web 可下载的客户端](deploy-web-downloadable-clients.md)
    
- [在 Skype for Business 中自定义 Mac 客户端体验](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

[部署 Office 365 中的商业客户端 Skype](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)