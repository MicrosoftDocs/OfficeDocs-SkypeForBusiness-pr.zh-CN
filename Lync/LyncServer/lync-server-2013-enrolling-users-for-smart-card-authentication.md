---
title: Lync Server 2013：为用户注册智能卡身份验证
description: Lync Server 2013：为用户注册智能卡身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558468"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中为用户注册智能卡身份验证

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-03_

为用户注册智能卡身份验证的方法通常有两种。 更简单的方法是让用户使用 web 注册直接注册智能卡身份验证，而更复杂的方法涉及使用注册代理。 本主题重点介绍了智能卡证书的自注册。

有关作为注册代理代表用户注册的详细信息，请参阅在上代表其他用户注册证书 [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) 。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

1.  使用启用了 Lync 的用户的凭据登录到 Windows 8 工作站。

2.  启动 Internet Explorer。

3.  浏览到 " **证书颁发机构 Web 注册** " 页 (https://MyCA.contoso.com/certsrv) 例如，
    
    <div>
    

    > [!NOTE]  
    > 如果使用的是 Internet Explorer 10，则可能需要在兼容模式下查看此网站。

    
    </div>

4.  在 " **欢迎** " 页面上，选择 " **申请证书**"。

5.  接下来，选择 " **高级请求**"。

6.  选择 " **创建并向此 CA 提交一个请求**"。

7.  在 "**证书模板**" 部分下选择 "**智能卡用户**"，并使用以下值完成高级证书请求：
    
      - **主要选项** 确认他的以下设置：
        
          - 选择 " **创建新密钥集** " 单选按钮
        
          - 对于 **CSP**，选择 **Microsoft 基本智能卡加密提供程序**
        
          - 若要 **使用密钥**，请选择 " **Exchange** (这是唯一可) 的选项。
        
          - 对于 **密钥大小**，请输入 **2048**
        
          - 确认已选择 " **自动密钥容器名称** "
        
          - 将其他框保留为未选中状态。
    
      - 在 " **其他选项** " 下，确认以下值：
        
          - 对于 **请求格式** ，请选择 **CMC**。
        
          - 对于 **哈希算法** ，请选择 " **sha1**"。
        
          - 对于 **友好名称** ，请输入 **Smardcard 证书**。

8.  如果使用的是物理智能卡读取器，请将智能卡插入设备中。

9.  单击 " **提交** " 以提交证书请求。

10. 出现提示时，请输入用于创建虚拟智能卡的 PIN。
    
    <div>
    

    > [!NOTE]  
    > 默认的虚拟智能卡 PIN 值为 "12345678"。

    
    </div>

11. 颁发证书后，单击 " **安装此证书** " 以完成注册过程。
    
    <div>
    

    > [!NOTE]  
    > 如果您的证书请求失败，并出现错误 "此 Web 浏览器不支持生成证书请求"，则有三种可能的方法可以解决此问题： 
    > <OL>
    > <LI>
    > <P>在 Internet Explorer 中启用兼容性视图</P>
    > <LI>
    > <P>启用 Internet Explorer 中的 "打开 Intranet 设置" 选项</P>
    > <LI>
    > <P>在 "Internet Explorer 选项" 菜单中的 "安全" 选项卡下，选择 "将所有区域重置为默认级别" 设置。</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

