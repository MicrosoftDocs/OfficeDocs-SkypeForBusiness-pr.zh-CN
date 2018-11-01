---
title: 创建注册器配置设置
TOCTitle: 创建注册器配置设置
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182601(v=OCS.15)
ms:contentKeyID: 49314661
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建注册器配置设置

 

_**上一次修改主题：** 2013-03-17_

可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：

  - **Kerberos** 这是可供客户端使用的最强大的基于密码的身份验证方案，但因为它要求有客户端连接到密钥发行中心（Kerberos 域控制器），所以通常只能供企业客户端使用。如果服务器仅验证企业客户端的身份，则此设置适用。

  - **NTLM** 这是基于密码的身份验证，可供对密码使用质询响应哈希方案的客户端使用。对于无法连接到密钥发行中心（Kerberos 域控制器）的客户端（例如，远程用户），这是唯一可用的身份验证方案。如果服务器仅验证远程用户的身份，则应选择 NTLM。

  - **证书身份验证** 这是新的身份验证方法，当服务器需要从 Lync Phone Edition 客户端、公用区域电话和 Lync 2013 中获取证书时适用。在 Lync Phone Edition 客户端上，当用户登录并通过提供个人标识号 (PIN) 成功通过身份验证后，Lync Server 2013 将为电话设置 SIP URI，并为电话设置由 Lync Server 签名的证书或标识 Joe 的用户证书（例如：SN=joe@contoso.com）。此证书用于使用注册器和 Web 服务进行身份验证。

> [!NOTE]  
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。



按照以下步骤创建新的注册器。

## 创建注册器

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“注册器”。

4.  在“注册器”页上，单击“新建”。

5.  在“选择服务”中，单击将应用此注册器的服务，然后单击“确定”。

6.  在“新建注册器设置”中，根据客户端的功能和环境支持，选择下列一项或多项：
    
      - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
      - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
      - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。

7.  单击“提交”。

