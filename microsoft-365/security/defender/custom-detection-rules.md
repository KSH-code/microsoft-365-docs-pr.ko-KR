---
title: Microsoft 365 Defender에서 사용자 지정 검색 규칙 만들기 및 관리
description: 고급 헌팅 쿼리를 기반으로 사용자 지정 검색 규칙을 만들고 관리하는 방법을 배우기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, Microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 규칙, schema, kusto, RBAC, 사용 권한, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f37cc63c958331f7c03e09689de92c73fd06b4d4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952563"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="f0f84-104">사용자 지정 검색 규칙 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="f0f84-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f0f84-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f0f84-105">**Applies to:**</span></span>
- <span data-ttu-id="f0f84-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0f84-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f0f84-107">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f0f84-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f0f84-108">사용자 지정 검색 규칙은 고급 헌팅 쿼리를 사용하여 디자인하고 [조정하는 규칙입니다.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f0f84-108">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="f0f84-109">이러한 규칙을 사용하면 위반 활동 및 잘못 구성된 끝점을 포함하여 다양한 이벤트 및 시스템 상태 등을 사전 예방적으로 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-109">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="f0f84-110">이러한 경고를 정기적으로 실행하여 일치하는 경우 경고를 생성하고 응답 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="f0f84-111">사용자 지정 검색을 관리하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="f0f84-111">Required permissions for managing custom detections</span></span>

<span data-ttu-id="f0f84-112">사용자 지정 검색을 관리하려면 다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-112">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="f0f84-113">**보안 관리자**- [이 Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 역할이 있는 사용자는 Microsoft 365 보안 센터 및 기타 포털 및 서비스에서 보안 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-113">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="f0f84-114">**보안 운영자**- 이 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 역할이 있는 사용자는 경고를 관리하고 Microsoft 365 보안 센터의 모든 정보를 포함하여 보안 관련 기능에 대한 전역 읽기 전용 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-114">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="f0f84-115">이 역할은 Microsoft Defender for Endpoint에서 RBAC(역할 기반 액세스 제어)가 꺼져 있는 경우만 사용자 지정 검색을 관리하기에 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-115">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f0f84-116">RBAC를 구성한 경우 끝점용  Defender에 대한 보안 설정 관리 권한도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-116">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="f0f84-117">필요한 사용 권한을 관리하려면 전역 **관리자가 다음을 할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-117">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="f0f84-118">역할 보안 **관리자** 아래 [Microsoft 365](https://admin.microsoft.com/) 관리 센터에서 보안 관리자 또는 보안 운영자 역할을   >  **할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0f84-118">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="f0f84-119">설정 사용 권한 역할에서 Microsoft Defender 보안 센터의  [끝점용 Microsoft Defender에](https://securitycenter.windows.com/) 대한 RBAC  >    >  **설정을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0f84-119">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="f0f84-120">해당 역할을 선택하여 보안 설정 관리 **권한을 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0f84-120">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="f0f84-121">사용자 지정 검색을 **관리하려면** RBAC가 켜져 있는 경우 보안 운영자가 끝점용 Microsoft Defender의 보안 설정 관리 권한이 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="f0f84-121">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="f0f84-122">사용자 지정 검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="f0f84-122">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="f0f84-123">1. 쿼리를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-123">1. Prepare the query.</span></span>

<span data-ttu-id="f0f84-124">Microsoft 365 보안 센터에서  고급 헌팅으로 이동하여 기존 쿼리를 선택하거나 새 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-124">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="f0f84-125">새 쿼리를 사용할 때 쿼리를 실행하여 오류를 식별하고 가능한 결과를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-125">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f0f84-126">서비스가 너무 많은 경고를 반환하지 않도록 각 규칙은 실행 시 100개의 경고만 생성하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-126">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="f0f84-127">규칙을 만들기 전에 일반적인 일과 활동에 대한 경고가 표시되지 않도록 쿼리를 조정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0f84-127">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="f0f84-128">쿼리 결과의 필수 열</span><span class="sxs-lookup"><span data-stu-id="f0f84-128">Required columns in the query results</span></span>
<span data-ttu-id="f0f84-129">사용자 지정 검색 규칙을 만들하려면 쿼리에서 다음 열을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-129">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="f0f84-130">`Timestamp`-생성된 경고에 대한 타임스탬프를 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-130">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="f0f84-131">`ReportId`-를 사용하면 원본 레코드에 대한 검색을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-131">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="f0f84-132">특정 장치, 사용자 또는 사서함을 식별하는 다음 열 중 하나</span><span class="sxs-lookup"><span data-stu-id="f0f84-132">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="f0f84-133">`SenderFromAddress` (봉투 보낸 사람 또는 Return-Path 주소)</span><span class="sxs-lookup"><span data-stu-id="f0f84-133">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="f0f84-134">`SenderMailFromAddress` (전자 메일 클라이언트가 표시하는 보낸 사람 주소)</span><span class="sxs-lookup"><span data-stu-id="f0f84-134">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="f0f84-135">고급 헌팅 계획에 새 테이블이 추가될 때 추가 엔터티에 대한 [지원이 추가됩니다.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="f0f84-135">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="f0f84-136">또는 연산자를 사용하여 결과를 사용자 지정하거나 집계하지 않는 쿼리와 같은 단순 쿼리는 일반적으로 이러한 공통 `project` `summarize` 열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-136">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="f0f84-137">보다 복잡한 쿼리에서 이러한 열을 반환하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-137">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="f0f84-138">예를 들어 과 같은 열 아래에서 엔터티별로 집계 및 개수를 계산하고 를 원하는 경우 각 고유 을 포함하는 가장 최근 이벤트에서 를 반환하여 반환할 `DeviceId` `Timestamp` 수 `ReportId` `DeviceId` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-138">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="f0f84-139">아래 샘플 쿼리는 바이러스 백신 검색이 있는 고유 장치( )의 수를 계산하고 이 개수를 사용하여 5개가 넘게 검색된 장치만 `DeviceId` 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-139">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="f0f84-140">최신 및 해당 `Timestamp` 을 반환하기 위해 `ReportId` 함수와 함께 `summarize` 연산자를 `arg_max` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-140">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="f0f84-141">쿼리 성능을 향상하기 위해 규칙에 대해 의도한 실행 빈도와 일치하는 시간 필터를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0f84-141">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="f0f84-142">최소 자주 실행은 _24시간마다 이기_ 때문에 지난 날에 대한 필터링은 모든 새 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-142">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="f0f84-143">2. 새 규칙을 만들고 경고 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-143">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="f0f84-144">쿼리 편집기에서 쿼리를 사용하여 검색 규칙 만들기를 **선택하고** 다음 경고 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-144">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="f0f84-145">**검색 이름**- 검색 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="f0f84-145">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="f0f84-146">**빈도**- 쿼리를 실행하고 작업을 수행하기 위한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-146">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="f0f84-147">아래 추가 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0f84-147">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="f0f84-148">**경고 제목**- 규칙에 의해 트리거된 경고와 함께 표시되는 제목</span><span class="sxs-lookup"><span data-stu-id="f0f84-148">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="f0f84-149">**심각도**- 규칙으로 식별된 구성 요소 또는 활동의 잠재적 위험</span><span class="sxs-lookup"><span data-stu-id="f0f84-149">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="f0f84-150">**범주**-규칙으로 식별된 위협 구성 요소 또는 활동</span><span class="sxs-lookup"><span data-stu-id="f0f84-150">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="f0f84-151">**MITRE ATT&CK** 기술 - [MITRE ATT](https://attack.mitre.org/)&CK 프레임워크에 설명된 규칙으로 식별된 하나 이상의 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-151">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="f0f84-152">이 섹션은 맬웨어, 랜섬웨어, 의심스러운 활동 및 원치 않는 소프트웨어를 비롯한 특정 경고 범주에 대해 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-152">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="f0f84-153">**설명**- 규칙으로 식별된 구성 요소 또는 활동에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f0f84-153">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="f0f84-154">**권장 작업**- 경고에 대한 응답으로 응답할 수 있는 추가 작업</span><span class="sxs-lookup"><span data-stu-id="f0f84-154">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="f0f84-155">규칙 빈도</span><span class="sxs-lookup"><span data-stu-id="f0f84-155">Rule frequency</span></span>
<span data-ttu-id="f0f84-156">새 규칙을 저장하면 규칙이 실행된 후 지난 30일 동안의 데이터와 일치하는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-156">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="f0f84-157">그런 다음 규칙은 고정된 간격으로 다시 실행되어 선택한 빈도에 따라 콜백 기간을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-157">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="f0f84-158">**24시간마다**-지난 30일간의 데이터를 확인하여 24시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-158">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="f0f84-159">**12시간마다**-지난 24시간의 데이터를 확인하여 12시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-159">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="f0f84-160">**3시간마다**-지난 6시간의 데이터를 확인하여 3시간마다 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-160">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="f0f84-161">**매시간**-매시간 실행, 지난 2시간의 데이터 확인</span><span class="sxs-lookup"><span data-stu-id="f0f84-161">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="f0f84-162">규칙을 편집하면 설정한 빈도에 따라 예약된 다음 런타스에 적용된 변경 내용과 함께 규칙이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-162">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="f0f84-163">쿼리의 시간 필터를 조회 기간과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-163">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="f0f84-164">콜백 기간 외의 결과는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-164">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="f0f84-165">검색을 모니터링하려는 빈도와 일치하는 빈도를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-165">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="f0f84-166">조직의 경고에 응답할 수 있는 용량을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-166">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="f0f84-167">3. 영향을 미치는 엔터티를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-167">3. Choose the impacted entities.</span></span>
<span data-ttu-id="f0f84-168">영향을 받거나 영향을 받는 주 엔터티를 찾을 것으로 예상되는 쿼리 결과의 열을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-168">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="f0f84-169">예를 들어 쿼리는 보낸 사람( 또는 ) 및 받는 사람( ) 주소를 `SenderFromAddress` `SenderMailFromAddress` `RecipientEmailAddress` 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-169">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="f0f84-170">이러한 열 중 주요 영향을 미치는 엔터티를 나타내는 열을 식별하면 서비스에서 관련 경고를 집계하고 인시던트의 상관 관계 및 대상 대응 작업을 집계하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-170">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="f0f84-171">각 엔터티 유형(사서함, 사용자 또는 장치)에 대해 열을 하나만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-171">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="f0f84-172">쿼리에서 반환되지 않는 열은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-172">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="f0f84-173">4. 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-173">4. Specify actions.</span></span>
<span data-ttu-id="f0f84-174">사용자 지정 검색 규칙은 쿼리에서 반환되는 장치, 파일 또는 사용자에 대해 자동으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-174">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="f0f84-175">디바이스에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="f0f84-175">Actions on devices</span></span>
<span data-ttu-id="f0f84-176">이러한 작업은 쿼리 결과의 `DeviceId` 열에 있는 장치에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-176">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="f0f84-177">**장치 격리**- 끝점용 Microsoft Defender를 사용하여 전체 네트워크 격리 적용을 통해 장치가 응용 프로그램 또는 서비스에 연결하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-177">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="f0f84-178">끝점 컴퓨터의 Microsoft Defender에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="f0f84-178">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="f0f84-179">**조사 패키지 수집**- ZIP 파일에 장치 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-179">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="f0f84-180">Endpoint용 Microsoft Defender 조사 패키지에 대해 자세히 알아보시겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-180">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="f0f84-181">**바이러스 백신 검사 실행**-장치에서 Windows Defender 바이러스 백신 검사 수행</span><span class="sxs-lookup"><span data-stu-id="f0f84-181">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="f0f84-182">**조사 시작**- 디바이스에서 [자동화된](m365d-autoir.md) 조사 시작</span><span class="sxs-lookup"><span data-stu-id="f0f84-182">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="f0f84-183">**앱 실행 제한**- Microsoft에서 발급한 인증서로 서명된 파일만 실행할 수 있도록 장치에 대한 제한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-183">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="f0f84-184">끝점용 Microsoft Defender의 앱 제한에 대해 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="f0f84-184">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="f0f84-185">파일에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="f0f84-185">Actions on files</span></span>
<span data-ttu-id="f0f84-186">이 옵션을 선택하면 쿼리 결과의 , , 또는 열에 있는 파일에 대해 **Quarantine** 파일 `SHA1` `InitiatingProcessSHA1` 작업을 `SHA256` `InitiatingProcessSHA256` 적용하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-186">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="f0f84-187">이 작업은 현재 위치에서 파일을 삭제하고 복사본을 검사에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-187">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="f0f84-188">사용자에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="f0f84-188">Actions on users</span></span>
<span data-ttu-id="f0f84-189">이 옵션을  선택하면 쿼리 결과의 , 또는 열에서 사용자에게 손상된 것으로 표시 작업이 `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-189">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="f0f84-190">이 작업은 Azure Active Directory에서 사용자 위험 수준을 "높음"으로 설정하여 해당 ID 보호 [정책을 트리거합니다.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="f0f84-190">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="f0f84-191">사용자 지정 검색 규칙에 대한 허용 또는 차단 작업은 현재 Microsoft 365 Defender에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-191">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="f0f84-192">5. 규칙 범위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-192">5. Set the rule scope.</span></span>
<span data-ttu-id="f0f84-193">범위를 설정하여 규칙에서 다루는 장치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-193">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="f0f84-194">이 범위는 장치를 검사하는 규칙에 영향을 주며 사서함과 사용자 계정 또는 ID만 검사하는 규칙에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-194">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="f0f84-195">범위를 설정할 때 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-195">When setting the scope, you can select:</span></span>

- <span data-ttu-id="f0f84-196">모든 장치</span><span class="sxs-lookup"><span data-stu-id="f0f84-196">All devices</span></span>
- <span data-ttu-id="f0f84-197">특정 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="f0f84-197">Specific device groups</span></span>

<span data-ttu-id="f0f84-198">범위에 있는 장치의 데이터만 Queried로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-198">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="f0f84-199">또한 해당 디바이스에서만 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-199">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="f0f84-200">6. 규칙을 검토하고 켜기.</span><span class="sxs-lookup"><span data-stu-id="f0f84-200">6. Review and turn on the rule.</span></span>
<span data-ttu-id="f0f84-201">규칙을 검토한 후 만들기를 **선택하여** 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-201">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="f0f84-202">사용자 지정 검색 규칙이 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-202">The custom detection rule immediately runs.</span></span> <span data-ttu-id="f0f84-203">구성된 빈도에 따라 다시 실행하여 일치를 확인하고, 경고를 생성하고, 대응 조치를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-203">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="f0f84-204">사용자 지정 검색은 효율성과 효율성을 위해 정기적으로 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-204">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="f0f84-205">실제 경고를 트리거하는 검색을 만들 수 있도록 기존 사용자 지정 검색 규칙 관리의 단계에 따라 기존 사용자 지정 검색을 [검토합니다.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="f0f84-205">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="f0f84-206">사용자 지정 검색에서 생성되는 모든 거짓 경고는 규칙의 특정 매개 변수를 수정해야 하도록 사용자 지정 검색의 광범위성 또는 특정성에 대한 제어를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-206">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="f0f84-207">기존 사용자 지정 검색 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="f0f84-207">Manage existing custom detection rules</span></span>
<span data-ttu-id="f0f84-208">기존 사용자 지정 검색 규칙 목록을 보고, 이전 실행을 확인하고, 트리거된 경고를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-208">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="f0f84-209">필요한 경우 규칙을 실행하고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-209">You can also run a rule on demand and modify it.</span></span>

>[!TIP]
> <span data-ttu-id="f0f84-210">사용자 지정 검색으로 발생된 경고는 경고 및 인시던트 API를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-210">Alerts raised by custom detections are available over alerts and incident APIs.</span></span> <span data-ttu-id="f0f84-211">자세한 내용은 지원되는 [Microsoft 365 Defender API를 참조하세요.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="f0f84-211">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="f0f84-212">기존 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="f0f84-212">View existing rules</span></span>

<span data-ttu-id="f0f84-213">기존 사용자 지정 검색 규칙을 모두 보기 위해 사용자 지정 검색 **헌팅으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0f84-213">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="f0f84-214">이 페이지에는 다음 실행 정보가 있는 모든 규칙이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-214">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="f0f84-215">**마지막 실행**- 쿼리 일치를 확인하고 경고를 생성하기 위해 규칙을 마지막으로 실행한 경우</span><span class="sxs-lookup"><span data-stu-id="f0f84-215">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="f0f84-216">**마지막 실행 상태**- 규칙이 성공적으로 실행된지 여부</span><span class="sxs-lookup"><span data-stu-id="f0f84-216">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="f0f84-217">**다음 실행**-다음 예약된 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-217">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="f0f84-218">**상태**- 규칙이 켜져 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="f0f84-218">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="f0f84-219">규칙 세부 정보 보기, 규칙 수정 및 규칙 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-219">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="f0f84-220">사용자 지정 검색 규칙에 대한 포괄적인 정보를 보기 위해 사용자 지정 검색 헌팅으로 이동한 다음 규칙 이름을  >   선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-220">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="f0f84-221">그런 다음 규칙에 대한 일반 정보(실행 상태 및 범위 포함)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-221">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="f0f84-222">또한 이 페이지에서는 트리거된 경고 및 작업 목록도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-222">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="f0f84-223">![사용자 지정 검색 규칙 세부 정보 페이지](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="f0f84-223">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="f0f84-224">*사용자 지정 검색 규칙 세부 정보*</span><span class="sxs-lookup"><span data-stu-id="f0f84-224">*Custom detection rule details*</span></span>

<span data-ttu-id="f0f84-225">이 페이지에서 규칙에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-225">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="f0f84-226">**를** 실행하여 규칙을 즉시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-226">**Run**—run the rule immediately.</span></span> <span data-ttu-id="f0f84-227">그러면 다음 실행 간격도 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-227">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="f0f84-228">**편집**- 쿼리를 변경하지 않고 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="f0f84-228">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="f0f84-229">**쿼리 수정**-고급 헌팅에서 쿼리 편집</span><span class="sxs-lookup"><span data-stu-id="f0f84-229">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="f0f84-230">**켜기**  /  **끄기**-규칙 사용 또는 실행 중지</span><span class="sxs-lookup"><span data-stu-id="f0f84-230">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="f0f84-231">**삭제**- 규칙을 끄고 제거</span><span class="sxs-lookup"><span data-stu-id="f0f84-231">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="f0f84-232">트리거된 경고 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="f0f84-232">View and manage triggered alerts</span></span>

<span data-ttu-id="f0f84-233">규칙 세부 정보 **화면(사용자** 지정 검색  >    >  **[규칙 이름]** 헌팅)에서 트리거된 경고로 이동하여 규칙과 일치하여 생성된 경고를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-233">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="f0f84-234">경고를 선택하여 자세한 정보를 보고 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-234">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="f0f84-235">상태 및 분류를 설정하여 경고 관리(참 또는 거짓 경고)</span><span class="sxs-lookup"><span data-stu-id="f0f84-235">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="f0f84-236">경고를 인시던트에 연결</span><span class="sxs-lookup"><span data-stu-id="f0f84-236">Link the alert to an incident</span></span>
- <span data-ttu-id="f0f84-237">고급 헌팅 시 경고를 트리거한 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="f0f84-237">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="f0f84-238">작업 검토</span><span class="sxs-lookup"><span data-stu-id="f0f84-238">Review actions</span></span>
<span data-ttu-id="f0f84-239">규칙 세부 정보 **화면(사용자** 지정 검색  >    >  **[규칙 이름]** 헌팅)에서 트리거된 작업으로 이동하여 규칙과 일치하는 일치를 기반으로 수행된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-239">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="f0f84-240">정보를 빠르게 보고 표의 항목에 대한 작업을 수행하기 위해 표 왼쪽에 있는 [&#10003;] 열을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f0f84-240">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

>[!NOTE]
><span data-ttu-id="f0f84-241">이 문서의 일부 열은 Microsoft Defender for Endpoint에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-241">Some columns in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f0f84-242">[Microsoft 365 Defender를 켜서](m365d-enable.md) 더 많은 데이터 원본을 사용하여 위협을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-242">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="f0f84-243">Endpoint용 Microsoft Defender에서 Microsoft Defender의 고급 헌팅 쿼리 마이그레이션의 단계에 따라 끝점용 [Microsoft Defender에서 Microsoft](advanced-hunting-migrate-from-mde.md)365 Defender로 고급 헌팅 워크플로를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f84-243">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0f84-244">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0f84-244">See also</span></span>
- [<span data-ttu-id="f0f84-245">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="f0f84-245">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="f0f84-246">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="f0f84-246">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f0f84-247">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="f0f84-247">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f0f84-248">끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f0f84-248">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
