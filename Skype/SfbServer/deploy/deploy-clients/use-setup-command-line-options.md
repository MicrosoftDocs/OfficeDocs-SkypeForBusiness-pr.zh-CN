---
title: 使用 Setup command-line options Skype 业务客户端
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要： 了解 Office 安装程序中的 Setup.exe 命令行操作。
ms.openlocfilehash: d3bf2b4d867fbbb43c346f2b9572de329ec66bdc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214875"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>使用 Setup command-line options Skype 业务客户端
 
**摘要：** 了解 Office 安装程序中的 Setup.exe 命令行操作。
  
Setup.exe 命令行用于 Office 安装中的几个操作。 而不是使用安装程序命令行选项，您将通常使用 Office 自定义工具和 Config.xml 文件以进行产品安装程序和功能自定义。
  
Office Setup.exe 命令行识别下表中介绍的命令行选项。
  
**Office 安装程序命令行选项**

|**安装程序命令行选项**|**说明**|
|:-----|:-----|
|/admin  <br/> |运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。  <br/> |
|/adminfile [path]  <br/> |将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。  <br/> |
|/config [path]  <br/> |指定安装程序在安装过程中使用的 Config.xml 文件。 使用 /config 选项可指定 Config.xml 文件自定义的 Skype 对于业务安装，例如：`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。 例如，您可以使用 / 修改用于添加或删除业务功能 Skype 选项。  <br/> |
|/repair Skype  <br/> |从用户的计算机修复 for Business 的 Skype 运行安装程序。  <br/> |
|/uninstall Skype  <br/> |运行安装程序以删除用户的计算机的业务的 Skype。  <br/> |
   


