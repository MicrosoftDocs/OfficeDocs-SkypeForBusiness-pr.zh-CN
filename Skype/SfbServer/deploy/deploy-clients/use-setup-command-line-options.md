---
title: 将设置命令行选项与 Skype for Business 客户端配合使用
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要：了解 Office 安装程序中的 setup.exe 命令行操作。
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768625"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>将设置命令行选项与 Skype for Business 客户端配合使用
 
**摘要：** 了解 Office 安装程序中的 setup.exe 命令行操作。
  
Setup.exe 命令行用于 Office 安装中的几个操作。 通常使用 Office 自定义工具和 Config.xml 文件进行产品设置和功能自定义，而不是使用设置命令行选项。
  
Office Setup.exe 命令行识别下表中介绍的命令行选项。
  
**Office 安装程序命令行选项**

|**安装程序命令行选项**|**说明**|
|:-----|:-----|
|/admin  <br/> |运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。  <br/> |
|/adminfile [path]  <br/> |将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。  <br/> |
|/config [path]  <br/> |指定安装程序在安装过程中使用的 Config.xml 文件。 使用/config 选项指定为 Skype for Business 安装自定义的 Config.xml 文件，例如：`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。 例如，您可以使用/modify 选项添加或删除 Skype for Business 功能。  <br/> |
|/repair Skype  <br/> |从用户的计算机运行安装程序以修复 Skype for Business。  <br/> |
|/uninstall Skype  <br/> |运行安装程序以从用户的计算机中删除 Skype for Business。  <br/> |
   


