---
title: 患者应用程序和 EHR 集成 STU3 接口
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者 app EHR 集成
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643073"
---
# <a name="stu3-interface-specification"></a>STU3 接口规范

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

设置或重新配置 FHIR server 以使用 Microsoft 团队患者应用程序需要了解哪些应用程序需要访问的数据。 FHIR 服务器必须支持的以下资源使用捆绑的 POST 请求：

- [患者](#patient)
- [观察值](#observation)
- [条件](#condition)
- [遇到](#encounter)
- [过敏 Intolerance](#allergyintolerance)
- [覆盖范围](#coverage)
- [用药语句](#medication-request)（替换 PatientsApp DSTU2 版本 MedicationOrder）
- （信息需要从此资源可以包括在遇到） 的位置

> [!NOTE]
> 患者资源是唯一的必填资源 （该应用程序将不会加载根本）;但是，建议合作伙伴实现支持的每个规范下面提供的 Microsoft 团队患者 App 最佳最终用户体验的所有上面提到资源。

从多个资源的 Microsoft 团队患者应用程序的查询应发布到 FHIR 服务器的 URL 的请求的绑定 （批次）。 服务器应处理每个请求，并将返回匹配的每个请求的资源的绑定。 有关详细信息和示例，请参阅[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)。

## <a name="capability-statement"></a>功能语句

这是最小的必填的字段：

1. REST
   1. 模式
   2. 交互
   3. 资源： 类型
   4. 安全性：[扩展的 OAuth Uri](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion （我们的代码需要此选项可了解我们应该侧重于哪个版本。）

请参阅[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)有关此字段的其他详细信息设置。

## <a name="patient"></a>患者

下面是最小的必填的字段，它们是 Argonaut 患者的配置文件字段的子集：

1. Name.Given
2. Name.Family
3. 性别
4. 出生日期
5. MRN （标识符）

除了[Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner]-GeneralPractitioner 引用应包含在患者资源 （仅显示字段）

资源搜索使用 POST 方法 /Patient/_search 和以下参数：

1. id
2. 系列 = （搜索系列名称中包含值的所有患者）
3. 给定 =\<substring>
4. 出生日期 =(exact match)
5. 性别 = （正在管理性别之一的值）
6. \_计数 （最大应返回的结果数） <br> 响应应该包含由于搜索返回的记录的总计数和\_计数将由 PatientsApp 以限制返回的记录数。
7. 标识符 =\<mrn>

目标是能够搜索和筛选由以下患者：

- ID： 这是每个资源 FHIR 中的包含的资源 ID。
- MRN： 这是患者临床人员自己知道的实际标识符。 我们了解此 MRN 基于内 FHIR 标识符资源的标识符的类型。
- 名称
- 出生日期

请参阅下面的示例的呼叫：

* * *

    请求： POST <fhir-server>/患者/_search 请求正文： 给定 = ruth&family = 黑色
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"元数据": {"上次更新":"2019年-01-14T23:44:45.052 + 00:00"}，"类型":"searchset"，"total": 1，"链接": [{"关系":"自助"、"url": <fhir-server>/患者/_search"}]，entry: [{"fullUrl": <fhir-server>/患者/<patient-id>"，"资源": {"resourceType":"患者"，"id":"<patient id>"、"元数据": {"versionId":"1"的"上次更新":"2017年-10-18T18:32:37.000 + 00:00"}，"text": {"状态":"生成"、"div": "<div>\n        <p>有所黑色</p>\n      </div>"}，"标识符": [{"使用":"常用"的"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"，"显示":"医疗记录号"、"userSelected": false}]，"text":"医疗记录号"}，"系统":"http://hospital.smarthealthit.org"，"value":"1234567"}]、"活动": 为 true，则"名称": [{"使用":"正式"，"系列":"黑色"，"授予": ["有所"，"c"。
    ]}]，"电信": [{"系统":"电话"，"value":"800-599-2739"，"使用":"主页"}，{"系统":"电话"，"value":"800-808-7785"，"使用":"移动"}，{"系统":"电子邮件"、"value":"ruth.black@example.com"}]，"性别":"女"，"出生日期":"1951年-08-23"，"address": [{"使用":"主页"，"线条": ["26 南部 RdApt 22"]，"city":"Sapulpa"，"state":"OK"，"postalCode":"74066"，"country":"美国"}]}，"搜索": {"模式":"匹配"}}]}

* * *

    请求： 获取 <fhir-server>/患者/<patient-id>
    
    响应: {"resourceType":"患者"，"id":"<patient id>"、"标识符": [{"使用":"常用"的"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"}]，"text":"医疗记录号"}，"value":"1234567"}]，"名称": [{"使用":"正式"，"系列":"Adams"，"授予": ["Daniel"、"X。 ] {}]，"性别":"男"，"出生日期":"1925年-12-23"}

* * *

请参阅[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)有关此字段的其他详细信息设置。

## <a name="observation"></a>观察值

这些是最小必填的字段，是[Argonaut 重要征兆配置文件](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。

1. 有效 （日期时间或段）
2. Code.Coding.Code
3. ValueQuantity.Value

除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. Code.Coding.Display
2. ValueQuantity.Unit

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _sort = 日期
3. 类别 (我们将查询"类别 = 重要迹象") 以检索重要标志的列表。

请参阅本例呼叫：

* * *

    请求： 获取观察值 <fhir-server>？ 患者 = <patient id>&category = 重要迹象
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 20，entry: [{"资源": {"resourceType":"观察值"、"id":"<resource id>"、"category": [{"编码": [{"系统":"http://hl7.org/fhir/observation-category"，"代码":"重要标记"}]}]，"代码": {"编码": [{"系统":"http://loinc.org"，"代码":"8867-4"，"显示":"heart_rate"}]}，"effectiveDateTime":"2009年-04-08T00:00:00-06:00"，"valueQuantity": {"value": 72.0，"单位":"{优于} / min"，"系统":"http://unitsofmeasure.org"，}}}。
        .
        .
      ] }

* * *

请参阅[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)有关此字段的其他详细信息设置。

## <a name="condition"></a>条件

下面是最小必填的字段，是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集。

1. Code.Coding[0]。显示

除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. AssertedDate
2. 严重级别

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大 results>

请参阅下面的示例，此呼叫的：

* * *

    请求： 获取 <fhir server>/条件？ 患者 = <patient id>&_count = 10
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 2，entry: [{"资源": {"resourceType":"条件"、"id":"<resource id>"、"代码": {"编码": [{"系统":"http://snomed.info/sct"，"代码":"185903001"，"显示":"需求流感免疫"}]}，"severity": {"编码": [{"系统":"http://snomed.info/sct"，"代码":"24484000"，"显示":"严重"}]}，"assertedDate":"2018年-04-04"}}。
        .
        .
      ] }

* * *
请参阅[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)有关此字段的其他详细信息设置。

## <a name="encounter"></a>遇到

这些是最小的必填的字段，它们是[美国核心遇到配置文件](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)"必须具有"字段的子集。）

1. 状态
2. 类型 [0]。编码 [0]。显示

此外，从美国核心遇到配置文件的以下字段"必须支持"字段：

1. Period.Start
2. 位置 [0]。Location.Display

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _sort:desc =\<ex 字段。 date>
3. _count =\<最大 results>

目标是能够检索患者的最后一个已知的位置。 每个遇到引用的位置资源。 引用还应包括的位置显示字段。

请参阅[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)有关此字段的其他详细信息设置。

## <a name="allergyintolerance"></a>AllergyIntolerance

这是最小必填的字段，是[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)配置文件的子集：

1. Code.Text
2. Code.Coding[0]。显示
3. ClinicalStatus/VerificationStatus （我们读取两者）

除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. AssertedDate
2. Note.Text
3. 反应
    1. 材料 （一个编码元素）
    2. 体现 （一个编码元素）

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>

请参阅下面的示例的呼叫： 

* * *

    请求： 获取 <fhir-server>/AllergyIntolerance？ 患者 = <patient id>
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"AllergyIntolerance"，"id":"<resource id>"、"clinicalStatus":"活动"，"verificationStatus":"确认"，"代码": {"编码": [{"系统":"http://rxnav.nlm.nih.gov/REST/Ndfrt"，"代码":"N0000175503"，"显示":"sulfonamide antibacterial"}]，"text":"sulfonamide antibacterial"}，"assertedDate":"2018年-01-01T00:00:00-07:00"，"反应": [{"体现": [{"编码": [{"系统":"http://snomed.info/sct"，"代码": "271807003"，"显示":"外观一连串"}]，"text":"外观一连串"}]，}]}}]}

* * *

请参阅[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)有关此字段的其他详细信息设置。

## <a name="medication-request"></a>用药请求

这是最小必填的字段，是[美国核心用药请求配置文件](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：

1. Medication.Display (如果引用)
2. Medication.Text (如果 CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

除了美国核心字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. DosageInstruction [.]。文本
2. 文本

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大 results>

请参阅[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段的其他详细信息设置。

## <a name="coverage"></a>覆盖范围

这是最小的必填的字段，不受美国核心或 Argonaut 配置文件：

1. 分组，至少一个元素
    1. GroupDisplay
    2. PlanDisplay
2. 时间段
3. SubscriberId

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>

请参阅[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段的其他详细信息设置。
