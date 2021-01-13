---
title: 查看网络接口信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 可以使用 Windows PowerShell 和 Get-CsNetworkInterface cmdlet 查看网络接口信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815132"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>在 Skype for Business Server 中查看网络接口信息

可以使用 Windows PowerShell **和 Get-CsNetworkInterface** cmdlet 查看网络接口信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 

## <a name="to-view-network-interface-information"></a>查看网络接口信息

  - 若要查看网络接口信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：
    
        Get-CsNetworkInterface
    
    对于每个网络接口，此命令返回的信息类似于以下内容：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    有关详细信息，请参阅 [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。


