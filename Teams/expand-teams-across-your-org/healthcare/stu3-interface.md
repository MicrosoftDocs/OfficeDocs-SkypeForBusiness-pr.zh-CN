---
title: 患者应用和 EHR 集成 STU3 界面
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者应用 EHR 集成
ms.openlocfilehash: 6c7638436f35a1e460c176964dfc63624985b12e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827630"
---
# <a name="stu3-interface-specification"></a>STU3 接口规范

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。 FHIR 服务器必须使用以下资源的捆绑包支持发布请求：

- [档案](#patient)
- [知识产权](#observation)
- [条件](#condition)
- [产生](#encounter)
- [过敏症 Intolerance](#allergyintolerance)
- [内](#coverage)
- [药物对帐单](#medication-request)（替换 PATIENTSAPP 的 DSTU2 版本中的 MedicationOrder）
- 位置（可能会包含此资源所需的信息）

> [!NOTE]
> 患者资源是唯一必需的资源（根本不会加载应用）;但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。

来自 Microsoft 团队患者应用的来自多个资源的查询将向 FHIR 服务器的 URL 发布请求的捆绑（批处理）。 服务器应对每个请求进行处理，并返回每个请求所匹配的资源的捆绑包。 有关详细信息和示例，请[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)参阅。

## <a name="capability-statement"></a>功能陈述

以下是最少的必填字段：

1. 余下
   1. 众
   2. 相交
   3. 资源：类型
   4. 安全性： [OAuth uri 的扩展](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion （我们的代码需要此内容才能了解应将数据透视到哪一个版本。）

有关[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)此字段集的其他详细信息，请参阅。

## <a name="patient"></a>档案

下面是 "Argonaut" 患者档案字段子集的最少必填字段：

1. 名称。给定
2. 名称。家庭
3. 性别
4. BirthDate
5. MRN （标识符）

除了[Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

1. 名称。使用
2. 名称。前缀
3. [GeneralPractitioner]-GeneralPractitioner 参考应包括在患者资源中（仅显示字段）

资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：

1. 标识号
2. 系列 = （搜索其系列名称包含该值的所有患者）
3. 给定 =\<substring>
4. 出生日期 = （完全匹配）
5. 性别 = （值为管理性别之一）
6. \_计数（应返回的最大结果数） <br> 该响应应包含作为搜索和\_计数的结果返回的记录总数，PatientsApp 将使用该计数来限制返回的记录数。
7. 标识符 =\<mrn>

目标是能够搜索和筛选患者，如下所示：

- ID：这是 FHIR 中的每个资源具有的资源 ID。
- MRN：这是临床人员将知道的患者的实际标识符。 我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型。
- 名称
- Birthdate

请参阅下面的通话示例：

* * *

    请求： POST <fhir-server>/Patient/_search 请求正文：给定 = ruth&家族 = 黑色
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"meta"： {"lastUpdated"： "2019-01-" type "：" searchset "，" total "：1，" link "： [{" relation "：" self "，" url "： <fhir-服务器>/Patient/_search"}]，"entry"： [{"fullUrl"： <fhir-server>/Patient/<患者 id> "，" 资源 "： {" resourceType "：" 患者 "，" id "：" <患者 id> "，" meta "： {" versionId "：" 1 "，" lastUpdated "：" 2017-18T18：32： 37.000 + 00： 00 "}，" text "： {" status "：" 已生成 "，" div "："<div>\n        <p>Ruth 黑</p>\n      </div>"}，" 标识符 "： [{" 使用 "：" 常规 "，" 键入 "： {" 编码 "： [{" 系统 "："http://hl7.org/fhir/v2/0203"，" 代码 "：" "MR"，"代码"： "MR"，"显示"： "userSelected"： false}]，"文本"： "医学记录编号"}，"systemhttp://hospital.smarthealthit.org"： "1234567"，"name"： [{"：" ""，"name"： [{"：" 官方 "，" 系列 "：" 黑色 "，" 第一个 "： [" Ruth "，" C "。
    ]}]，"电信"： [{"系统"： "电话"，"值"： "800-599-2739"，"使用"： "手机"}，{"系统"： "800-808-7785"，"值"： "ruth.black@example.com"，"使用"： "mobile"}，{"系统"： "电子邮件"，"值"： ""}]，"性别"： "女"，"出生日期"： "1951-08-23"，"地址"： [{"使用"： "开始"，"行"： ["26 RdApt 22"]，"城市"： "Sapulpa"，"状态"： "确定"，"邮政编码"： "74066"，"国家/地区"： "美国"}]}，"search"： {"mode"： "match"}}]}

* * *

    请求：获取 <fhir-服务器>/Patient/<患者 id>
    
    回复： {"resourceType"： "患者"，"id"： "<患者 id>"，"标识符"： [{"使用"： "常规"，"键入"： {"编码"： [{"系统"： "http://hl7.org/fhir/v2/0203"，"代码"： "MR"，}]，"文本"： "医学记录数字"}，"值"： "1234567"}]，"名称"： [{"：" "}]，" 名称 "： [{" "Adams"，"family"： "Daniel"，"X"。 ]}]，"性别"： "男"，"出生日期"： "1925-12-23"，}

* * *

有关[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)此字段集的其他详细信息，请参阅。

## <a name="observation"></a>知识产权

以下是最少的必填字段，它们是 Argonaut 的[重要签名配置文件](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。

1. 有效（日期时间或周期）
2. 编码代码
3. ValueQuantity 值

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

1. 代码编码。显示
2. ValueQuantity 单位

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _sort =-日期
3. 类别（我们将查询 "category = 重要标志"）以检索关键签名列表。

请参阅此通话示例：

* * *

    请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&类别 = "重要签名"
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：20，"entry"： [{"resource"： {""： "观察"，"id"： "<资源 id>"，"类别"： [{"编码"： [{"系统"：http://hl7.org/fhir/observation-category"" "，" 代码 "：" 重要签名 "}]，}]，" 代码 "： {" code "： [{" system "：http://loinc.org" ""，"code"： "8867-4"，"显示"： "heart_rate"}]}，"effectiveDateTime"： "2009 年08T00：00： 00-06： 00"，"valueQuantity"： {"value"：72.0，"unit"： "{节拍} ¢"，"system"： "http://unitsofmeasure.org"，"
        .
        .
      ] }

* * *

有关[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)此字段集的其他详细信息，请参阅。

## <a name="condition"></a>条件

下面是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段。

1. 代码。编码 [0]。画面

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

1. AssertedDate
2. 严重性

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大结果>

请参阅下面的此呼叫示例：

* * *

    请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"类型"： "searchset"，"total"：2，"entry"： [{"resource"： {"resourceType"： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"system"：http://snomed.info/sct""，"代码"： "185903001"，"display"： "需要 influenza 免疫接种"、}]}、"严重性"： {"编码"： [{"system"http://snomed.info/sct： ""，"代码"： "24484000"，"显示"： "严重"}]}，"assertedDate"： "2018-04-04"}}。
        .
        .
      ] }

* * *
有关[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)此字段集的其他详细信息，请参阅。

## <a name="encounter"></a>产生

以下是最少必填字段，这些字段是 "[美国核心" 基本配置文件](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)"必须具有" 字段的子集。

1. 状态栏
2. 键入 [0]。编码 [0]。画面

此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段：

1. 句号。开始
2. 位置 [0]。位置。显示

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _sort： desc =\<field （ex） 日期>
3. _count =\<最大结果>

目标是能够检索患者的最后一个已知位置。 每个遇到的都引用一个位置资源。 该引用还应包含位置的显示字段。

有关[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)此字段集的其他详细信息，请参阅。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是最少的必填字段，它们是[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)配置文件的子集：

1. 代码。文本
2. 代码。编码 [0]。画面
3. ClinicalStatus/VerificationStatus （我们通读两个）

除了 Argonaut 字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：

1. AssertedDate
2. 备注。文本
3. 被动
    1. 物质（一个编码元素）
    2. 表现形式（一个编码元素）

资源搜索使用 GET 方法和以下参数：

1. 患者 = \<患者 id>

请参阅下面的通话示例： 

* * *

    请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id>
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"type"： "searchset"，"total"：1，"entry"： [{"资源"： {"resourceType"： "AllergyIntolerance"，"id"： "<资源 id>"，"clinicalStatus"： "active"，"verificationStatus"： "已确认"，"代码"： {"编码"： [{"系统"http://rxnav.nlm.nih.gov/REST/Ndfrt： "" "，" 代码 "：" N0000175503 "，" display "：" sulfonamide antibacterial "，}]，" text "：" sulfonamide antibacterial "}，" assertedDate "：" 2018 日-01-01T00：00： 00-07： [{"code"： [{"系统"： "271807003"，"： [{" 系统http://snomed.info/sct： "外观 rash"，}]，"text"： "外观 rash"}]，}]}

* * *

有关[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)此字段集的其他详细信息，请参阅。

## <a name="medication-request"></a>药物请求

以下是最少的必填字段，这些字段是[美国核心药物请求档案](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：

1. 药物的显示（如果参考）
2. 药物文本（如果 CodableConcept）
3. AuthoredOn
4. 请求者代理。显示

除了 US 核心字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：

1. DosageInstruction[..].文本
2. 文本

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大结果>

有关[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)此字段集的其他详细信息，请参阅。

## <a name="coverage"></a>内

以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：

1. 组合，至少一个元素具有
    1. GroupDisplay
    2. PlanDisplay
2. 试用期
3. SubscriberId

资源搜索使用 GET 方法和以下参数：

1. 患者 = \<患者 id>

有关[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)此字段集的其他详细信息，请参阅。
