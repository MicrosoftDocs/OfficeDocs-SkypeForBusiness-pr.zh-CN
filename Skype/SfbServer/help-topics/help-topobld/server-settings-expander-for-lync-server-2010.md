---
title: Lync Server 2010 中的服务器设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑此计算机的属性，则执行以下操作：
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Lync Server 2010 中的服务器设置扩展器
 
若要编辑此计算机的属性，则执行以下操作：
  
- 编辑的**完全合格的域名称 (FQDN)**为这台计算机。 此项必须与定义在域名系统 (DNS) 和主题备用名称 (SAN) 或与该计算机关联的证书使用者名称 (SN) 相匹配的计算机名。
    
- 您可以选择下列项之一：
    
    **使用所有已配置的 IP 地址**： 选择此选项可使用的计算机上配置的所有 IP 地址。
    
    > [!IMPORTANT]
    > 如果计算机具有多个 IP 地址，您必须意识到，与该计算机相关的服务将所有服务使用的所有 IP 地址。 如果侦听服务器或服务需要特定的 IP 地址和端口的通信，该服务可能无法表达哪些 IP 地址上侦听的最佳选择。 
  
    **限制到选定的 IP 地址的服务使用情况**： 选择此选项，如果您要定义特定的 IP 地址，此计算机将侦听从其他计算机中和池部署进行通信的**主 IP 地址**。 定义特定的 IP 地址的计算机和服务将侦听通信并将通信发送到定义的 PSTN 网关或 IP PBX 的**PSTN IP 地址**。
    

