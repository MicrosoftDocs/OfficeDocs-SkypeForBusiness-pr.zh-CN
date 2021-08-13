---
title: 部署客户端Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要：企业客户端安装方法概述Skype for Business。
ms.openlocfilehash: 592c8e3b6b29aba5ade30e61939ba2243864e45aa6079380b6c36feee60779f6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340248"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>部署客户端Skype for Business Server
 
**摘要：** 企业客户端安装方法概述Skype for Business。
  
如何向Skype for Business部署策略取决于您是购买 Skype for Business 作为 Microsoft 365 或 Office 365 计划的一部分，还是购买了 Skype for Business 的批量许可Skype for Business。 
  
- **Microsoft 365 或 Office 365** 如果你有包含Microsoft 365或Office 365安装Skype for Business，则使用的安装技术称为即点即用。 你可以让用户从 Skype for Business自行安装Microsoft 365 管理中心。 或者，也可以Skype for Business软件下载到本地网络，然后使用现有软件部署工具（如通过 Microsoft Endpoint Configuration Manager）将软件部署到用户。 有关 Skype for Business 和 Microsoft 365 Office 365 的安装信息，请参阅在 Microsoft 365 或 Office 365 中部署[Skype for Business 客户端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **批量许可** 如果你有 Skype for Business 2015 或 2016 客户端的批量许可版本，则使用的安装技术是 Windows Installer (MSI) 。 基于Windows安装程序的安装包包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。 2019 Skype for Business 2019 客户端使用即点即用安装程序。
    
本节中的主题介绍如何使用和自定义 Windows Installer，以通过常规Skype for Business向用户部署客户端。
  
> [!NOTE]
> 支持 Skype 会议Microsoft Office消息和Outlook客户端中的会议管理的 Microsoft Office 外接程序将自动随 Skype for Business 客户端一起安装。 
  
> [!NOTE]
> 安装程序Microsoft 365和Office 365安装程序不会卸载早期版本的 Lync。 客户端Skype for Business与其他 Lync 客户端并排安装。 
  
## <a name="installing-windows-clients"></a>安装Windows客户端

- [自定义Windows客户端安装Skype for Business Server](customize-windows-client-installation.md)
    
- [使用客户端配置客户端Skype for Business](configure-the-client-experience.md)
    
- [配置智能联系人列表Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安装设备客户端

- [安装和测试Windows Phone版Skype for Business](windows-phone.md)
    
- [安装和测试 Skype for Business for iOS](ios.md)
    
    
- [将 Lync VDI 插件与 Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [在客户端部署 Web 可下载Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [自定义 Mac 客户端体验Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另请参阅

[在 Skype for Business 或 Microsoft 365 部署 Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
