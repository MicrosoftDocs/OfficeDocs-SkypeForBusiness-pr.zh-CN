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
ms.localizationpriority: medium
description: 您可以使用 Windows PowerShell cmdlet 查看Get-CsNetworkInterface信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。
ms.openlocfilehash: 64e22ef14260ebadbbbe05ac1c7eff8cdf0b2ff1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585046"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>在服务器中查看网络Skype for Business Server

可以使用 **Get-CsNetworkInterface** cmdlet 和 Windows PowerShell 查看网络接口信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 

## <a name="to-view-network-interface-information"></a>查看网络接口信息

  - 若要查看网络接口信息，请在命令行管理程序Skype for Business Server以下命令，然后按 Enter：
    
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
    
    有关详细信息，请参阅 [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface)。