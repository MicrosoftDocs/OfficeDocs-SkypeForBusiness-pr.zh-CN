---
title: 查看网络接口信息
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用 Windows PowerShell 和 Get-csnetworkinterface cmdlet 查看网络接口信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。
ms.openlocfilehash: b3f1217c53176ae2a67ba81893864e1fb3a4e384
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222763"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>为业务服务器在 Skype 中查看网络接口信息

您可以使用 Windows PowerShell 和**Get-csnetworkinterface** cmdlet 查看网络接口信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 

## <a name="to-view-network-interface-information"></a>若要查看网络接口信息

  - 若要查看网络接口信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkInterface
    
    此命令将返回类似于以下的每个网络接口信息：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    有关详细信息，请参阅[Get-csnetworkinterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。


