---
title: 在 Skype for Business 服务器中使用 Office 自定义工具（OCT）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何将 Office 自定义工具与 Skype for Business 客户端配合使用。
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768445"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>在 Skype for Business 服务器中使用 Office 自定义工具（OCT）
 
**摘要：** 如何将 Office 自定义工具与 Skype for Business 客户端配合使用。
  
Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。 使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。 可将该文件放在网络安装点上的 Updates 文件夹中。 在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。 "更新" 文件夹仅可用于在 Office 的初始安装期间部署软件更新。
  
OCT 是设置的一部分，它仅用于批量许可的产品版本。 通过从包含 Office 源文件的`setup.exe /admin`网络安装点的根处键入命令行来运行 OCT。 例如，可使用以下命令：
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理员使用 OCT 创建安装程序自定义 .msp 文件，并可自定义以下区域：
  
- **设置**用于指定客户端的默认安装位置和默认组织名称、其他网络安装源、产品密钥、最终用户许可协议、显示级别、早期版本的 Office 以删除、在安装期间运行的自定义程序、安全设置和设置属性。
    
- **功能**用于配置用户设置和自定义 Office 功能的安装方式。 管理员可以使用 OCT 指定用户的 Office 应用程序设置的初始默认值。 安装后，用户可以修改大多数设置。
    
- **其他内容**用于添加或删除文件、添加或删除注册表项以及配置快捷方式。
    
- **Outlook**用于自定义用户的默认 Outlook 配置文件、指定 Exchange 设置、添加帐户、删除帐户和导出设置，以及指定 Send\Receive 组。
    
有关 OCT 的详细信息，请参阅[使用 OCT 自定义 Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。 请注意，此信息也适用于 Office 的更高版本。
  

