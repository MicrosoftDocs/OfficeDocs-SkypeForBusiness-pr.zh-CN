---
title: 在 Skype for Business Server 2015 中使用 Office 自定义工具 (OCT)
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要： 如何使用 Office 自定义工具 Skype 业务客户端。
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中使用 Office 自定义工具 (OCT)
 
**摘要：**如何使用 Office 自定义工具 Skype 业务客户端。
  
Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。 使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。 可将该文件放在网络安装点上的 Updates 文件夹中。 在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。 更新文件夹可用于仅在初始安装 Office 的过程中部署软件更新。
  
OCT 是安装程序的一部分，仅用于该产品的批量许可版本。 键入运行 OCT`setup.exe /admin`在命令行中包含办公室网络安装点根目录下的源文件。 例如，可使用以下命令：
  
 `\\server\share\Office15\setup.exe /admin`
  
管理员使用 OCT 创建的安装程序自定义.msp 文件并可以自定义以下几个方面：
  
- **安装程序**用于在客户端与默认的组织名称、 安装其他网络资源、 产品密钥、 最终用户许可协议中指定默认的安装位置，显示级别、 早期 Office 版本的删除，期间运行的自定义程序安装、 安全设置和安装程序属性。
    
- **功能**用来配置用户设置以及如何自定义 Office 功能的安装方式。 管理员可以使用 OCT 可以指定 Office 应用程序设置为用户的初始默认值。 安装完成后，用户可以修改大部分设置。
    
- **其他内容**用于添加或删除文件，添加或删除注册表项和配置快捷方式。
    
- **Outlook**用于自定义默认用户的 Outlook 配置文件，指定交换设置、 添加帐户，删除帐户和导出设置，并指定发送 \ 接收组。
    
OCT 有关的信息，请参阅[使用 OCT 可以自定义 Office 2013](https://technet.microsoft.com/library/cc179132.aspx)。 请注意，此信息也适用于 Office 2016。
  

