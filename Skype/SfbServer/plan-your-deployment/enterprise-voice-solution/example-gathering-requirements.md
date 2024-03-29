---
title: 示例 收集呼叫允许控制在Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: 提供规划呼叫允许控制在 Skype for Business Server 企业语音，包括收集有关网络站点、地区和带宽的信息的详细示例。
---

# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>示例：收集呼叫允许控制在Skype for Business Server

提供规划呼叫允许控制在 Skype for Business Server 企业语音，包括收集有关网络站点、地区和带宽的信息的详细示例。

此示例显示如何规划和实现呼叫允许控制 (CAC)。总体来说，包括以下活动：

1. 标识所有网络中心和网络中枢（称为网络区域）。

2. 确定Skype for Business Server区域管理 CAC 的一个中央站点。

3. 标识并定义连接到每个网络区域的网络站点。

4. 对于与 WAN 的连接受带宽限制的每个网络站点，描述 WAN 连接的带宽容量以及网络管理员为 Skype for Business Server 媒体流量设置的带宽限制（如果适用）。 不需要包括与 WAN 的连接不受带宽限制的站点。

5. 将网络中的每个子网与一个网络站点相关联。

6. 映射网络区域之间的链路。 对于每个链接，描述其带宽容量以及网络管理员对媒体流量Skype for Business Server限制。

7. 定义每对网络区域之间的路由。

## <a name="gather-the-required-information"></a>收集所需信息

要准备呼叫允许控制，请收集以下步骤中描述的信息：

1. 标识网络区域。网络区域代表网络中枢或网络中心。 

    网络中枢或网络中心是计算机网络基础结构的一部分，它将网络的各个部分相互连接起来，提供在不同 LAN 或子网之间交换信息的路径。网络中枢可以将各种网络关联在一起，适用范围从较小区域到广阔的地理区域。网络中枢的容量通常大于与其连接的网络的容量。

    示例拓扑具有三个网络区域：北美、EMEA 和 APAC。网络区域包含网络站点的集合。与网络管理员合作以定义企业的网络区域。

2. 标识每个网络区域关联的中央站点。 中央站点至少包含一台前端服务器，它是管理通过网络区域 WAN 连接的所有媒体流量的 CAC 的 Skype for Business Server 部署。

   **分为三个网络区域的企业网络示例**

     ![具有 3 个网络区域的网络拓扑示例。](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > 多协议标签交换 (MPLS) 网络应代表一个网络区域，在该网络区域中，每个物理位置都具有一个相应的网络站点。 有关详细信息，请参阅呼叫[允许控制的组件和](components-and-topologies.md)Skype for Business。 

    在上例网络拓扑中，有三个网络区域，每个网络Skype for Business Server管理 CAC 的一个中央站点。 按地理距离选择网络区域相应的中央站点。 由于网络区域内的媒体流量最多，按地理距离选择中央站点使网络区域能够独立运行，因此即使其他中央站点不可用，网络区域也可以继续正常工作。 

    本示例中，名为Skype for Business芝加哥的部署是北美区域的中央站点。

    北美Skype for Business用户都位于芝加哥部署中的服务器上。 下表显示了所有三个网络区域的中央站点。

    **网络区域及其关联的中央站点**

    |**网络区域**|**中央站点**|
    |:-----|:-----|
    |北美  <br/> |Chicago  <br/> |
    |EMEA  <br/> |伦敦  <br/> |
    |APAC  <br/> |北京  <br/> |

    > [!NOTE]
    > 根据您的网络Skype for Business Server，可以将同一中央站点分配给多个网络区域。 

3. 对于每个网络区域，标识其 WAN 连接不受带宽限制的所有网络站点（办公室或位置）。由于这些站点不受带宽限制，因此无需对其应用 CAC 带宽策略。

    在下表显示的示例中，有三个网络站点没有受带宽限制的 WAN 链路：纽约、芝加哥和底特律。

   **不受 WAN 带宽限制的网络站点**


   | **网络站点** | **网络区域**   |
   |:-----------------|:---------------------|
   | 纽约  <br/>  | 北美  <br/> |
   | Chicago  <br/>   | 北美  <br/> |
   | 底特律  <br/>   | 北美  <br/> |


4. 对于每个网络区域，标识所有通过受带宽限制的 WAN 链路连接到网络区域的网络站点。

    为了帮助确保音频和视频质量，我们建议这些受带宽限制的网络站点监控其 WAN，并拥有限制流入和流出网络区域的媒体（音频或视频）流量的 CAC 带宽策略。

    在下表显示的示例中，有三个受 WAN 带宽限制的网络站点：波特兰、里诺和阿尔伯克基。

   **受 WAN 带宽限制的网络站点**

   |**网络站点**|**网络区域**|
   |:-----|:-----|
   |Albuquerque  <br/> |北美  <br/> |
   |Reno  <br/> |北美  <br/> |
   |波特兰  <br/> |北美  <br/> |

   **CAC 网络区域北美拥有三个不受带宽限制的网络站点（芝加哥、纽约和底特律）和三个受 WAN 带宽限制的网络站点（波特兰、里诺和阿尔伯克基）。**

     ![受 WAN 带宽限制的网络站点示例。](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. 对于每个受带宽限制的 WAN 链路，需确定以下事项：

   - 要为所有并发音频会话设置的总体带宽限制。 如果新的音频会话将导致超出此限制，Skype for Business Server不允许会话启动。

   - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。

   - 要为所有并发视频会话设置的总体带宽限制。 如果新的视频会话将导致超出此限制，Skype for Business Server不允许该会话启动。

   - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。

     **具有 WAN 带宽限制信息（带宽单位：kbps）的网络站点**


     | **网络站点**   | **网络区域**   | **BW 限制**      | **音频限制**   | **音频会话限制** | **视频限制**   | **视频会话限制** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | 北美  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | 北美  <br/> | 10,000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | 波特兰  <br/>    | 北美  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | 纽约  <br/>    | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       |
     | Chicago  <br/>     | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       |
     | 底特律  <br/>     | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       |


6. 对于网络中的每个子网，指定其关联的网络站点。

    > [!IMPORTANT]
    > 即使网络站点不受带宽限制，网络中的每个子网也必须与一个网络站点相关联。这是因为呼叫允许控制使用子网信息来确定终结点所在的网络站点。确定会话双方的位置后，呼叫允许控制可以确定是否有足够的带宽来建立呼叫。当通过没有带宽限制的链路建立会话时，会生成警报。 

    > [!IMPORTANT]
    > 如果部署音频/视频边缘服务器，则每台边缘服务器的公共 IP 地址都必须与部署边缘服务器的网络站点关联。 必须将 A/V 边缘服务器的每个公共 IP 地址作为子网掩码为 32 的子网添加到网络配置设置中。 例如，如果在芝加哥部署 A/V 边缘服务器，则为这些服务器的每个外部 IP 地址创建一个子网掩码为 32 的子网，并将网络站点芝加哥与这些子网相关联。 有关公用 IP 地址的详细信息，请参阅 Plan [network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)。 

    生成关键运行状况指示器 (KHI) 警报，指定存在于网络中但不与子网关联的 IP 地址列表，或指定包含 IP 地址的子网不与网络站点关联。该警报在 8 小时内只产生一次。相关的警报信息和示例如下所示：

    **源**：CS 带宽策略服务（核心） 

    **事件数**：36034

    **级别**：2

    **说明**：未配置以下 IP \<List of IP Addresses\> 地址的子网，或者子网未与网络站点关联。 

    **原因**：网络配置设置中缺少相应 IP 地址的子网，或子网未与网络站点关联。 

    **解决方案**：将与上述 IP 地址列表对应的子网添加到网络配置设置中，并将每个子网关联到网络站点。

    例如，如果警报中的 IP 地址列表指定 10.121.248.226 和 10.121.249.20，则可能是这些 IP 地址没有与子网关联，或者与其关联的子网不属于网络站点。如果 10.121.248.0/24 和 10.121.249.0/24 是与这些地址对应的子网，则可按如下所示解决此问题：

    a. 确保 IP 地址 10.121.248.226 与子网 10.121.248.0/24 关联，IP 地址 10.121.249.20 与子网 10.121.249.0/24 关联。

    b. 确保子网 10.121.248.0/24 和 10.121.249.0/24 分别与一个网络站点关联。

   **网络站点和关联子网（带宽单位：kbps）**


   | **网络站点**   | **网络区域**   | **BW 限制**      | **音频限制**   | **音频会话限制** | **视频限制**   | **视频会话限制** | **子网**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | 北美  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | 北美  <br/> | 10,000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | 波特兰  <br/>    | 北美  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | 纽约  <br/>    | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | 底特律  <br/>     | 北美  <br/> | （没有限制）  <br/> | （没有限制）  <br/> | （没有限制）  <br/>       | （没有限制）  <br/> | （没有限制）  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. 在Skype for Business Server允许控制中，网络区域间的连接称为区域链接。 对于每个区域链路，按照对网络站点执行的操作，确定以下事项：

   - 要为所有并发音频会话设置的总体带宽限制。 如果新的音频会话将导致超出此限制，Skype for Business Server不允许该会话启动。

   - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。

   - 要为所有并发视频会话设置的总体带宽限制。 如果新的视频会话将导致超出此限制，Skype for Business Server不允许会话启动。

   - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。

   **具有关联带宽限制的网络区域链路**

     ![3 个区域之间的限制示例。](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **区域链路带宽信息（带宽单位：kbps）**


   | **区域链路名称**  | **第一个区域**     | **第二个区域** | **BW 限制**  | **音频限制** | **音频会话限制** | **视频限制** | **视频会话限制** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | 北美  <br/> | EMEA  <br/>       | 50,000  <br/> | 20,000  <br/>   | 175  <br/>              | 14,000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25,000  <br/> | 10,000  <br/>   | 175  <br/>              | 7,000  <br/>    | 700  <br/>              |


8. 定义每对网络区域之间的路由。

    > [!NOTE]
    > 北美和 APAC 区域之间的路由需要两个链路，因为没有直接连接这两个区域的区域链路。 

   **区域路由**


   | **区域路由名称**  | **第一个区域**     | **第二个区域** | **区域链路**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | 北美  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | 北美  <br/> | APAC  <br/>       | NA-EMEA-LINK、EMEA-APAC-LINK  <br/> |


9. 对于通过单链路（称为站点间 链路）直接进行连接的每对网络站点，需确定以下事项：

     - 要为所有并发音频会话设置的总体带宽限制。 如果新的音频会话将导致超出此限制，Skype for Business Server不允许该会话启动。

     - 要为每个单独的音频会话设置的带宽限制。默认 CAC 带宽限制是 175 kbps，但是管理员可修改该值。

     - 要为所有并发视频会话设置的总体带宽限制。 如果新的视频会话将导致超出此限制，Skype for Business Server不允许会话启动。

     - 要为每个单独的视频会话设置的带宽限制。默认 CAC 带宽限制是 700 kbps，但是管理员可修改该值。

   **CAC 网络区域北美显示里诺和阿尔伯克基之间的站点间链路的带宽容量和带宽限制。**

     ![受 WAN 带宽限制的网络站点示例。](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **两个网络站点间的站点间链路的带宽信息（带宽单位：kbps）**

   |**站点间链路名称**|**第一个站点**|**第二个站点**|**BW 限制**|**音频限制**|**音频会话限制**|**视频限制**|**视频会话限制**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20,000  <br/> |12,000  <br/> |175  <br/> |5,000  <br/> |700  <br/> |

### <a name="next-steps"></a>后续步骤

收集所需信息后，可以使用命令行管理程序或控制面板Skype for Business Server CAC Skype for Business Server CAC 部署。

> [!NOTE]
> 虽然可以使用"控制面板"Skype for Business Server大多数网络配置任务，但若要创建子网和站点间链接，必须使用命令行管理Skype for Business Server命令行管理程序。 有关详细信息，请参阅 [New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps) 和 [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。