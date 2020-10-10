---
title: Microsoft Threat Protection에서 사용자 지정 검색 규칙 만들기 및 관리
description: 고급 검색 쿼리를 기반으로 사용자 지정 검색 규칙을 만들고 관리 하는 방법에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 규칙, 스키마, kusto, microsoft 365, Microsoft Threat Protection, RBAC, 사용 권한, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: a0fb30915cac875e1e5278ecec2b3a1c65685f37
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412529"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="c5aea-104">사용자 지정 검색 규칙 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="c5aea-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5aea-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c5aea-105">**Applies to:**</span></span>
- <span data-ttu-id="c5aea-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="c5aea-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c5aea-107">사용자 지정 검색 규칙은 [고급](advanced-hunting-overview.md) 검색 쿼리를 사용 하 여 디자인 하 고 조정할 수 있는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="c5aea-108">이러한 규칙을 사용 하면 의심 스러운 위반 작업과 잘못 구성 된 끝점을 비롯 한 다양 한 이벤트 및 시스템 상태를 사전에 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c5aea-109">이러한 항목은 일치 하는 모든 경우에 알림을 생성 하 고 응답 작업을 수행 하 여 정기적인 간격으로 실행 되도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="c5aea-110">사용자 지정 검색을 관리 하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c5aea-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="c5aea-111">사용자 지정 검색을 관리 하려면 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="c5aea-112">**보안 관리자**—이 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 을 사용 하는 사용자는 Microsoft 365 보안 센터 및 기타 포털 및 서비스에서 보안 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="c5aea-113">**보안 운영자**—이 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 을 가진 사용자는 알림을 관리 하 고 Microsoft 365 보안 센터의 모든 정보를 포함 하 여 보안 관련 기능에 대 한 전역 읽기 전용 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="c5aea-114">이 역할은 Microsoft Defender ATP에서 RBAC (역할 기반 액세스 제어)가 해제 된 경우에만 사용자 지정 검색을 관리 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="c5aea-115">RBAC를 구성한 경우에는 Microsoft Defender ATP에 대 한 **보안 설정 관리** 권한도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-115">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="c5aea-116">**전역 관리자** 는 필요한 권한을 관리 하기 위해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="c5aea-117">**역할**보안 관리자 아래의 [Microsoft 365 관리 센터](https://admin.microsoft.com/) 에서 **보안 관리자** 또는 **보안 운영자** 역할을 할당 합니다  >  **Security admin**.</span><span class="sxs-lookup"><span data-stu-id="c5aea-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="c5aea-118">**설정**사용 권한 역할 아래의 [microsoft defender Security Center](https://securitycenter.windows.com/) 에서 microsoft defender ATP에 대 한 RBAC 설정을 확인  >  **Permissions**  >  **Roles**합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-118">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="c5aea-119">해당 하는 역할을 선택 하 여 **보안 설정 관리** 권한을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="c5aea-120">RBAC가 설정 된 경우 사용자 지정 검색을 관리 하려면 **보안 운영자** 에 게 MICROSOFT Defender ATP의 **보안 설정 관리** 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="c5aea-121">사용자 지정 검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="c5aea-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="c5aea-122">1. 쿼리를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-122">1. Prepare the query.</span></span>

<span data-ttu-id="c5aea-123">Microsoft 365 보안 센터에서 **고급 구하기** 로 이동 하 여 기존 쿼리를 선택 하거나 새 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="c5aea-124">새 쿼리를 사용할 때 쿼리를 실행 하 여 오류를 식별 하 고 가능한 결과를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c5aea-125">서비스가 너무 많은 경고를 반환 하지 못하게 하기 위해 각 규칙은 실행 될 때마다 100 경고만 생성 하도록 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="c5aea-126">규칙을 만들기 전에 일상적인 활동에 대 한 경고를 방지 하기 위해 쿼리를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="c5aea-127">쿼리 결과의 필수 열</span><span class="sxs-lookup"><span data-stu-id="c5aea-127">Required columns in the query results</span></span>
<span data-ttu-id="c5aea-128">사용자 지정 검색 규칙을 만들려면 쿼리가 다음 열을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="c5aea-129">`Timestamp`-생성 된 경고에 대 한 타임 스탬프를 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="c5aea-130">`ReportId`— 원본 레코드에 대 한 조회 사용</span><span class="sxs-lookup"><span data-stu-id="c5aea-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="c5aea-131">특정 장치, 사용자 또는 사서함을 식별 하는 다음 열 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="c5aea-132">`SenderFromAddress` (봉투 보낸 사람 또는 Return-Path 주소)</span><span class="sxs-lookup"><span data-stu-id="c5aea-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="c5aea-133">`SenderMailFromAddress` (전자 메일 클라이언트에 의해 표시 되는 보낸 사람 주소)</span><span class="sxs-lookup"><span data-stu-id="c5aea-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="c5aea-134">새 테이블이 [고급 구하기 스키마](advanced-hunting-schema-tables.md)에 추가 되 면 추가 엔터티에 대 한 지원이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="c5aea-135">결과를 사용자 지정 하거나 집계 하기 위해 or 연산자를 사용 하지 않는 것과 같은 단순한 쿼리는 `project` `summarize` 일반적으로 이러한 공통 열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="c5aea-136">좀 더 복잡 한 쿼리가 이러한 열을 반환 하 게 하는 다양 한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="c5aea-137">예를 들어와 같은 열에서 엔터티를 집계 하 고 개수를 계산 하려는 경우에는 `DeviceId` `Timestamp` 각 고유 항목을 `ReportId` 포함 하는 최신 이벤트에서 반환 하 고 가져올 수 있습니다 `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="c5aea-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="c5aea-138">아래 예제 쿼리는 바이러스 백신 검색이 포함 된 고유한 장치 수를 계산 하 `DeviceId` 고이 수를 사용 하 여 검색 수가 5 개 이상인 장치만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="c5aea-139">가장 최근 항목과 해당 하는 개체를 반환 하려면 `Timestamp` `ReportId` 함수에 연산자를 사용 `summarize` `arg_max` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="c5aea-140">쿼리 성능을 개선 하려면 규칙의 의도 한 실행 빈도와 일치 하는 시간 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="c5aea-141">가장 자주 실행 되는 시간은 _24 시간 마다_다르기 때문에 지난 날 필터링은 모든 새 데이터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="c5aea-142">2. 새 규칙을 만들고 알림 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="c5aea-143">쿼리 편집기에서 쿼리를 사용 하 여 **검색 규칙 만들기** 를 선택 하 고 다음 알림 세부 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="c5aea-144">**검색 이름**— 검색 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="c5aea-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="c5aea-145">**빈도**— 쿼리를 실행 하 고 작업을 수행 하기 위한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="c5aea-146">아래 추가 지침 보기</span><span class="sxs-lookup"><span data-stu-id="c5aea-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="c5aea-147">**알림 제목**— 규칙에 의해 트리거된 경고와 함께 표시 되는 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="c5aea-148">**심각도**— 구성 요소나 작업의 잠재적 위험을 규칙으로 식별</span><span class="sxs-lookup"><span data-stu-id="c5aea-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="c5aea-149">**범주**-규칙에 따라 식별 되는 위협 구성 요소 또는 활동</span><span class="sxs-lookup"><span data-stu-id="c5aea-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="c5aea-150">**MITRE at&t&접시 헤드 기술**- [MITRE at&t&접시 프레임 워크](https://attack.mitre.org/)에 설명 된 것 처럼 규칙으로 식별 되는 하나 이상의 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="c5aea-151">이 섹션은 맬웨어, 랜 섬 웨어, 의심 스러운 활동 및 원치 않는 소프트웨어를 비롯 한 특정 경고 범주에 대해 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="c5aea-152">**설명**— 규칙으로 식별 되는 구성 요소 또는 작업에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c5aea-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="c5aea-153">**권장 작업**— 응답 자가 경고에 대해 취할 수 있는 추가 작업</span><span class="sxs-lookup"><span data-stu-id="c5aea-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="c5aea-154">규칙 빈도</span><span class="sxs-lookup"><span data-stu-id="c5aea-154">Rule frequency</span></span>
<span data-ttu-id="c5aea-155">새 규칙을 저장 하거나 편집할 때이를 실행 하 고 최근 30 일 동안의 일치 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="c5aea-156">이 규칙은 고정 된 간격으로 다시 실행 되며 선택한 빈도에 따라 lookback 기간이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="c5aea-157">**24 시간**마다-24 시간 마다 실행 되며 지난 30 일 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="c5aea-158">**12 시간 마다**-12 시간 마다 실행 되며 지난 24 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="c5aea-159">**3 시간**마다-3 시간 마다 실행 되며 지난 6 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="c5aea-160">**1 시간 마다**-매시간 실행 되며 지난 2 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="c5aea-161">쿼리의 시간 필터를 lookback 기간과 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="c5aea-162">Lookback 기간을 벗어난 결과는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="c5aea-163">검색을 모니터링할 정도와 일치 하는 빈도를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="c5aea-164">조직의 용량을 고려 하 여 경고에 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="c5aea-165">3. 영향을 받는 엔터티를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="c5aea-166">영향을 받는 주요 엔터티나 해당 엔터티를 찾을 것으로 예상 되는 쿼리 결과의 열을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="c5aea-167">예를 들어 쿼리는 보낸 사람 ( `SenderFromAddress` 또는 `SenderMailFromAddress` ) 및 받는 사람 ( `RecipientEmailAddress` ) 주소를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="c5aea-168">이러한 어떤 열이 영향을 받는 주요 엔터티를 나타내는 것을 확인 하면 서비스에서 관련 경고를 집계 하 고 인시던트와 대상 응답 작업을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="c5aea-169">각 엔터티 유형 (사서함, 사용자 또는 장치)에 대해 열을 하나만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="c5aea-170">쿼리에 의해 반환 되지 않는 열은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="c5aea-171">4. 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-171">4. Specify actions.</span></span>
<span data-ttu-id="c5aea-172">사용자 지정 검색 규칙은 쿼리에서 반환 된 장치, 파일 또는 사용자에 대 한 작업을 자동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="c5aea-173">장치에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="c5aea-173">Actions on devices</span></span>
<span data-ttu-id="c5aea-174">이러한 작업은 쿼리 결과 열에 있는 장치에 적용 됩니다 `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="c5aea-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="c5aea-175">**장치 격리**-MICROSOFT Defender ATP를 사용 하 여 전체 네트워크 격리를 적용 하 여 장치가 어떤 응용 프로그램 또는 서비스에도 연결 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-175">**Isolate device**—uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="c5aea-176">Microsoft Defender ATP 컴퓨터 격리에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c5aea-176">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="c5aea-177">**수집 조사 패키지**-ZIP 파일의 장치 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="c5aea-178">Microsoft Defender ATP 조사 패키지에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c5aea-178">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="c5aea-179">**바이러스 검사 실행**-장치에서 전체 Windows Defender 바이러스 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="c5aea-180">**시작 조사**-장치에 대 한 [자동화 된 조사](mtp-autoir.md) 시작</span><span class="sxs-lookup"><span data-stu-id="c5aea-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="c5aea-181">**앱 실행 제한**-Microsoft에서 발급 한 인증서로 서명 된 파일만 실행 하도록 장치에 대 한 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="c5aea-182">앱 제한에 대 한 자세한 내용은 Microsoft Defender ATP를 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5aea-182">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="c5aea-183">파일 작업</span><span class="sxs-lookup"><span data-stu-id="c5aea-183">Actions on files</span></span>
<span data-ttu-id="c5aea-184">이 방법을 선택 하면 **Quarantine file** `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 쿼리 결과의,, 또는 열에 파일에 대 한 파일 격리 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="c5aea-185">이 동작은 현재 위치에서 파일을 삭제 하 고 격리에 복사본을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="c5aea-186">사용자에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="c5aea-186">Actions on users</span></span>
<span data-ttu-id="c5aea-187">이 **확인란** 을 선택 하면 `AccountObjectId` `InitiatingProcessAccountObjectId` 쿼리 결과의, 또는 열에 있는 사용자가 사용자에 게 작업을 손상 시킬 수 `RecipientObjectId` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="c5aea-188">이 작업은 Azure Active Directory에서 사용자 위험 수준을 "높음"으로 설정 하 여 해당 하는 [id 보호 정책을](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="c5aea-189">사용자 지정 검색 규칙에 대 한 allow 또는 block 작업은 현재 Microsoft Threat Protection에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-189">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="c5aea-190">5. 규칙 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-190">5. Set the rule scope.</span></span>
<span data-ttu-id="c5aea-191">범위를 설정 하 여 규칙에 포함 되는 장치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="c5aea-192">범위는 장치를 확인 하는 규칙에 영향을 주며 사서함과 사용자 계정 또는 id만 검사 하는 규칙에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="c5aea-193">범위를 설정 하는 경우 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="c5aea-194">모든 장치</span><span class="sxs-lookup"><span data-stu-id="c5aea-194">All devices</span></span>
- <span data-ttu-id="c5aea-195">특정 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="c5aea-195">Specific device groups</span></span>

<span data-ttu-id="c5aea-196">범위에 있는 장치의 데이터만 쿼리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="c5aea-197">또한 해당 장치 에서만 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="c5aea-198">6. 규칙을 검토 하 고 켭니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="c5aea-199">규칙을 검토 한 후 **만들기** 를 선택 하 여 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="c5aea-200">사용자 지정 검색 규칙이 즉시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="c5aea-201">구성 된 빈도에 따라 다시 실행 하 여 일치 여부를 확인 하 고 경고를 생성 하 고 응답 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="c5aea-202">기존 사용자 지정 검색 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="c5aea-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="c5aea-203">기존 사용자 지정 검색 규칙 목록을 확인 하 고, 이전 실행을 확인 하 고, 트리거된 경고를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="c5aea-204">요청에 대해 규칙을 실행 하 여 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="c5aea-205">기존 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="c5aea-205">View existing rules</span></span>

<span data-ttu-id="c5aea-206">기존의 모든 사용자 지정 검색 규칙을 보려면 **사냥**  >  **사용자 지정**감지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="c5aea-207">다음 실행 정보와 함께 모든 규칙이 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="c5aea-208">**마지막 실행**-쿼리 일치를 확인 하기 위해 규칙을 마지막으로 실행 한 시기 및 경고 생성</span><span class="sxs-lookup"><span data-stu-id="c5aea-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="c5aea-209">**마지막 실행 상태**-규칙이 성공적으로 실행 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="c5aea-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="c5aea-210">**다음 실행**-예약 된 다음 실행</span><span class="sxs-lookup"><span data-stu-id="c5aea-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="c5aea-211">**상태**-규칙이 설정 또는 해제 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="c5aea-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="c5aea-212">규칙 세부 정보 보기, 규칙 수정 및 규칙 실행</span><span class="sxs-lookup"><span data-stu-id="c5aea-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="c5aea-213">사용자 지정 검색 규칙에 대 한 포괄적인 정보를 보려면 **사냥**  >  **사용자 지정** 감지로 이동한 다음 규칙의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="c5aea-214">그런 다음 규칙에 대 한 일반 정보 (실행 상태 및 범위 정보 포함)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="c5aea-215">이 페이지에는 트리거된 경고 및 작업의 목록도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="c5aea-216">![사용자 지정 검색 규칙 세부 정보 페이지](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="c5aea-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="c5aea-217">*사용자 지정 검색 규칙 세부 정보*</span><span class="sxs-lookup"><span data-stu-id="c5aea-217">*Custom detection rule details*</span></span>

<span data-ttu-id="c5aea-218">또한이 페이지의 규칙에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="c5aea-219">**실행**-규칙을 즉시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="c5aea-220">또한 다음 실행에 대 한 간격이 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="c5aea-221">**편집**-쿼리를 변경 하지 않고 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="c5aea-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="c5aea-222">**수정 쿼리**-고급 검색에서 쿼리를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="c5aea-223">**켜기**  /  **해제**-규칙을 사용 하도록 설정 하거나 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="c5aea-224">**삭제**-규칙을 해제 하 고 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="c5aea-225">트리거된 알림 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="c5aea-225">View and manage triggered alerts</span></span>

<span data-ttu-id="c5aea-226">규칙 세부 정보 화면 (**사냥**  >  **사용자 지정**  >  검색 **[규칙 이름]**)에서 규칙에 대 한 일치 항목에 의해 생성 된 경고를 나열 하는 **트리거된 알림에**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="c5aea-227">알림을 선택 하 여 자세한 정보를 확인 하 고 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="c5aea-228">상태 및 분류 (참 또는 거짓 경고)를 설정 하 여 경고를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="c5aea-229">인시던트에 경고 연결</span><span class="sxs-lookup"><span data-stu-id="c5aea-229">Link the alert to an incident</span></span>
- <span data-ttu-id="c5aea-230">고급 구하기에 대 한 경고를 트리거한 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="c5aea-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="c5aea-231">작업 검토</span><span class="sxs-lookup"><span data-stu-id="c5aea-231">Review actions</span></span>
<span data-ttu-id="c5aea-232">규칙 세부 정보 화면 (**사냥**  >  **사용자 지정**  >  검색 **[규칙 이름]**)에서 **트리거된 작업**으로 이동 하 여 규칙에 대 한 일치 항목을 기준으로 수행한 작업을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="c5aea-233">테이블의 항목에 대 한 정보를 빠르게 확인 하 고 작업을 수행 하려면 표 왼쪽에 있는 선택 열인 [&#10003;]을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aea-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="c5aea-234">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c5aea-234">Related topic</span></span>
- [<span data-ttu-id="c5aea-235">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="c5aea-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="c5aea-236">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="c5aea-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5aea-237">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="c5aea-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
