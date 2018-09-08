---
title: 为 Skype for Business 服务器创建 DNS 记录
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 摘要： 了解如何配置 DNS 和业务服务器创建 DNS 记录的 Skype 安装。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 0090cdd19d0bef8b73ad79bd8c7f0d36a5044a48
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885457"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>为 Skype for Business 服务器创建 DNS 记录
 
**摘要：** 了解如何配置 DNS 和业务服务器创建 DNS 记录的 Skype 安装。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
为业务服务器可以正常运行的 Skype，大量域名系统 (DNS) 设置必须就地。 从而使客户端知道该如何访问服务以及让服务器知道相互之间的情况。 每个部署仅需完成一次此类设置，因为在您分配 DNS 条目之后，该条目便在整个域中可用。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 创建 DNS 记录是 8 个步骤中的第 5 步。 有关规划 DNS 的详细信息，请参阅[环境要求 Skype 业务服务器](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[服务器要求的业务服务器 2019 Skype](../../../SfBServer2019/plan/system-requirements.md)。
  
> [!IMPORTANT]
> 请注意，这只是一个有关如何在 Windows Server DNS 环境中创建 DNS 记录的示例。 有许多其他所需的 Skype 业务服务器的 DNS 项，创建 DNS 记录的过程取决于您使用您的组织中管理 DNS 系统。 有关 DNS 要求的完整列表，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概述图表](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>配置 DNS

DNS 记录所需的 Skype 业务服务器能正常工作，可以访问用户。
  
在此示例中，我们使用名为 pool.contoso.local 并经过 DNS 负载平衡的 FQDN。 此池包含业务 Server Enterprise edition 运行 Skype 的三个服务器。 Standard Edition 前端服务器仅可包含一台服务器。 如果使用 Standard Edition，在引用前端角色（而非创建经过 DNS 负载平衡的服务器池）时，您将仅使用单台 Standard Edition 服务器的完全限定域名 (FQDN)，如该示例所示。 该简单示例仅使用前端角色，其包含了下表中的 DNS 条目。 若要规划您的特定 DNS 要求，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**说明**|**记录类型**|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**解析为**|**负载平衡类型**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web 服务 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |服务器 SFB01 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |服务器 SFB02 的 IP 地址  <br/> |DNS  <br/> |
|池 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |服务器 SFB03 的 IP 地址  <br/> |DNS  <br/> |
|Skype for Business 自动发现  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|会议简单 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|拨入简单 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|Web 计划程序简单 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|管理简单 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web 服务的 VIP  <br/> |支持的软件和硬件  <br/> |
|旧版发现  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |池 FQDN（端口 5061）  <br/> |不适用  <br/> |
   
### <a name="create-dns-records"></a>创建 DNS 记录

1. 登录 DNS 服务器，然后打开“**服务器管理器**”。
    
2. 单击“**工具**”下拉菜单，然后单击“**DNS**”。
    
3. 在您的 SIP 域的控制台树中，展开**正向查找区域**，，然后展开将在安装 Skype 业务服务器的 SIP 域。
    
4. 右键单击该 SIP 域，然后选择“**新建主机（A 或 AAAA）**”，如图所示。
    
     ![选择新的 A 记录](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 在“**名称**”框中，键入主机记录的名称（将自动追加域名）。
    
6. 在“**IP 地址**”框中，键入单个前端服务器的 IP 地址，然后选择“**创建关联的指针 (PTR) 记录**”或“**允许所有经过身份验证的用户使用同一所有者名称更新 DNS 记录**”（如果适用）。注意，以上过程假定已使用 DNS 来对所有流量（Web 服务除外）进行负载平衡。在此示例中，我们拥有三台前端服务器，如表中所示。
    
   |**服务器名称**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
7. 接下来，为池创建 DNS 负载平衡条目。 DNS 负载平衡允许 DNS 向池中的各个服务器发送请求，与此同时使用相同的 DNS 池名称。 有关 DNS 和负载平衡的详细信息，请参阅[Skype 业务服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 仅可在 Enterprise Edition 部署中汇集多台服务器。如果您要部署单台 Enterprise Server 或 Standard Edition 服务器，您需要仅为该单台服务器创建一个 A 记录。 
  
    例如，如果已有一个名为 pool.contoso.local 的池和三台前端服务器，则需创建以下 DNS 条目：
    
   |**FQDN**|**类型**|**数据**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |主机 (A)  <br/> |10.0.0.7  <br/> |
   
8. 继续为计划部署中的所有服务器创建 A 记录。 
    
9. 要为旧版发现创建服务记录 (SRV) 记录，请右键单击 SIP 域，然后选择“**其他新记录**”。
    
10. 在“**选择资源记录类型**”中，单击“**服务位置 (SRV)**”，然后单击“**创建记录**”。
    
11. 单击“**服务**”，然后键入“**_sipinternaltls**”。
    
12. 单击“**协议**”，然后键入“**_tcp**”。
    
13. 单击“**端口号**”，然后键入“**5061**”。
    
14. 单击“**提供此服务的主机**”，然后键入池或 Standard Edition 服务器的 FQDN。
    
     ![“新资源记录”对话框的屏幕截图。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. 单击“**确定**”，然后单击“**完成**”。
    
### <a name="verify-dns-records"></a>验证 DNS 记录

1. 使用属于 Authenticated Users 组成员的帐户或具有等效权限的帐户登录到域中的客户端计算机。
    
2. 单击“**开始**”，然后键入“**cmd**”并按 Enter 键。
    
3. 类型**nslookup\<的前端池的 FQDN\>** 或**\<Standard Edition server 或单个 Enterprise Edition server 的 FQDN\>**，然后按 Enter。
    
4. 继续为您的部署验证其余 A 记录。
    
5. 如果您要支持旧版客户端并创建了 SRV 记录，请在 **nslookup** 命令提示行中键入 **set type=srv** 并按 Enter 键以进行验证。
    
6. 键入 **_sipinternaltls._tcp。*域***(例如，_sipinternaltls._tcp.contoso.local)，然后按 Enter。
    
7. 预计结果应当类似于图中所示内容。注意，示例结果中没有显示全部 DNS 记录，但应对所有记录进行验证。 
    
     ![验证 dns 设置。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

