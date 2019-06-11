---
title: 'Lync Server 2013: 注册智能卡身份验证的用户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中注册智能卡身份验证的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-03_

通常，可通过两种方法为用户注册智能卡身份验证。较为轻松的方法涉及使用 Web 注册直接为用户注册智能卡身份验证，而较为复杂的方法涉及使用注册代理。本主题着重介绍自动注册智能卡证书。

有关作为注册代理代表用户进行注册的详细信息, 请参阅在[http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)上代表其他用户注册证书。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>为用户注册智能卡身份验证

1.  使用启用了 Lync 的用户的凭据登录到 Windows 8 工作站。

2.  启动 Internet Explorer。

3.  浏览到**证书颁发机构 Web 注册**页面 (例如https://MyCA.contoso.com/certsrv),
    
    <div>
    

    > [!NOTE]  
    > 如果您正在使用 Internet Explorer 10，则可能需要在兼容模式下查看此网站。

    
    </div>

4.  在“欢迎”**** 页面上，选择“申请证书”****。

5.  下一步，选择“高级申请”****。

6.  单击“创建并向此 CA 提交一个申请”****。

7.  在“证书模板”**** 部分下方选择“智能卡用户”****，并使用以下值完成高级证书申请：
    
      - “密钥选项”**** 确认以下设置：
        
          - 选择“创建新密钥集”**** 单选按钮
        
          - 对于“CSP”****，选择“Microsoft 基本智能卡加密提供程序”****
        
          - 对于“密钥用法”****，选择“Exchange”****（这是唯一可用选项）。
        
          - 对于“密码大小”****，输入 **2048**
        
          - 确认已选中“自动密钥容器名称”****
        
          - 取消选中其他框。
    
      - 在“其他选项”**** 下方，确认以下值：
        
          - 对于“申请格式”****，选择“CMC”****。
        
          - 对于“哈希算法”****，选择“sha1”****。
        
          - 对于“友好名称”****，输入**Smardcard Certificate**。

8.  如果您正在使用物理智能卡读取器，请将智能卡插入设备中。

9.  单击“提交”**** 提交证书申请。

10. 出现提示时，输入用于创建虚拟智能卡的 PIN。
    
    <div>
    

    > [!NOTE]  
    > 默认虚拟智能卡 PIN 值是“12345678”。

    
    </div>

11. 颁发证书后，单击“安装此证书”**** 完成注册过程。
    
    <div>
    

    > [!NOTE]  
    > 如果证书申请失败并出现错误“Web 浏览器不支持生成证书申请”，可通过三种可能的方法解决该问题： 
    > <OL>
    > <LI>
    > <P>在 Internet Explorer 中启用兼容性视图</P>
    > <LI>
    > <P>在 Internet Explorer 中启用“启用 Intranet 设置”选项</P>
    > <LI>
    > <P>在“Internet Explorer 选项”菜单的“安全”选项卡下方选择“将所有区域重置为默认级别”。</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

