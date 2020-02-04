---
title: Lync Server 2013：企业语音部署准则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企业语音部署准则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

本主题介绍了规划部署 Lync Server 2013 和企业语音工作负荷时需要考虑的先决条件和其他指南。

<div>

## <a name="deployment-prerequisites"></a>部署先决条件

若要在部署企业语音时获得最佳体验，请确保你的 IT 基础结构、网络和系统满足以下先决条件：

  - Lync Server 2013 标准版或企业版已安装并在您的网络上运行。

  - 所有边缘服务器都在你的外围网络中部署并运行，包括具有访问边缘服务的边缘服务器、A/V 边缘服务、Web 会议边缘服务和反向代理。

  - 已为 Lync Server 创建并启用了一个或多个用户。

  - 已安装 microsoft Exchange Server 2007 Service Pack 1 （SP1）或最新 service pack 或 Microsoft Exchange Server 2010。 其中一种是将 Exchange 统一消息（UM）与 Lync Server 集成所必需的，并向客户端终结点提供丰富通知和呼叫日志信息。

  - 为要启用企业语音的每位用户指定、正常化和复制到**msRTCSIP**属性的唯一主要电话号码。
    
    <div>
    

    > [!NOTE]  
    > Lync 服务器支持 E-164 个号码和非直接向内拨号（已有）号码。 未完成的数字可以采用<STRONG> &lt;E-164&gt;、ext =&lt;extension&gt; </STRONG>或数字字符串表示，要求专用扩展在整个企业中唯一。 例如，1001的私密号码可以表示为<STRONG>+ 1425550100; ext = 1001</STRONG>，或<STRONG>1001</STRONG>。 当表示为<STRONG>1001</STRONG>时，预期是此专用号码在整个企业中是唯一的。

    
    </div>

  - 部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。

  - 至少已成功部署 Office Communicator 2007。 若要使用此版本的新功能，请部署 Lync 2013。

  - 托管密钥基础结构（MKI）使用 Microsoft 或第三方证书颁发机构（CA）基础结构进行部署和配置。

  - 安装中介服务器的每台计算机都必须：
    
      - 域的成员服务器，并准备好使用 Active Directory 域服务。 有关 Active Directory 域服务的准备过程，请参阅部署文档中的[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。
    
      - 运行下列操作系统之一：
        
          - <span></span>  
            Windows Server 2008 标准操作系统的64位版本
        
          - <span></span>  
            Windows Server 2008 企业版操作系统的64位版本

  - 如果与公共交换电话网络（PSTN）或专用分支交换（PBX）的连接是通过时间段多路复用（TDM）连接的，则可以使用一个或多个 PSTN 网关进行部署。 （如果通过 SIP 中继连接，则不需要 PSTN 网关。）

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>电源、网络或电话服务中断

如果你所在位置有停机、中断或其他电源、网络或电话服务，并且 Lync Server 和连接到 Lync 服务器的任何设备的声音、即时消息、状态和其他功能可能无法正常工作。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>企业语音取决于服务器可用性和语音客户端和硬件可操作性

与 Lync Server 的语音通信取决于服务器软件的可用性以及连接到服务器软件的语音客户端或硬件电话设备是否正常工作。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>访问紧急服务的替代方法

对于安装语音客户端的那些位置（例如，运行 Lync 客户端或 Lync Phone Edition 设备的电脑），我们建议你为用户保留一个备份选项，以便用户在出现电源故障时呼叫紧急服务（例如，911或999）、网络连接降低、电话服务中断或其他可能阻碍 Lync 服务器、Lync 或 Lync Phone Edition 设备运行的问题。 此类替代选项可能包括连接到标准的公共交换电话网络线路或手机的电话。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>紧急呼叫和多行电话系统

使用多行电话系统（MLTS）可能受美国国家/地区的美国国家/地区（如拨打紧急接入号码，如911或999）的要求 MLTS 的要求，提供呼叫者的电话号码、分机和/或物理位置的适用紧急服务的规定。 在此版本中，可将 Lync Server 配置为向紧急服务提供商提供呼叫方的物理位置，如[Lync Server 2013 中的 "紧急服务（E9-1-1）规划](lync-server-2013-planning-for-emergency-services-e9-1-1.md)" 中所述。 遵守 MLTS 法律是 Lync Server、Lync 客户端和 Lync Phone 版设备的买方的唯一责任。

</div>

</div>

<span> </span>

</div>

</div>

</div>

