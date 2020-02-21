---
title: Lync Server 2013：在中介服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7705da8beee8f6ee45d74fbdbb6eb03180234a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>在 Lync server 2013 的中介服务器上部署 IP 地址类型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-28_

使用拓扑生成器，执行以下过程中的步骤，以在中介服务器上部署 IP 地址类型。

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

  - 在拓扑生成器中，在 "**中介池**" 下，右键单击池内的服务器，然后选择 "**编辑属性**"。 （或者，选择服务器，然后从 "**操作**" 菜单中单击 "**编辑属性**"。）

  - 在“编辑属性”**** 对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”**** 和“启用 IPv6”****，如下图所示。
    
    **用于中介服务器池的“编辑属性”对话框**
    
    ![具有 FQDN 的 "Lync Server 常规属性" 页](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "具有 FQDN 的 "Lync Server 常规属性" 页")
    
      - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。
        
        <div>
        

        > [!NOTE]  
        > 这是用于 IP 版本 6 (IPv6) 配置的建议选项。

        
        </div>
    
      - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须为主 IP 地址输入值。
    
      - **主 IP 地址**。输入服务器将用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。输入的 IP 地址必须与选定地址类型的格式匹配。
    
      - **PSTN IP 地址**。 当中介服务器是独立的时，定义 PSTN IP 地址。 该地址必须符合选择的地址类型的格式。
        
        <div>
        

        > [!NOTE]  
        > 并置中介服务器角色不支持安装额外的网络接口卡（NIC） s 来支持 Lync Server 2013 的 PSTN IP 地址配置。 有关 Lync Server 2013 支持的 NIC 配置的详细信息，请参阅<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

