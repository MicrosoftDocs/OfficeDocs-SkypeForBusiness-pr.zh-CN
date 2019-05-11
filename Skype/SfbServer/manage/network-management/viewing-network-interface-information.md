---
title: 查看网络接口信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用 Windows PowerShell 和 Get-csnetworkinterface cmdlet 查看网络接口信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。
ms.openlocfilehash: 5460ee66d61c43925de1ec74778ea8920f79df25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910261"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="a83c9-104">为业务服务器在 Skype 中查看网络接口信息</span><span class="sxs-lookup"><span data-stu-id="a83c9-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="a83c9-105">您可以使用 Windows PowerShell 和**Get-csnetworkinterface** cmdlet 查看网络接口信息。</span><span class="sxs-lookup"><span data-stu-id="a83c9-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="a83c9-106">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a83c9-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="a83c9-107">若要查看网络接口信息</span><span class="sxs-lookup"><span data-stu-id="a83c9-107">To view network interface information</span></span>

  - <span data-ttu-id="a83c9-108">若要查看网络接口信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="a83c9-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="a83c9-109">此命令将返回类似于以下的每个网络接口信息：</span><span class="sxs-lookup"><span data-stu-id="a83c9-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="a83c9-110">有关详细信息，请参阅[Get-csnetworkinterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。</span><span class="sxs-lookup"><span data-stu-id="a83c9-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


