---
title: 'Lync Server 2013: 创建注册机构配置设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建注册机构配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-17_

可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：

  - **Kerberos**   这是可供客户端使用的最强大的基于密码的身份验证方案, 但通常仅适用于企业客户端, 因为它需要与密钥分发中心 (Kerberos 域控制器) 的客户端连接。 如果服务器仅验证企业客户端的身份，则此设置适用。

  - **NTLM**   这是基于密码的身份验证, 可供对密码使用挑战响应哈希方案的客户端使用。 对于无法连接到密钥发行中心（Kerberos 域控制器）的客户端（例如，远程用户），这是唯一可用的身份验证方案。 如果服务器仅验证远程用户的身份，则应选择 NTLM。

  - **证书身份验证**   当服务器需要从 Lync Phone Edition 客户端、公共区域手机、lync 2013 和 lync Windows 应用商店应用获取证书时, 这是新的身份验证方法。 在 Lync Phone 版客户端上, 用户登录并通过提供个人识别码 (PIN) 成功进行身份验证后, Lync Server 2013 将 SIP URI 设置到手机并设置 Lync Server 签名证书或用户证书用于向手机标识 Joe (如: SN=joe@contoso.com)。 此证书用于使用注册器和 Web 服务进行身份验证。

<div>


> [!NOTE]  
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。<BR>如果你要使用 Lync Windows 应用商店应用客户端, 则必须启用证书身份验证。



</div>

按照以下步骤创建新的注册器。

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>创建新的注册器配置设置

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。

4.  在“注册器”**** 页上，单击“新建”****。

5.  在“选择服务”**** 中，单击将应用此注册器的服务，然后单击“确定”****。

6.  在“新建注册器设置”**** 中，根据客户端的功能和环境支持，选择下列一项或多项：
    
      - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
      - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
      - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。

7.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

