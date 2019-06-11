---
title: Lync Server 2013：配置反向代理以实现移动功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a>在 Lync Server 2013 中配置反向代理以实现移动功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-03-20_

如果你想要对移动设备客户端使用自动发现, 你需要修改现有的或创建反向代理的新 web 发布规则, 无论你是否更新反向代理证书上的主题备用名称列表。

如果你决定为初始 Lync Server 2013 自动发现服务请求使用 HTTPS, 并更新反向代理证书上的 "主题备用名称" 列表, 你需要将更新的公共证书分配给安全套接字层 (SSL) 侦听器的安全套接字层 (SSL) 侦听器您的反向代理。 有关所需的主题可选名称条目的详细信息, 请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。 然后, 你需要修改外部 web 服务的现有侦听器或为外部自动发现服务 URL 创建新的 web 发布规则。 如果你的前端池的外部 Lync Server 2013 Web 服务 URL 尚无 web 发布规则, 你还需要为其发布规则。

<div>


> [!NOTE]  
> 反向代理发布规则和 "自动发现" 服务可以同时为外部 web 服务和自动发现服务提供服务, 前提是分配给侦听器的证书包含两者所需的主题名称和使用者备用名称。 有关 web 侦听器和发布规则的默认配置的详细信息, 请参阅<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">设置 Lync Server 2013 的反向代理服务器</A>了解更多详细信息。



</div>

如果你决定将 HTTP 用于初始自动发现服务请求, 以便你无需更新反向代理的使用者备用名称, 你需要为端口80创建或修改 web 发布规则。

本节中的过程介绍了如何在 Microsoft Forefront 威胁管理网关2010中创建或修改 web 发布规则以进行自动发现。

<div>


> [!NOTE]  
> 这些过程假设你已安装了标准版 Forefront 威胁管理网关 (TMG) 2010。 如果您使用的是其他反向代理, 则过程与此类似, 但需要将其映射到第三方产品的文档。



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>为外部自动发现 URL 创建 web 发布规则

1.  单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。

2.  在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 指向 "**新建**", 然后单击 "网站**发布规则**"。

3.  在 "**欢迎使用新 Web 发布规则**" 页面上, 键入新发布规则的显示名称 (例如, LyncDiscoveryURL)。

4.  在 "**选择规则操作**" 页面上, 选择 "**允许**"。

5.  在 "**发布类型**" 页面上, 选择 "**发布单个网站" 或 "负载平衡器**"。

6.  在 "**服务器连接安全**" 页面上, 选择 **"使用 SSL 连接到发布的 Web 服务器或服务器场"**。

7.  在 "**内部发布详细信息**" 页面上的 "**内部网站名称**" 中, 键入你的控制器池的完全限定的域名 (FQDN) (例如, lyncdir01)。 如果要为前端池上的外部 Web 服务 URL 创建规则, 请在前端池前面键入硬件负载平衡器 (HLB) 的 VIP 地址。

8.  在 "**内部发布详细信息**" 页面上的 "**路径 (可选)**" 中, 键入** / **作为要发布的文件夹的路径, 然后选择 **"转发原始主机头**"。

9.  在 "**公共名称详细信息**" 页面上, 执行下列操作:
    
      - 在 "**接受请求**" 下, 选择 "**此域名**"。
    
      - 在 "**公共名称**" 中, 键入**lyncdiscover。**\<sipdomain\> (外部自动发现服务 URL)。 如果要为前端池上的外部 Web 服务 URL 创建规则, 请在前端池上键入外部 Web 服务的 FQDN (例如, lyncwebextpool01.contoso.com)。
    
      - 在 "**路径**" ** /** 中, 键入。

10. 在 "**选择 Web 侦听器**" 页面上的 " **web 侦听器**" 中, 选择包含已更新的公共证书的现有 SSL 侦听器。

11. 在 "**身份验证委派**" 页面上, 选择 "**无委派", 但客户端可以直接进行身份验证**。

12. 在 "**用户设置**" 页面上, 选择 "**所有用户**"。

13. 在 "**正在完成新建 Web 发布规则向导**" 页面上, 验证 Web 发布规则设置是否正确, 然后单击 "**完成**"。

14. 在 web 发布规则的 Forefront TMG 列表中, 双击刚刚添加到打开的 "**属性**" 的新规则。

15. 在 "**收件人**" 选项卡上, 执行下列操作:
    
      - 选择 **"转发原始主机标头, 而不是实际主机标头"**。
    
      - 选择**请求似乎来自 FOREFRONT TMG 计算机**。

16. 在 "**桥接**" 选项卡上, 配置以下内容:
    
      - 选择 " **Web 服务器**"。
    
      - 选择 "**将请求重定向到 HTTP 端口**", 然后键入**8080**作为端口号。
    
      - 选择 "**将请求重定向到 SSL 端口**", 然后键入**4443**作为端口号。

17. 单击“**确定**”。

18. 单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。

19. 单击 "**测试规则**" 以验证您的新规则是否设置正确。

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a>修改现有 web 发布规则以添加外部自动发现 SAN 和 URL

1.  单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 你将对你拥有的每个发布规则和侦听器重复进行修改。 通常, 这将是一个规则和一个用于前端池的侦听器, 另一个是可选控制器或控制器池 (如果已部署)。

    
    </div>

2.  在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 然后单击相应的规则。 在 "**任务**" 选项卡上, 单击 "**编辑所选规则**"。

3.  在 "**公共名称**" 选项卡上的 "**此规则适用**于" 中, 选择**以下网站的请求**。

4.  单击 "**添加**", 键入新的自动发现网站的名称 (例如, "lyncdiscover.contoso.com"), 然后单击 **"确定**"。

5.  在 "**侦听器**" 选项卡上, 单击 "**选择证书**", 然后将新证书分配给已添加的自动发现 SAN 条目。 关闭 "侦听器" 和 "Web 发布" 属性。

6.  单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。

7.  单击 "**测试规则**" 以验证您的新规则是否设置正确。

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a>为端口80创建 web 发布规则

1.  单击 "**开始**", 指向 "**程序**", 指向 " **Microsoft Forefront tmg**", 然后单击 " **Forefront tmg 管理**"。

2.  在左窗格中, 展开 "**服务器名**", 右键单击 "**防火墙策略**", 指向 "**新建**", 然后单击 "网站**发布规则**"。

3.  在 "**欢迎使用新 Web 发布规则**" 页面上, 键入新发布规则的显示名称 (例如, Lync 自动发现 (HTTP))。

4.  在 "**选择规则操作**" 页面上, 选择 "**允许**"。

5.  在 "**发布类型**" 页面上, 选择 "**发布单个网站" 或 "负载平衡器**"。

6.  在 "**服务器连接安全**" 页面上, 选择 **"使用非安全连接" 连接到已发布的 Web 服务器或服务器场**。

7.  在 "**内部发布详细信息**" 页面上的 "**内部网站名称**" 中, 在前端池前面键入硬件负载平衡器 (HLB) 的 VIP 地址。

8.  在 "**内部发布详细信息**" 页上的 "**路径 (可选)**" 中, 键入** / **作为要发布的文件夹的路径, 然后选择 **"转发原始主机头", 而不是 "内部网站名称" 字段中指定的主机头**.

9.  在 "**公共名称详细信息**" 页面上, 执行下列操作:
    
      - 在 "**接受请求**" 下, 选择 "**此域名**"。
    
      - 在 "**公共名称**" 中, 键入**lyncdiscover。**\<sipdomain\> (外部自动发现服务 URL)。
    
      - 在 "**路径**" ** /** 中, 键入。

10. 在 "**选择 Web 侦听器**" 页面上的 " **web 侦听器**" 中, 选择 web 侦听器或使用 "新建 Web 侦听器定义" 向导创建新的 web 侦听器。

11. 在 "**身份验证委派**" 页面上, 选择 "**无委派", 并且客户端无法直接进行身份验证**。

12. 在 "**用户设置**" 页面上, 选择 "**所有用户**"。

13. 在 "**正在完成新建 Web 发布规则向导**" 页面上, 验证 Web 发布规则设置是否正确, 然后单击 "**完成**"。

14. 在 web 发布规则的 Forefront TMG 列表中, 双击刚刚添加到打开的 "**属性**" 的新规则。

15. 在 "**桥接**" 选项卡上, 配置以下内容:
    
      - 选择 " **Web 服务器**"。
    
      - 选择 "**将请求重定向到 HTTP 端口**", 然后键入**8080**作为端口号。
    
      - 验证是否未选中 "**将请求重定向到 SSL 端口**"。

16. 单击“**确定**”。

17. 单击 "详细信息" 窗格中的 "**应用**" 以保存更改并更新配置。

18. 单击 "**测试规则**" 以验证您的新规则是否设置正确。

19. 验证外部自动发现服务 URL 是否未在任何其他 web 发布规则上定义。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

