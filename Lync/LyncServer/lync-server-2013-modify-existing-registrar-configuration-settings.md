---
title: 修改现有的注册器配置设置
TOCTitle: 修改现有的注册器配置设置
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182566(v=OCS.15)
ms:contentKeyID: 49313860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改现有的注册器配置设置

 

_**上一次修改主题：** 2012-11-01_

可以使用注册器配置代理服务器身份验证协议。有关可用协议的信息，请参阅[创建注册器配置设置](lync-server-2013-create-registrar-configuration-settings.md)。

> [!NOTE]  
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。



按照以下步骤修改现有的注册器。

## 修改现有的注册器

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“注册器”。

4.  在“注册器”页上，单击某个服务，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑注册器设置”中，根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
      - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
      - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
      - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。

6.  单击“提交”。

