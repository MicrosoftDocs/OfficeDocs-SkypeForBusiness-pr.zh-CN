---
title: Lync Server 2010 的边缘计算机设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要将边缘服务器计算机的属性编辑为单个边缘服务器或作为边缘池中的成员计算机，请配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: 81fb33a2217431cd908156dab95e36cca0675f23
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604941"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘计算机设置扩展器
 
若要将边缘服务器计算机的属性编辑为单个边缘服务器或作为边缘池中的成员计算机，请配置 **服务器名称和 IP 地址配置** 设置：
  
- **内部名称或 FQDN**：键入在域名系统 (DNS) 中引用的计算机名称。 
    
- **内部 IPv4 地址**：键入该计算机内部网络接口卡 (NIC) 的 IPv4 地址。
    
- 配置与此 **计算机关联的访问** 边缘服务外部 **IPv4** 地址
    
    > [!IMPORTANT]
    > 如果选择将单个 IP 地址用于边缘服务器配置，则只能编辑访问边缘服务的外部 IPv4 地址。 其他边缘服务将共享与访问边缘服务相同的 IPv4 地址。 
  
- 如果可供编辑，则配置与此计算机关联的 **Web** 会议服务外部 **IPv4** 地址
    
- 如果可供编辑，请配置与此计算机关联的 **A/V** 边缘服务外部 **IPv4** 地址
    
- 如果可供编辑，则配置与该计算机关联的“启用 NAT 的公共 IPv4 地址”。
    
    > [!IMPORTANT]
    > 只有选择为 A/V 边缘服务提供网络地址转换 (NAT) ，启用 NAT 的公共 **IPv4** 地址的配置属性才可供编辑
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

