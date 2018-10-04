---
title: Lync Server 2010 的边缘计算机设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要为单个边缘服务器或边缘池中的成员计算机，请编辑边缘服务器计算机的属性，您配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: 10709088aee9d1b5ec247804122520afa3b29dee
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373383"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘计算机设置扩展器
 
若要为单个边缘服务器或边缘池中的成员计算机，请编辑边缘服务器计算机的属性，您可以配置**服务器名称和 IP 地址配置**设置：
  
- **内部名称或 FQDN**： 键入域名系统 (DNS) 中引用的计算机的名称。 
    
- **内部 IPv4 地址**： 键入该计算机内部网络接口卡 (NIC) 的 IPv4 地址。
    
- 配置与该计算机关联的**访问边缘服务****的外部 IPv4 地址**
    
    > [!IMPORTANT]
    > 如果您选择要用于边缘服务器配置的单个 IP 地址，将只能编辑访问边缘服务的外部 IPv4 地址。 其他边缘服务将共享相同的访问边缘服务的 IPv4 地址。 
  
- 如果可供编辑，则配置与该计算机关联的**Web 会议服务****外部 IPv4 地址**
    
- 如果可供编辑，则配置**A / V 边缘服务**与该计算机关联的**外部 IPv4 地址**
    
- 如果可供编辑，则配置与该计算机关联的**启用 NAT 的公共 IPv4 地址**。
    
    > [!IMPORTANT]
    > **启用 NAT 的公共 IPv4 地址**的配置属性仅可编辑如果您选择提供网络地址转换 (NAT) 的 a / V 边缘服务
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

