---
title: Lync Server 2013：企业语音的安全性和配置先决条件
TOCTitle: 企业语音的安全性和配置先决条件
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398221(v=OCS.15)
ms:contentKeyID: 49312098
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中企业语音的安全性和配置先决条件

 

_**上一次修改主题：** 2012-10-18_

验证您的基础结构是否满足以下安全性、用户配置和特定于方案的硬件先决条件。

## 管理权限和证书基础结构

确保通过企业语音部署过程中使用的以下管理用户组和证书基础结构来配置环境。

  - 部署企业语音的管理员应当是 RTCUniversalServerAdmins 组的成员。

  - 执行配置任务的管理员必须具有足够的权限：
    
      - **CsVoiceAdministrator：** 此管理员角色可以执行语音配置任务、管理语音应用程序以及将语音策略分配给最终用户。
    
      - **CsUserAdministrator：** 此管理员角色可以管理用户属性，如为用户启用企业语音。此管理员角色还可以分配每用户策略（存档策略例外）、移动用户以及管理公用区域电话和模拟设备。
    
      - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。
    
    > [!NOTE]  
	> 通过委派，无须开放对资源的多余访问权限，即可让更多管理员参与 Lync Server 的部署
    


  - 使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。
    
    > [!NOTE]  
	> 有关 Lync Server 中证书要求的详细信息，请参阅规划文档中的<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的证书基础结构要求</a>。
    


## 用户配置

如果在前端部署期间将中介服务器与每个前端池或 Standard Edition Server 并置，则为这些服务器角色安装文件的过程中会自动配置企业语音所需的用户设置。

如果此时要执行全新的企业语音工作负荷部署，则在开始部署过程之前，为计划要对其启用企业语音的每个用户指定一个主电话号码。作为管理员，应确保此号码是唯一的。在实现之前，必须对所有主电话号码进行规范化（使用正确的格式），并使用 Lync Server 控制面板将其复制到每个用户的“线路 URI”属性。

> [!NOTE]  
> 有关企业语音部署所需的主电话号码示例，请参阅规划文档中<a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的拨号计划和规范化规则</a>的<a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的拨号计划和规范化规则</a>一节。



## 后续步骤：安装文件或配置 PSTN 连接

验证企业语音的软件先决条件和环境先决条件后，可以使用以下内容执行相应操作：

  - 安装中介服务器（如 [在 Lync Server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述），但仅当要部署独立的中介服务器或池时才执行此操作，因为如果进行并置，会在前端池或 Standard Edition Server 部署过程中安装中介服务器。

  - 或者，开始配置设置以路由企业语音用户的呼叫，如[在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)中所述。

