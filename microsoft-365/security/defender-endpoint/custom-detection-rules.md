---
title: Microsoft Defender ATP에서 사용자 지정 검색 규칙 만들기
ms.reviewer: ''
description: 고급 헌팅 쿼리를 기반으로 사용자 지정 검색 규칙을 만드는 방법 학습
keywords: 사용자 지정 검색, 만들기, 관리, 경고, 편집, 요청 시 실행, 빈도, 간격, 검색 규칙, 고급 헌팅, 헌팅, 쿼리, 응답 작업, mdatp, Microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163590"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="061f0-104">사용자 지정 검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="061f0-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="061f0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="061f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="061f0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="061f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="061f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="061f0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="061f0-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="061f0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="061f0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="061f0-110">고급 헌팅 [](advanced-hunting-overview.md) 쿼리로 구축된 사용자 지정 검색 규칙을 사용하면 위반 활동 및 잘못 구성된 장치를 포함하여 다양한 이벤트 및 시스템 상태도 사전적으로 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="061f0-111">이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="061f0-112">이 문서를 읽고 새 사용자 지정 검색 규칙을 만드는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="061f0-113">또는 [기존 규칙 보기 및 관리를 참조합니다.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="061f0-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="061f0-114">사용자 지정 검색을 만들거나 관리하려면 역할에 보안 설정 관리 **권한이 필요합니다.** [](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)</span><span class="sxs-lookup"><span data-stu-id="061f0-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="061f0-115">1. 쿼리를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-115">1. Prepare the query.</span></span>

<span data-ttu-id="061f0-116">Microsoft Defender 보안 센터에서 고급 헌팅으로 **이동하여** 기존 쿼리를 선택하거나 새 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="061f0-117">새 쿼리를 사용할 때 쿼리를 실행하여 오류를 식별하고 가능한 결과를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="061f0-118">서비스가 너무 많은 경고를 반환하지 않도록 각 규칙은 실행 시 100개의 경고만 생성하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="061f0-119">규칙을 만들기 전에 일반적인 일과 활동에 대한 경고가 표시되지 않도록 쿼리를 조정하십시오.</span><span class="sxs-lookup"><span data-stu-id="061f0-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="061f0-120">쿼리 결과의 필수 열</span><span class="sxs-lookup"><span data-stu-id="061f0-120">Required columns in the query results</span></span>

<span data-ttu-id="061f0-121">사용자 지정 검색 규칙에 쿼리를 사용하려면 쿼리에서 다음 열을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="061f0-122">또는 연산자를 사용하여 결과를 사용자 지정하거나 집계하지 않는 쿼리와 같은 단순 쿼리는 일반적으로 이러한 공통 `project` `summarize` 열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="061f0-123">보다 복잡한 쿼리에서 이러한 열을 반환하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="061f0-124">예를 들어 별로 집계 및 개수를 계산하려면 각 디바이스와 관련된 가장 최근 이벤트에서 를 반환하여 반환할 `DeviceId` `Timestamp` 수 `ReportId` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="061f0-125">아래 샘플 쿼리는 바이러스 백신 검색이 있는 고유 장치( )의 수를 계산하고 이 쿼리를 사용하여 5개가 넘게 검색된 장치만 `DeviceId` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="061f0-126">최신 및 해당 `Timestamp` 을 반환하기 위해 `ReportId` 함수와 함께 `summarize` 연산자를 `arg_max` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="061f0-127">쿼리 성능을 향상하기 위해 규칙에 대해 의도한 실행 빈도와 일치하는 시간 필터를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="061f0-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="061f0-128">최소 자주 실행은 24시간마다이기 때문에 지난 날에 대한 필터링은 모든 새 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="061f0-129">2. 새 규칙을 만들고 경고 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="061f0-130">쿼리 편집기에서 쿼리를 사용하여 검색 규칙 만들기를 **선택하고** 다음 경고 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="061f0-131">**검색 이름**- 검색 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="061f0-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="061f0-132">**빈도**- 쿼리를 실행하고 작업을 수행하기 위한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="061f0-133">아래 추가 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="061f0-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="061f0-134">**경고 제목**- 규칙에 의해 트리거된 경고와 함께 표시되는 제목</span><span class="sxs-lookup"><span data-stu-id="061f0-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="061f0-135">**심각도**- 규칙으로 식별된 구성 요소 또는 활동의 잠재적 위험입니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="061f0-136">경고 심각도에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="061f0-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="061f0-137">**범주**- 위협 구성 요소 또는 활동의 유형(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="061f0-138">경고 범주에 대한 읽기</span><span class="sxs-lookup"><span data-stu-id="061f0-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="061f0-139">**MITRE ATT&CK** 기술 - MITRE ATT&CK 프레임워크에 설명된 규칙으로 식별된 하나 이상의 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="061f0-140">이 섹션은 맬웨어, 랜섬웨어, 의심스러운 활동 및 원치 않는 소프트웨어와 같은 특정 경고 범주에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="061f0-141">**설명**- 규칙으로 식별된 구성 요소 또는 활동에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="061f0-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="061f0-142">**권장 작업**- 경고에 대한 응답으로 응답할 수 있는 추가 작업</span><span class="sxs-lookup"><span data-stu-id="061f0-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="061f0-143">경고 세부 정보가 표시되는 방법에 대한 자세한 내용은 경고 [큐 를 참조하세요.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="061f0-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="061f0-144">규칙 빈도</span><span class="sxs-lookup"><span data-stu-id="061f0-144">Rule frequency</span></span>

<span data-ttu-id="061f0-145">저장하면 새 사용자 지정 검색 규칙이 즉시 실행되고 지난 30일 동안의 데이터와 일치하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="061f0-146">그런 다음 규칙은 선택한 빈도에 따라 고정된 간격 및 콜백 기간에 따라 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="061f0-147">**24시간마다**-지난 30일간의 데이터를 확인하여 24시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="061f0-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="061f0-148">**12시간마다**-지난 24시간의 데이터를 확인하여 12시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="061f0-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="061f0-149">**3시간마다**-지난 6시간의 데이터를 확인하여 3시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="061f0-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="061f0-150">**매시간**-매시간 실행, 지난 2시간의 데이터 확인</span><span class="sxs-lookup"><span data-stu-id="061f0-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="061f0-151">이미 사용자 지정 검색으로 예약된 쿼리를 변경하는 경우 즉시 실행되는 쿼리는 새 쿼리를 만들 때와 똑같은 30일의 조회 기간을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="061f0-152">많은 수의 쿼리 및 선택한 빈도에 대한 기본 조회 기간보다 더 많은 시간 필터를 변경하면 고급 헌팅의 전체 할당량 소비에 영향을 미쳐 일별 할당량이 소진될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="061f0-153">쿼리의 시간 필터를 조회 기간과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="061f0-154">콜백 기간 외의 결과는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="061f0-155">검색을 모니터링할 빈도와 일치하는 빈도를 선택하고 경고에 응답할 조직의 용량을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="061f0-156">3. 영향을 미치는 엔터티를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="061f0-157">영향을 받거나 영향을 받는 주 엔터티를 찾을 것으로 예상되는 쿼리 결과의 열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="061f0-158">예를 들어 쿼리는 장치와 사용자 ID를 모두 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="061f0-159">이러한 열 중 주요 영향을 미치는 엔터티를 나타내는 열을 식별하면 서비스에서 관련 경고를 집계하고 인시던트의 상관 관계 및 대상 대응 작업을 집계하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="061f0-160">각 엔터티 유형에 대해 하나의 열만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="061f0-161">쿼리에서 반환되지 않는 열은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="061f0-162">4. 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-162">4. Specify actions.</span></span>

<span data-ttu-id="061f0-163">사용자 지정 검색 규칙은 쿼리에서 반환되는 파일 또는 장치에 대해 자동으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="061f0-164">디바이스에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="061f0-164">Actions on devices</span></span>

<span data-ttu-id="061f0-165">이러한 작업은 쿼리 결과의 `DeviceId` 열에 있는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="061f0-166">**장치 격리**- 전체 네트워크 격리가 적용될 경우 장치가 끝점용 Defender 서비스를 제외한 모든 응용 프로그램 또는 서비스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="061f0-167">장치 고리에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="061f0-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="061f0-168">**조사 패키지 수집**- ZIP 파일에 장치 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="061f0-169">조사 패키지에 대해 자세히 알아보시겠습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="061f0-170">**바이러스 백신 검사 실행**-장치에서 전체 Microsoft Defender 바이러스 백신 검사 수행</span><span class="sxs-lookup"><span data-stu-id="061f0-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="061f0-171">**조사 시작**- 디바이스에서 [자동화된](automated-investigations.md) 조사 시작</span><span class="sxs-lookup"><span data-stu-id="061f0-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="061f0-172">**앱 실행 제한**- Microsoft에서 발급한 인증서로 서명된 파일만 실행할 수 있도록 장치에 대한 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="061f0-173">앱 실행 제한에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="061f0-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="061f0-174">파일에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="061f0-174">Actions on files</span></span>

<span data-ttu-id="061f0-175">이러한 작업은 쿼리 결과의 열 또는 파일에 `SHA1` `InitiatingProcessSHA1` 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="061f0-176">**허용/차단**- 항상 실행되거나 [](manage-indicators.md) 실행이 차단될 수 있도록 파일을 사용자 지정 표시기 목록에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="061f0-177">선택한 장치 그룹에서만 수행될 수 있도록 이 작업의 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="061f0-178">이 범위는 규칙의 범위와는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="061f0-179">**파일 Quarantine -deletes** the file from its current location and places a copy in quarantine</span><span class="sxs-lookup"><span data-stu-id="061f0-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="061f0-180">사용자에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="061f0-180">Actions on users</span></span>

- <span data-ttu-id="061f0-181">**사용자를 손상된** 것으로 표시 - Azure Active Directory에서 사용자의 위험 수준을 "높음"으로 설정하여 해당 ID 보호 [정책을 트리거합니다.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="061f0-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="061f0-182">5. 규칙 범위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-182">5. Set the rule scope.</span></span>

<span data-ttu-id="061f0-183">규칙을 적용하는 장치를 지정하기 위해 범위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="061f0-184">모든 장치</span><span class="sxs-lookup"><span data-stu-id="061f0-184">All devices</span></span>
- <span data-ttu-id="061f0-185">특정 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="061f0-185">Specific device groups</span></span>

<span data-ttu-id="061f0-186">범위에 있는 장치의 데이터만 Queried로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="061f0-187">또한 해당 디바이스에서만 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="061f0-188">6. 규칙을 검토하고 켜기.</span><span class="sxs-lookup"><span data-stu-id="061f0-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="061f0-189">규칙을 검토한 후 만들기를 **선택하여** 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="061f0-190">사용자 지정 검색 규칙이 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="061f0-191">구성된 빈도에 따라 다시 실행하여 일치를 확인하고, 경고를 생성하고, 대응 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="061f0-192">사용자 지정 검색 규칙을 [보고 관리하고,](custom-detections-manage.md)이전 실행을 확인하고, 트리거된 경고를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="061f0-193">필요한 경우 규칙을 실행하고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061f0-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="061f0-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="061f0-194">Related topics</span></span>

- [<span data-ttu-id="061f0-195">사용자 지정 검색 규칙 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="061f0-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="061f0-196">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="061f0-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="061f0-197">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="061f0-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="061f0-198">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="061f0-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="061f0-199">경고 보기 및 구성</span><span class="sxs-lookup"><span data-stu-id="061f0-199">View and organize alerts</span></span>](alerts-queue.md)
