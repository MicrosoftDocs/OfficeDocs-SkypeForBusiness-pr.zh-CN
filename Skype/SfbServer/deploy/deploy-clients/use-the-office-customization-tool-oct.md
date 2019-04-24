---
title: 业务服务器 Skype 中使用 Office 自定义工具 (OCT)
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要： 如何使用 Office 自定义工具 Skype for Business 客户端。
ms.openlocfilehash: 6530199ce86914feae6b44ae8b73137263fcd6a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207900"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>业务服务器 Skype 中使用 Office 自定义工具 (OCT)
 
**摘要：** 如何使用 Office 自定义工具 Skype for Business 客户端。
  
Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。 使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。 可将该文件放在网络安装点上的 Updates 文件夹中。 在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。 可在 Updates 文件夹仅将软件更新部署期间初始安装 Office。
  
OCT 是安装的一部分，仅用于产品的批量许可版本。 通过键入以下内容运行 OCT`setup.exe /admin`中包含 Office 网络安装点的根目录的命令行在源文件。 例如，可使用以下命令：
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
管理员可以使用 OCT 创建安装程序自定义.msp 文件和可自定义的以下方面：
  
- **安装程序**用来指定客户端和默认单位名称、 其他网络安装源、 产品密钥、 最终用户许可协议的默认安装位置，显示级别、 早期版本的 Office 以删除，请运行过程中的自定义程序安装、 安全设置和安装程序属性。
    
- **功能**用于配置用户设置和自定义 Office 功能的安装方式。 管理员可以使用 OCT 指定用户的 Office 应用程序设置的初始默认值。 用户可以在安装后修改大部分设置。
    
- **其他内容**用于添加或删除文件、 添加或删除注册表项，并配置快捷方式。
    
- **Outlook**用于自定义用户的默认 Outlook 配置文件、 指定 Exchange 设置、 添加帐户、 删除帐户和导出设置，并指定发送 \ 接收组。
    
有关 OCT 的信息，请参阅[使用 OCT 自定义 Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。 请注意，此信息也适用于 Office 的更高版本。
  

