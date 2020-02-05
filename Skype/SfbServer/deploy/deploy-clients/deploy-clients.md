---
title: 为 Skype for Business Server 部署客户端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要： Skype for business 的企业客户端安装方法概述。
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768725"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>为 Skype for Business Server 部署客户端
 
**摘要：** Skype for business 的企业客户端安装方法概述。
  
如何将 Skype for business 部署到你的用户取决于你是在 Office 365 计划中购买的 Skype for business 还是你购买了批量许可版本的 Skype for business。 
  
- **Office 365**如果您有包含 Skype for Business 的 Office 365 计划，则使用的安装技术称为即点即用。 通过 Office 365，你可以让你的用户从 Office 365 门户为自己安装 Skype for business。 或者，你可以通过将软件下载到本地网络，然后使用现有软件部署工具（如 Microsoft 终结点配置管理器），将 Skype for business 部署到你的用户。 有关 Office 365 附带的 Skype for business 的安装信息，请参阅[在 office 365 中部署 skype for business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **批量许可**如果你拥有 Skype for Business 2015 或2016客户端的批量许可版本，则使用的安装技术是 Windows Installer （MSI）。 基于 Windows Installer 的安装程序包由多个 MSI 文件组成。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。 Skype for Business 2019 客户端使用即点即用安装程序。
    
本部分中的主题介绍如何使用和自定义 Windows 安装程序，以便通过常规过程将 Skype for Business 客户端部署到用户。
  
> [!NOTE]
> 用于 Microsoft Office 的 Skype 会议加载项（支持来自 Outlook 消息和协作客户端的会议管理）将自动与 Skype for Business 客户端一起安装。 
  
> [!NOTE]
> Office 365 安装程序不会卸载以前版本的 Lync。 Skype for Business 客户端与其他 Lync 客户端并排安装。 
  
## <a name="installing-windows-clients"></a>安装 Windows 客户端

- [在 Skype for Business 服务器中自定义 Windows 客户端安装](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [在 Skype for Business Server 中配置智能联系人列表](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装设备客户端

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [通过 Skype for Business 服务器部署 Lync VDI 插件](deploy-the-lync-vdi-plug-in.md)
    
- [在 Skype for Business 服务器中部署 Web 可下载的客户端](deploy-web-downloadable-clients.md)
    
- [在 Skype for Business 中自定义 Mac 客户端体验](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

[在 Office 365 中部署 Skype for Business 客户端](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
