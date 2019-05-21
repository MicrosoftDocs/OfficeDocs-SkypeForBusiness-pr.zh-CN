---
title: 适合于 Lync Server 2010 的服务器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: '若要编辑此计算机的属性, 请执行以下操作:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297608"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的服务器设置扩展器
 
若要编辑此计算机的属性, 请执行以下操作:
  
- 编辑此计算机的**完全限定的域名 (FQDN)** 。 此条目必须匹配在域名系统 (DNS) 中定义的计算机名称, 以及与此计算机关联的证书的 "使用者备用名称 (SAN)" 或 "使用者名称 (SN)"。
    
- 选择下列操作之一:
    
    **使用所有配置的 ip 地址**: 选择此项可使用计算机上配置的所有 ip 地址。
    
    > [!IMPORTANT]
    > 如果计算机有多个 IP 地址, 则必须注意与此计算机关联的服务将对所有服务使用所有 IP 地址。 如果侦听服务器或服务需要通信特定的 IP 地址和端口, 则该服务可能无法最佳选择要在哪个 IP 地址上进行侦听。 
  
    **将服务使用限制为选定的 IP 地址**: 如果你想要为此计算机侦听的用于从其他计算机和部署中的其他计算机和池通信的**主 ip 地址**定义特定 ip 地址, 请选择此选项。 为计算机和服务侦听通信的特定 IP 地址定义**PSTN IP 地址**, 并将通信发送到已定义的 PSTN 网关或 IP PBX。
    

