---
title: Power BI에 대한 Microsoft Defender ATP API 연결
ms.reviewer: ''
description: 끝점 API용 Microsoft Defender 위에 POWER BI(비즈니스 인텔리전스) 보고서를 만들 수 있습니다.
keywords: api, 지원되는 api, Power BI, 보고서
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 696782ca03e5494c3fc5ca08943d1079c5d78f8a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167034"
---
# <a name="create-custom-reports-using-power-bi"></a><span data-ttu-id="d2822-104">Power BI를 사용하여 사용자 지정 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="d2822-104">Create custom reports using Power BI</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2822-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="d2822-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2822-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d2822-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2822-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2822-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="d2822-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="d2822-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2822-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="d2822-110">이 섹션에서는 끝점 API용 Defender 위에 Power BI 보고서를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-110">In this section you will learn create a Power BI report on top of Defender for Endpoint APIs.</span></span>

<span data-ttu-id="d2822-111">첫 번째 예제에서는 Power BI를 고급 헌팅 API에 연결하는 방법을 보여 주며, 두 번째 예제에서는 Machine Actions 또는 Alerts와 같은 OData API에 대한 연결을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-111">The first example demonstrates how to connect Power BI to Advanced Hunting API and the second example demonstrates a connection to our OData APIs, such as Machine Actions or Alerts.</span></span>

## <a name="connect-power-bi-to-advanced-hunting-api"></a><span data-ttu-id="d2822-112">고급 헌팅 API에 Power BI 연결</span><span class="sxs-lookup"><span data-stu-id="d2822-112">Connect Power BI to Advanced Hunting API</span></span>

- <span data-ttu-id="d2822-113">Microsoft Power BI 열기</span><span class="sxs-lookup"><span data-stu-id="d2822-113">Open Microsoft Power BI</span></span>

- <span data-ttu-id="d2822-114">데이터 **빈 쿼리**  >  **다운로드를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2822-114">Click **Get Data** > **Blank Query**</span></span>

    ![빈 쿼리 만들기 이미지](images/power-bi-create-blank-query.png)

- <span data-ttu-id="d2822-116">고급 **편집기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2822-116">Click **Advanced Editor**</span></span>

    ![고급 편집기 열기 이미지](images/power-bi-open-advanced-editor.png)

- <span data-ttu-id="d2822-118">아래를 복사하여 편집기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-118">Copy the below and paste it in the editor:</span></span>

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- <span data-ttu-id="d2822-119">완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2822-119">Click **Done**</span></span>

- <span data-ttu-id="d2822-120">자격 **증명 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2822-120">Click **Edit Credentials**</span></span>

    ![자격 증명 편집 이미지0](images/power-bi-edit-credentials.png)

- <span data-ttu-id="d2822-122">조직 **계정 로그인**  >  **선택**</span><span class="sxs-lookup"><span data-stu-id="d2822-122">Select **Organizational account** > **Sign in**</span></span>

    ![자격 증명 설정 이미지1](images/power-bi-set-credentials-organizational.png)

- <span data-ttu-id="d2822-124">자격 증명을 입력하고 로그인 대기</span><span class="sxs-lookup"><span data-stu-id="d2822-124">Enter your credentials and wait to be signed in</span></span>

- <span data-ttu-id="d2822-125">연결 **클릭**</span><span class="sxs-lookup"><span data-stu-id="d2822-125">Click **Connect**</span></span>

    ![자격 증명 설정 이미지2](images/power-bi-set-credentials-organizational-cont.png)

- <span data-ttu-id="d2822-127">이제 쿼리 결과가 표로 표시될 것이고 그 위에 시각화 빌드를 시작할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="d2822-127">Now the results of your query will appear as table and you can start build visualizations on top of it!</span></span>

- <span data-ttu-id="d2822-128">이 테이블을 복제하고 이름을 변경한 다음 내부에서 고급 헌팅 쿼리를 편집하여 원하는 데이터를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-128">You can duplicate this table, rename it and edit the Advanced Hunting query inside to get any data you would like.</span></span>

## <a name="connect-power-bi-to-odata-apis"></a><span data-ttu-id="d2822-129">Power BI를 OData API에 연결</span><span class="sxs-lookup"><span data-stu-id="d2822-129">Connect Power BI to OData APIs</span></span>

- <span data-ttu-id="d2822-130">위의 예제와 유일한 차이점은 편집기 내부의 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d2822-130">The only difference from the above example is the query inside the editor.</span></span> 

- <span data-ttu-id="d2822-131">아래를 복사하여 편집기에 붙여넣어 조직에서 모든 **컴퓨터** 작업을 끌어오세요.</span><span class="sxs-lookup"><span data-stu-id="d2822-131">Copy the below and paste it in the editor to pull all **Machine Actions** from your organization:</span></span>

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- <span data-ttu-id="d2822-132">경고 및 컴퓨터 **에** 대해 동일한 작업을 할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="d2822-132">You can do the same for **Alerts** and **Machines**.</span></span>

- <span data-ttu-id="d2822-133">쿼리 필터에 OData 쿼리를 사용할 수 있습니다. 자세한 내용은 [OData 쿼리 사용을 참조](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d2822-133">You also can use OData queries for queries filters, see [Using OData Queries](exposed-apis-odata-samples.md)</span></span>


## <a name="power-bi-dashboard-samples-in-github"></a><span data-ttu-id="d2822-134">GitHub의 Power BI 대시보드 샘플</span><span class="sxs-lookup"><span data-stu-id="d2822-134">Power BI dashboard samples in GitHub</span></span>
<span data-ttu-id="d2822-135">자세한 내용은 Power BI 보고서 서식 [파일을 참조하세요.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)</span><span class="sxs-lookup"><span data-stu-id="d2822-135">For more information see the [Power BI report templates](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).</span></span>

## <a name="sample-reports"></a><span data-ttu-id="d2822-136">예제 보고서</span><span class="sxs-lookup"><span data-stu-id="d2822-136">Sample reports</span></span>
<span data-ttu-id="d2822-137">Microsoft Defender ATP Power BI 보고서 샘플을 보세요.</span><span class="sxs-lookup"><span data-stu-id="d2822-137">View the Microsoft Defender ATP Power BI report samples.</span></span> <span data-ttu-id="d2822-138">자세한 내용은 코드 샘플 [찾아보기를 참조하세요.](https://docs.microsoft.com/samples/browse/?products=mdatp)</span><span class="sxs-lookup"><span data-stu-id="d2822-138">For more information, see [Browse code samples](https://docs.microsoft.com/samples/browse/?products=mdatp).</span></span>


## <a name="related-topic"></a><span data-ttu-id="d2822-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d2822-139">Related topic</span></span>
- [<span data-ttu-id="d2822-140">끝점 API용 Defender</span><span class="sxs-lookup"><span data-stu-id="d2822-140">Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="d2822-141">고급 헌팅 API</span><span class="sxs-lookup"><span data-stu-id="d2822-141">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="d2822-142">OData 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="d2822-142">Using OData Queries</span></span>](exposed-apis-odata-samples.md)
