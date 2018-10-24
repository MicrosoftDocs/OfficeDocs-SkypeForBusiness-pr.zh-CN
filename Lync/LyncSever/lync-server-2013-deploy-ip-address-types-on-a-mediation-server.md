---
title: Lync Server 2013：在中介服务器上部署 IP 地址类型
TOCTitle: 在中介服务器上部署 IP 地址类型
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204964(v=OCS.15)
ms:contentKeyID: 49313114
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中介服务器上部署 IP 地址类型

 

_**上一次修改主题：** 2016-07-28_

通过使用 拓扑生成器，执行以下过程中的步骤在 中介服务器上部署 IP 地址类型。

## 在中介服务器上部署 IP 地址类型

  - 在拓扑生成器中的“中介池”下，右键单击池中的服务器并选择“编辑属性”。（也可以选择服务器并从“操作”菜单中单击“编辑属性”。）

  - 在“编辑属性”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”和“启用 IPv6”，如下图所示。
    
    **用于中介服务器池的“编辑属性”对话框**
    
    ![Lync Server 的包含 FQDN 的常规属性页](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server 的包含 FQDN 的常规属性页")
    
      - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。
        
        > [!NOTE]  
		> 这是针对 IP 版本 6 (IPv6) 配置的建议选项。
        
    
      - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须为主 IP 地址输入值。
    
      - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。
    
      - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。
        
        > [!NOTE]  
		> 用以支持适用于 Lync Server 2013 的 PSTN IP 地址配置的额外网络接口卡 (NIC) 的安装不受支持。有关适用于 Lync Server 2013 的受支持的 NIC 配置的详细信息，请参阅 <a href="lync-server-2013-server-hardware-platforms.md">适用于 Lync Server 2013 的服务器硬件平台</a>。
        

