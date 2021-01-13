---
title: Lync Server 2010 的边缘服务器 FQDN 设置扩展器
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要定义“外部设置”下的属性，请配置以下内容：
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807092"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘服务器 FQDN 设置扩展器
 
若要定义“外部设置”下的属性，请配置以下内容：
  
如果想要为 Web 会议和 A/V 定义不同的池 FQDN 和 IP 地址，则选中“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。
  
> [!NOTE]
> 如果选择不选中单独的 FQDN 和 IP 地址的复选框，则必须为边缘服务器提供的三种服务分别提供不同的端口。 要配置的唯一完全限定域名是与访问边缘服务关联的 FQDN。 
  
如果希望 **A/V 边缘** 服务使用 NAT 地址转换和 IP 地址 (NAT) ，请选中"启用 NAT 的 A/V 边缘服务"复选框。
  
对于已启用的边缘服务，在"端口"下键入池 **FQDN** 和 **端口**
  
- 定义 **访问边缘服务** 池 FQDN 和唯一标识该服务的端口。
    
- 定义 **Web 会议** 边缘服务池 FQDN (如果未选择为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址，) 并且没有选择唯一标识该服务的端口。
    
- 定义 **A/V** 边缘服务池 FQDN (如果未选择为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址，) 并且没有选择唯一标识该服务的端口。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

