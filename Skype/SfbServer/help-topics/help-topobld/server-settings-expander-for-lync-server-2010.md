---
title: 适合于 Lync Server 2010 的服务器设置扩展器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑该计算机的属性，请执行以下操作：
ms.openlocfilehash: 4b05c52d92d3702c76afd6c7b682c1c9ffda7ab9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219203"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的服务器设置扩展器
 
若要编辑该计算机的属性，请执行以下操作：
  
- 编辑**完全限定域名 (FQDN)** 为此计算机。 此条目必须与它被定义在域名系统 (DNS) 和使用者替代名称 (SAN) 或使用者名称 (SN) 与该计算机关联的证书匹配的计算机名称。
    
- 您选择下列选项之一：
    
    **使用所有已配置的 IP 地址**： 选择此选项可在计算机上使用所有已配置的 IP 地址。
    
    > [!IMPORTANT]
    > 如果计算机有多个 IP 地址，必须注意与该计算机关联的服务，将使用的所有服务的所有 IP 地址。 如果侦听服务器或服务预期的特定的 IP 地址和端口的通信，服务可能不进行侦听的 IP 地址的最佳选择。 
  
    **将服务使用率限制为所选的 IP 地址**： 选择此选项，如果您想要定义特定 IP 地址从其他计算机和池部署中的通信将侦听此计算机的**主 IP 地址**。 为特定的 IP 地址的计算机和服务将侦听的通信和发送到定义 PSTN 网关或 IP PBX 的通信，定义**PSTN IP 地址**。
    

