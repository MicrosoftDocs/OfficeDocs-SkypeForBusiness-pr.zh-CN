---
title: Lync Server 2013：企业语音部署准则
TOCTitle: 企业语音部署准则
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398694(v=OCS.15)
ms:contentKeyID: 49313511
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的企业语音部署准则

 

_**上一次修改主题：** 2012-09-21_

本主题介绍规划部署 Lync Server 2013 和 企业语音工作负荷时应考虑的先决条件及其他准则。

## 部署的先决条件

为了在部署 企业语音时获得最佳体验，请确保您的 IT 基础结构、网络和系统满足下列先决条件：

  - 已在网络上安装 Lync Server 2013 Standard Edition 或 Enterprise Edition，并且运行正常。

  - 已在外围网络中部署所有边缘服务器（包括运行 访问边缘服务、 A/V 边缘服务、 Web 会议边缘服务的边缘服务器和反向代理），并且运行正常。

  - 已创建一个或多个用户，并对这些用户启用了 Lync Server。

  - 已安装 Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新 Service Pack 或者 Microsoft Exchange Server 2010。要将 Exchange 统一消息 (UM) 与 Lync Server 集成并向客户端终结点提供丰富的通知和呼叫日志信息，必须安装其中任一组件。

  - 对于要启用 企业语音的每个用户，指定并规范化了唯一的主电话号码，并将该号码复制到了 **msRTCSIP-line** 属性。
    
    > [!NOTE]  
    > Lync Server 支持 E.164 号码和非外线直拨分机 (DID) 号码。可以用 <strong>&lt;E.164&gt;;ext=&lt;extension&gt;</strong> 格式或数字字符串形式表示非 DID 号码，同时要求专用分机号在整个企业中是唯一的。例如，可以使用 <strong>+1425550100;ext=1001</strong> 或 <strong>1001</strong> 表示专用号码 1001。使用 <strong>1001</strong> 表示时，预期此专用号码在整个企业中是唯一的。
    


  - 部署 企业语音的管理员应当是 RTCUniversalServerAdmins 组的成员。

  - 至少成功部署了 Office Communicator 2007。为使用此版本的新增功能，部署了 Lync 2013。

  - 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。

  - 安装中介服务器的每台计算机必须：
    
      - 是域的成员服务器，并已针对 Active Directory 域服务 做好准备。有关 Active Directory 域服务 的准备过程，请参阅部署文档中的 [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。
    
      - 运行以下操作系统之一：
        
           64 位版本的 Windows Server 2008 Standard 操作系统
        
           64 位版本的 Windows Server 2008 Enterprise 操作系统

  - 如果与公用电话交换网 (PSTN) 或专用交换机 (PBX) 的连接采用的是时分多路复用 (TDM) 连接，则有一个或多个 PSTN 网关可供部署。（如果连接使用的是 SIP 中继，则不需要 PSTN 网关。）

## 电源、网络或电话服务中断

如果您所在位置的电源、网络或电话服务出现中断、损坏或其他性能降低的情况，则 Lync Server 的语音、即时消息、状态和其他功能以及连接到 Lync Server 的任何设备可能无法正常工作。

## 企业语音依赖于服务器可用性以及语音客户端和硬件的可操作性

通过 Lync Server 进行的语音通信依赖于服务器软件的可用性以及语音客户端或连接到服务器软件的硬件电话设备的正常工作。

## 访问紧急服务的其他方式

对于要安装语音客户端（如运行 Lync 的 PC 或 Lync Phone Edition 设备）的位置，建议您为用户提供一个后备可选方案，以便在出现电源故障、网络连接性能降低、电话服务中断或其他可能导致 Lync Server、 Lync 或 Lync Phone Edition 设备无法运行的问题时呼叫紧急服务（如 911 或 999）。此类备用选项可能包括连接到标准公用电话交换网线路的电话或移动电话。

## 紧急呼叫和多路电话系统

对多路电话系统 (MLTS) 的使用须遵守美国（州或联邦）法律或其他国家/地区的法律，这些法律要求 MLTS 在呼叫者呼叫紧急服务（例如拨打诸如 911 或 999 之类的紧急访问号码）时，为适用的紧急服务机构提供呼叫者的电话号码、分机号和/或物理位置。在此版本中，可以将 Lync Server 配置为向紧急服务提供商提供呼叫者的物理位置，如 [在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md) 中所述。 Lync Server、 Lync 客户端和 Lync Phone Edition 设备的购买者需独自承担遵守 MLTS 法律的责任。

