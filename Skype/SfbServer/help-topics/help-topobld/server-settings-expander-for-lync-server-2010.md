---
title: 适合于 Lync Server 2010 的服务器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑该计算机的属性，请执行以下操作：
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215693"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的服务器设置扩展器
 
若要编辑该计算机的属性，请执行以下操作：
  
- 编辑该计算机的“完全限定的域名(FQDN)”****。此条目必须与域名系统 (DNS) 以及与该计算机关联的证书的使用者替代名称 (SAN) 或使用者名称 (SN) 中定义的计算机名匹配。
    
- 选择下列选项之一：
    
    **使用所有已配置的 IP 地址**：选择此选项可使用计算机上所有已配置的 IP 地址。
    
    > [!IMPORTANT]
    > 如果计算机具有多个 IP 地址，则必须意识到与该计算机关联的服务将所有的 IP 地址用于所有服务。如果某个侦听服务器或服务期待特定 IP 地址和端口的通信，则该服务可能无法选择用于侦听的最佳 IP 地址。 
  
    **将服务用途限制为所选 IP 地址**：如果要为该计算机在其上侦听来自部署中其他计算机和池的通信的“主 IP 地址”**** 定义特定的 IP 地址，则选择此选项。为计算机和服务将在其上侦听通信并将通信发送至定义的 PSTN 网关或 IP-PBX 的特定 IP 地址定义“PSTN IP 地址”****。
    

