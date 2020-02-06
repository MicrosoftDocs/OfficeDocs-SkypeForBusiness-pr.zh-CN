---
title: 适合于 Lync Server 2010 的 Edge Server FQDN 设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要在 "外部设置" 下定义属性，请配置以下内容：
ms.openlocfilehash: 95e55625ec698d8762832e812a79547daf4d2bcf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820054"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>适合于 Lync Server 2010 的 Edge Server FQDN 设置扩展器
 
若要在 "**外部设置**" 下定义属性，请配置以下内容：
  
如果要为 web 会议和音频/视频定义不同的池 FQDN 和 IP 地址，请选中 "**为 web 会议和 A/V 启用单独的 FQDN 和 ip 地址**" 复选框。
  
> [!NOTE]
> 如果您选择不选中单独的 FQDN 和 IP 地址的复选框，则必须为 Edge 服务器提供的三种服务提供不同的端口。 要配置的唯一完全限定的域名是与访问边缘服务关联的 FQDN。 
  
如果你希望 A/V 边缘服务使用网络地址转换（NAT） IP 地址和配置，请选中 " **a/v 边缘服务为 NAT 已启用**" 复选框。
  
对于启用的边缘服务，在 "**端口**" 下键入**池 FQDN**和端口
  
- 定义**访问边缘服务**池 FQDN 和唯一标识该服务的端口。
    
- 定义**Web 会议边缘服务**池 FQDN （如果未选中 "web 会议" 和 "A/V" 的单独 FQDN 和 IP 地址）和唯一标识该服务的端口。
    
- 定义**A/V 边缘服务**池 FQDN （如果未选中 "web 会议" 和 "A/v" 的单独 FQDN 和 IP 地址）和唯一标识该服务的端口。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

