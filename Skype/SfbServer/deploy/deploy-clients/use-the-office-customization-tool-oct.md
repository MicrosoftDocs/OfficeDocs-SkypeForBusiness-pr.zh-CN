---
title: 在 Skype for Business Server 中Office OCT (OCT) 工具Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何将自定义Office与 Skype for Business 一起使用。
ms.openlocfilehash: d1fa867326ec1c613793831253dc693783132b57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587834"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>在 Skype for Business Server 中Office OCT (OCT) 工具Skype for Business Server
 
**摘要：** 如何将自定义Office与 Skype for Business 一起使用。
  
Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。 使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。 可将该文件放在网络安装点上的 Updates 文件夹中。 在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。 Updates 文件夹只能用于在初始安装更新期间部署Office。
  
OCT 是安装程序的一部分，仅用于产品的批量许可版本。 通过从网络安装点的根目录键入包含此子源文件的网络安装点中的命令行， `setup.exe /admin` 可以Office OCT。 例如，可使用以下命令：
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理员可以使用 OCT 创建安装程序自定义 .msp 文件，并可以自定义以下区域：
  
- **设置** 用于指定客户端的默认安装位置和默认组织名称、其他网络安装源、产品密钥、最终用户许可协议、显示级别、要删除的 Office 的早期版本、安装期间运行的自定义程序、安全设置和安装程序属性。
    
- **功能** 用于配置用户设置和自定义Office安装方式。 管理员可以使用 OCT 为用户指定Office应用程序设置的初始默认值。 用户可以在安装后修改大多数设置。
    
- **其他内容** 用于添加或删除文件、添加或删除注册表项以及配置快捷方式。
    
- **Outlook** 用于自定义用户的默认Outlook配置文件、指定Exchange设置、添加帐户、删除帐户和导出设置，以及指定发送\接收组。
    
有关 OCT 的信息，请参阅使用[OCT 自定义 Office 2013。](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) 请注意，此信息也适用于更高版本的 Office。
