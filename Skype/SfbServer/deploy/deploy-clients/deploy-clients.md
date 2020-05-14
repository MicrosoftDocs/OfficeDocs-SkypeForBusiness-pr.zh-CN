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
description: 摘要：适用于 Skype for business 的企业客户端安装方法概述。
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220642"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>为 Skype for Business Server 部署客户端
 
**摘要：** Skype for business 的企业客户端安装方法概述。
  
如何将 Skype for Business 部署到用户取决于您是在 Microsoft 365 还是 Office 365 计划中购买了 Skype for Business，还是购买了批量许可版本的 Skype for Business。 
  
- **Microsoft 365 或 Office 365**如果你拥有包含 Skype for Business 的 Microsoft 365 或 Office 365 计划，则使用的安装技术称为即点即用。 你可以让你的用户从 Microsoft 365 管理中心为自己安装 Skype for Business。 或者，您可以通过将软件下载到本地网络，然后使用您现有的软件部署工具（如 Microsoft 终结点配置管理器），将 Skype for Business 部署到用户。 有关 Microsoft 365 和 Office 365 附带的 Skype for business 的安装信息，请参阅[在 microsoft 365 或 office 365 中部署 skype For business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **批量许可**如果你拥有批量许可版本的 Skype for Business 2015 或2016客户端，则使用的安装技术是 Windows Installer （MSI）。 基于 Windows Installer 的安装包包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。 Skype for Business 2019 客户端使用即点即用安装程序。
    
本节中的主题介绍如何使用和自定义 Windows Installer，以通过常规过程将 Skype for Business 客户端部署到用户。
  
> [!NOTE]
> Microsoft Office 的 Skype 会议外接程序（支持从 Outlook 消息和协作客户端中进行会议管理）通过 Skype for Business 客户端自动安装。 
  
> [!NOTE]
> Microsoft 365 和 Office 365 安装程序不会卸载早期版本的 Lync。 Skype for Business 客户端将与其他 Lync 客户端并行安装。 
  
## <a name="installing-windows-clients"></a>安装 Windows 客户端

- [在 Skype for Business Server 中自定义 Windows 客户端安装](customize-windows-client-installation.md)
    
- [配置 Skype for Business 的客户端体验](configure-the-client-experience.md)
    
- [在 Skype for Business Server 中配置智能联系人列表](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装设备客户端

- [安装和测试适用于 Windows Phone 的 Skype for Business](windows-phone.md)
    
- [安装和测试适用于 iOS 的 Skype for Business](ios.md)
    
    
- [使用 Skype for Business Server 部署 Lync VDI 插件](deploy-the-lync-vdi-plug-in.md)
    
- [在 Skype for Business Server 中部署 Web 可下载客户端](deploy-web-downloadable-clients.md)
    
- [在 Skype for Business 中自定义 Mac 客户端体验](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

[在 Microsoft 365 或 Office 365 中部署 Skype for Business 客户端](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
