---
title: 查看网络接口信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以使用 Windows PowerShell 和 CsNetworkInterface cmdlet 查看网络接口信息。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817348"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>查看 Skype for Business 服务器中的网络接口信息

你可以使用 Windows PowerShell 和**CsNetworkInterface** cmdlet 查看网络接口信息。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 

## <a name="to-view-network-interface-information"></a>查看网络接口信息

  - 若要查看网络接口信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkInterface
    
    此命令针对每个网络接口返回类似于以下内容的信息：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    有关详细信息，请参阅[CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。


