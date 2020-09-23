---
title: Lync Server 2010 的边缘计算机设置扩展器
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要将边缘服务器计算机的属性编辑为单个边缘服务器或边缘池中的成员计算机，请配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218923"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘计算机设置扩展器
 
若要将边缘服务器计算机的属性编辑为单个边缘服务器或边缘池中的成员计算机，请配置 **服务器名称和 IP 地址配置** 设置：
  
- **内部名称或 FQDN**：键入在域名系统 (DNS) 中引用的计算机名称。 
    
- **内部 IPv4 地址**：键入该计算机内部网络接口卡 (NIC) 的 IPv4 地址。
    
- 配置与此计算机关联的**访问边缘服务****外部 IPv4 地址**
    
    > [!IMPORTANT]
    > 如果选择将单个 IP 地址用于边缘服务器配置，则只能编辑访问边缘服务的外部 IPv4 地址。 其他边缘服务将与访问边缘服务共享相同的 IPv4 地址。 
  
- 如果可编辑，请配置与此计算机关联的**Web 会议服务****外部 IPv4 地址**
    
- 如果可编辑，则配置**A/V 边缘服务**与此计算机关联的**外部 IPv4 地址**
    
- 如果可供编辑，则配置与该计算机关联的“启用 NAT 的公共 IPv4 地址”****。
    
    > [!IMPORTANT]
    > 如果选择为 A/V 边缘服务提供网络地址转换 (NAT) ，则 **启用 NAT 的公用 IPv4 地址** 的 configuration 属性将仅可供编辑。
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

