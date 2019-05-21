---
title: 查看网络接口信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以使用 Windows PowerShell 和 CsNetworkInterface cmdlet 查看网络接口信息。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279387"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>查看 Skype for Business 服务器中的网络接口信息

你可以使用 Windows PowerShell 和**CsNetworkInterface** cmdlet 查看网络接口信息。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 

## <a name="to-view-network-interface-information"></a>查看网络接口信息

  - 若要查看网络接口信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkInterface
    
    此命令针对每个网络接口返回类似于以下内容的信息:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    有关详细信息, 请参阅[CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。


