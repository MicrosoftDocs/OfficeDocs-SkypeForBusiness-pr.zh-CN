---
title: Lync Server 2013：在前端服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fae6ceef3bbc9d49bbc3afcb4236c4f8ba8bfb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>在 Lync Server 2013 的前端服务器上部署 IP 地址类型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-28_

使用拓扑生成器，执行以下过程中的步骤，以在前端服务器上部署 IP 地址类型。

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

1.  在“Enterprise Edition 前端池”**** 下，右键单击池中的服务器，然后选择“编辑属性”****。（也可以选择服务器，然后单击“操作”**** 菜单中的“编辑属性”****。）

2.  在“编辑属性”**** 对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”**** 和“启用 IPv6”****，如下图所示。
    
    **前端服务器池的“编辑属性”对话框**
    
    ![前端服务器的 "编辑属性" 对话框](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "前端服务器的 "编辑属性" 对话框")
    
      - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。
        
        <div>
        

        > [!NOTE]  
        > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。

        
        </div>
    
      - **服务仅供选定 IP 地址使用**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“主 IP 地址”**** 的值。
    
      - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。
    
      - **PSTN IP 地址**。 并置中介服务器角色不支持安装额外的网络接口卡（NIC） s 来支持 Lync Server 2013 的 PSTN IP 地址配置。 有关 Lync Server 2013 支持的 NIC 配置的详细信息，请参阅[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

