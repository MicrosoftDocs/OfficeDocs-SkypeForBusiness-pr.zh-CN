---
title: Lync Server 2013：配置 Web 场 FQDN
TOCTitle: 配置 Web 场 FQDN
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429722(v=OCS.15)
ms:contentKeyID: 49314253
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 配置 Web 场 FQDN

 

_**上一次修改主题：** 2013-03-29_

当您在拓扑生成器中定义了 标准版 服务器、前端池、控制器或控制器池的配置时，您配置了一个外部 Web 服务完全限定的域名 (FQDN)。在登录驻留在 标准版 服务器或前端池中的客户端的过程中，将通过带内设置发送已配置的 Web 服务 FQDN。如果需要添加或更改外部 Web 服务 URL，则使用拓扑生成器按照本主题中的过程配置或重新配置 Web 服务配置。

## 配置 Web 服务的外部池 FQDN

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在拓扑生成器控制台树的“Standard Edition 前端”、“Enterprise Edition 前端”以及“控制器”下，右键单击需要编辑的池名称，然后单击“编辑属性”。

3.  在“Web 服务”部分，添加或编辑“外部 Web 服务 FQDN”。

4.  查看并调整 HTTP 和 HTTPS 的“侦听端口”。默认值为：
    
      - **侦听端口：** HTTP 8080、HTTPS 4443
    
      - **发布端口：** HTTP 80、HTTPS 443
    
    其中“侦听端口”是外部 Web 服务将配置为通过其接收来自反向代理的请求的端口，而“已发布端口”是由反向代理外部发布的端口且用于在带内设置期间与客户端进行通信。

5.  在完成添加和更新后，单击“确定”继续。

6.  右键单击 Lync Server 2013，然后单击“发布”。
    
    > [!IMPORTANT]  
    > 成功完成发布后，可能会显示一个链接，告知您需要执行其他步骤。如果单击该链接，则会打开受在 拓扑生成器中所做更改影响的服务器的列表，这需要您在列出的每台服务器上重新运行 Lync Server 部署向导以更新已添加、已删除或已更改组件的配置。


7.  为组织中的每个 标准版 服务器、前端池、控制器 或控制器池重复这些步骤。

