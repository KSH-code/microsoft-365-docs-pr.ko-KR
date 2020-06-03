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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a84c568d1411cf21c23e59cabad955c40c18ac6
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498366"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="2047c-104">사용자 지정 검색 규칙 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="2047c-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="2047c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2047c-105">**Applies to:**</span></span>
- <span data-ttu-id="2047c-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="2047c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2047c-107">[고급](advanced-hunting-overview.md) 검색 쿼리를 기반으로 작성 된 사용자 지정 감지 규칙을 사용 하면 의심 스러운 위반 작업과 잘못 구성 된 끝점을 비롯 한 다양 한 이벤트 및 시스템 상태를 사전에 모니터링할 수</span><span class="sxs-lookup"><span data-stu-id="2047c-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="2047c-108">이러한 항목은 일치 하는 모든 경우에 알림을 생성 하 고 응답 작업을 수행 하 여 정기적인 간격으로 실행 되도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="2047c-109">사용자 지정 검색을 관리 하는 데 필요한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="2047c-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="2047c-110">사용자 지정 검색을 관리 하려면 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="2047c-111">**보안 관리자** — 보안 관리자 또는 보안 관리자 역할은 Microsoft 365 보안 센터 및 다양 한 포털 및 서비스에서 다양 한 보안 설정을 관리 하는 데 사용할 수 있는 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 입니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="2047c-112">**보안 운영자** — 보안 운영자 역할은 경고를 관리 하 고 Microsoft 365 보안 센터의 모든 정보를 포함 하 여 보안 관련 기능에 대 한 전역 읽기 전용 액세스 권한이 있는 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 입니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="2047c-113">이 역할은 Microsoft Defender ATP에서 RBAC (역할 기반 액세스 제어)가 해제 된 경우에만 사용자 지정 검색을 관리 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="2047c-114">RBAC를 구성한 경우에는 Microsoft Defender ATP에 대 한 **보안 설정 관리** 권한도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="2047c-115">**전역 관리자** 는 필요한 권한을 관리 하기 위해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="2047c-116">**역할**보안 관리자 아래의 [Microsoft 365 관리 센터](https://admin.microsoft.com/) 에서 **보안 관리자** 또는 **보안 운영자** 역할을 할당 합니다  >  **Security admin**.</span><span class="sxs-lookup"><span data-stu-id="2047c-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="2047c-117">**설정**사용 권한 역할 아래의 [microsoft defender Security Center](https://securitycenter.windows.com/) 에서 microsoft defender ATP에 대 한 RBAC 설정을 확인  >  **Permissions**  >  **Roles**합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="2047c-118">해당 하는 역할을 선택 하 여 **보안 설정 관리** 권한을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="2047c-119">RBAC가 설정 된 경우 사용자 지정 검색을 관리 하려면 **보안 운영자** 에 게 MICROSOFT Defender ATP의 **보안 설정 관리** 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="2047c-120">사용자 지정 검색 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="2047c-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="2047c-121">1. 쿼리를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-121">1. Prepare the query.</span></span>

<span data-ttu-id="2047c-122">Microsoft 365 보안 센터에서 **고급 구하기** 로 이동 하 여 기존 쿼리를 선택 하거나 새 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="2047c-123">새 쿼리를 사용할 때 쿼리를 실행 하 여 오류를 식별 하 고 가능한 결과를 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="2047c-124">쿼리 결과의 필수 열</span><span class="sxs-lookup"><span data-stu-id="2047c-124">Required columns in the query results</span></span>
<span data-ttu-id="2047c-125">사용자 지정 검색 규칙을 만들려면 쿼리가 다음 열을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="2047c-126">다음 장치, 사용자 또는 사서함 열 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="2047c-127">`SenderFromAddress`(봉투 보낸 사람 또는 반환 경로 주소)</span><span class="sxs-lookup"><span data-stu-id="2047c-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="2047c-128">`SenderMailFromAddress`(전자 메일 클라이언트에 의해 표시 되는 보낸 사람 주소)</span><span class="sxs-lookup"><span data-stu-id="2047c-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="2047c-129">새 테이블이 [고급 구하기 스키마](advanced-hunting-schema-tables.md)에 추가 되 면 추가 엔터티에 대 한 지원이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="2047c-130">결과를 사용자 지정 하거나 집계 하기 위해 or 연산자를 사용 하지 않는 것과 같은 단순한 쿼리는 `project` `summarize` 일반적으로 이러한 공통 열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="2047c-131">좀 더 복잡 한 쿼리가 이러한 열을 반환 하 게 하는 다양 한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="2047c-132">예를 들어와 같은 열에 따라 엔터티에 대해 집계 하 고 개수를 계산 하려는 경우에는 `DeviceId` `Timestamp` 각 고유 항목을 포함 하는 최근 이벤트에서 가져오는 방식으로 반환할 수 있습니다 `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="2047c-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="2047c-133">아래 예제 쿼리는 바이러스 백신 검색이 포함 된 고유한 장치 수를 계산 하 `DeviceId` 고이 수를 사용 하 여 검색 수가 5 개 이상인 장치만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-133">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="2047c-134">이 메서드는 가장 최근 개체를 반환 하기 위해 `Timestamp` `summarize` 함수와 함께 연산자를 사용 `arg_max` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="2047c-135">2. 새 규칙을 만들고 알림 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="2047c-136">쿼리 편집기에서 쿼리를 사용 하 여 **검색 규칙 만들기** 를 선택 하 고 다음 알림 세부 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="2047c-137">**검색 이름** — 검색 규칙의 이름</span><span class="sxs-lookup"><span data-stu-id="2047c-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="2047c-138">**빈도** — 쿼리를 실행 하 고 작업을 수행 하기 위한 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="2047c-139">아래 추가 지침 보기</span><span class="sxs-lookup"><span data-stu-id="2047c-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="2047c-140">**알림 제목** — 규칙에 의해 트리거된 경고와 함께 표시 되는 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="2047c-141">**심각도** — 구성 요소나 작업의 잠재적 위험을 규칙으로 식별</span><span class="sxs-lookup"><span data-stu-id="2047c-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="2047c-142">**범주** -규칙에 따라 식별 되는 위협 구성 요소 또는 활동</span><span class="sxs-lookup"><span data-stu-id="2047c-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="2047c-143">**MITRE at&t&접시 헤드 기술** - [MITRE at&t&접시 프레임 워크](https://attack.mitre.org/)에 설명 된 것 처럼 규칙으로 식별 되는 하나 이상의 공격 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="2047c-144">이 섹션은 맬웨어, 랜 섬 웨어, 의심 스러운 활동 및 원치 않는 소프트웨어를 비롯 한 특정 경고 범주에 대해서는 적용 되지 않으며 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-144">This section does not apply and is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="2047c-145">**설명** — 규칙으로 식별 되는 구성 요소 또는 작업에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="2047c-145">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="2047c-146">**권장 작업** — 응답 자가 경고에 대해 취할 수 있는 추가 작업</span><span class="sxs-lookup"><span data-stu-id="2047c-146">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="2047c-147">규칙 빈도</span><span class="sxs-lookup"><span data-stu-id="2047c-147">Rule frequency</span></span>
<span data-ttu-id="2047c-148">저장 하면 새로 만들거나 편집한 사용자 지정 검색 규칙이 즉시 실행 되 고 최근 30 일 동안의 일치 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-148">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="2047c-149">그런 다음 일정 간격으로 규칙을 다시 실행 하 고 선택한 빈도에 따라 기간을 lookback 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-149">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="2047c-150">**24 시간** 마다-24 시간 마다 실행 되며 지난 30 일 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-150">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="2047c-151">**12 시간 마다** -12 시간 마다 실행 되며 지난 24 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-151">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="2047c-152">**3 시간** 마다-3 시간 마다 실행 되며 지난 6 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-152">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="2047c-153">**1 시간 마다** -매시간 실행 되며 지난 2 시간 동안의 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-153">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="2047c-154">검색을 모니터링할 간격을 일치 시키는 빈도를 선택 하 고, 조직에서 경고에 응답할 수 있는 용량을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-154">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="2047c-155">3. 영향을 받는 엔터티를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-155">3. Choose the impacted entities.</span></span>
<span data-ttu-id="2047c-156">영향을 받는 주요 엔터티나 해당 엔터티를 찾을 것으로 예상 되는 쿼리 결과의 열을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-156">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="2047c-157">예를 들어 쿼리는 보낸 사람 ( `SenderFromAddress` 또는 `SenderMailFromAddress` ) 및 받는 사람 ( `RecipientEmailAddress` ) 주소를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-157">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="2047c-158">이러한 어떤 열이 영향을 받는 주요 엔터티를 나타내는 것을 확인 하면 서비스에서 관련 경고를 집계 하 고 인시던트와 대상 응답 작업을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-158">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="2047c-159">각 엔터티 유형 (사서함, 사용자 또는 장치)에 대해 열을 하나만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-159">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="2047c-160">쿼리에 의해 반환 되지 않는 열은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-160">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="2047c-161">4. 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-161">4. Specify actions.</span></span>
<span data-ttu-id="2047c-162">사용자 지정 검색 규칙은 쿼리에서 반환 된 장치, 파일 또는 사용자에 대 한 작업을 자동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-162">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="2047c-163">장치에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="2047c-163">Actions on devices</span></span>
<span data-ttu-id="2047c-164">이러한 작업은 쿼리 결과 열에 있는 장치에 적용 됩니다 `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="2047c-164">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="2047c-165">**장치 격리** -MICROSOFT Defender ATP를 사용 하 여 전체 네트워크 격리를 적용 하 여 장치가 어떤 응용 프로그램 또는 서비스에도 연결 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-165">**Isolate device** — uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="2047c-166">Microsoft Defender ATP 컴퓨터 격리에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="2047c-166">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="2047c-167">**수집 조사 패키지** -ZIP 파일의 장치 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-167">**Collect investigation package** — collects device information in a ZIP file.</span></span> [<span data-ttu-id="2047c-168">Microsoft Defender ATP 조사 패키지에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="2047c-168">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="2047c-169">**바이러스 검사 실행** -장치에서 전체 Windows Defender 바이러스 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-169">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="2047c-170">**시작 조사** -장치에 대 한 [자동화 된 조사](mtp-autoir.md) 시작</span><span class="sxs-lookup"><span data-stu-id="2047c-170">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="2047c-171">**앱 실행 제한** -Microsoft에서 발급 한 인증서로 서명 된 파일만 실행 하도록 장치에 대 한 제한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-171">**Restrict app execution** — sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="2047c-172">앱 제한에 대 한 자세한 내용은 Microsoft Defender ATP를 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2047c-172">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="2047c-173">파일 작업</span><span class="sxs-lookup"><span data-stu-id="2047c-173">Actions on files</span></span>
<span data-ttu-id="2047c-174">이 방법을 선택 하면 **Quarantine file** `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` 쿼리 결과의,, 또는 열에 파일에 대 한 파일 격리 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-174">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="2047c-175">이 동작은 현재 위치에서 파일을 삭제 하 고 격리에 복사본을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-175">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="2047c-176">사용자에 대 한 작업</span><span class="sxs-lookup"><span data-stu-id="2047c-176">Actions on users</span></span>
<span data-ttu-id="2047c-177">이 **확인란** 을 선택 하면 `AccountObjectId` `InitiatingProcessAccountObjectId` 쿼리 결과의, 또는 열에 있는 사용자가 사용자에 게 작업을 손상 시킬 수 `RecipientObjectId` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-177">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="2047c-178">이 작업은 Azure Active Directory에서 사용자 위험 수준을 "높음"으로 설정 하 여 해당 하는 [id 보호 정책을](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-178">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="2047c-179">사용자 지정 검색 규칙에 대 한 allow 또는 block 작업은 현재 Microsoft Threat Protection에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-179">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="2047c-180">5. 규칙 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-180">5. Set the rule scope.</span></span>
<span data-ttu-id="2047c-181">범위를 설정 하 여 규칙에 포함 되는 장치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-181">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="2047c-182">범위는 장치를 확인 하는 규칙에 영향을 주며 사서함과 사용자 계정 또는 id만 검사 하는 규칙에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-182">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="2047c-183">범위를 설정 하는 경우 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-183">When setting the scope, you can select:</span></span>

- <span data-ttu-id="2047c-184">모든 장치</span><span class="sxs-lookup"><span data-stu-id="2047c-184">All devices</span></span>
- <span data-ttu-id="2047c-185">특정 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="2047c-185">Specific device groups</span></span>

<span data-ttu-id="2047c-186">범위에 있는 장치의 데이터만 쿼리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="2047c-187">또한 해당 장치 에서만 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-187">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="2047c-188">6. 규칙을 검토 하 고 켭니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-188">6. Review and turn on the rule.</span></span>
<span data-ttu-id="2047c-189">규칙을 검토 한 후 **만들기** 를 클릭 하 여 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-189">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="2047c-190">사용자 지정 검색 규칙이 즉시 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="2047c-191">구성 된 빈도에 따라 다시 실행 하 여 일치 여부를 확인 하 고 경고를 생성 하 고 응답 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="2047c-192">기존 사용자 지정 검색 규칙 관리</span><span class="sxs-lookup"><span data-stu-id="2047c-192">Manage existing custom detection rules</span></span>
<span data-ttu-id="2047c-193">기존 사용자 지정 검색 규칙 목록을 확인 하 고, 이전 실행을 확인 하 고, 트리거된 경고를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-193">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="2047c-194">요청에 대해 규칙을 실행 하 여 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-194">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="2047c-195">기존 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="2047c-195">View existing rules</span></span>

<span data-ttu-id="2047c-196">기존의 모든 사용자 지정 검색 규칙을 보려면 **사냥**  >  **사용자 지정**감지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-196">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="2047c-197">다음 실행 정보와 함께 모든 규칙이 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-197">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="2047c-198">**마지막 실행** -쿼리 일치를 확인 하기 위해 규칙을 마지막으로 실행 한 시기 및 경고 생성</span><span class="sxs-lookup"><span data-stu-id="2047c-198">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="2047c-199">**마지막 실행 상태** -규칙이 성공적으로 실행 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="2047c-199">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="2047c-200">**다음 실행** -예약 된 다음 실행</span><span class="sxs-lookup"><span data-stu-id="2047c-200">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="2047c-201">**상태** -규칙이 설정 또는 해제 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="2047c-201">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="2047c-202">규칙 세부 정보 보기, 규칙 수정 및 규칙 실행</span><span class="sxs-lookup"><span data-stu-id="2047c-202">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="2047c-203">사용자 지정 검색 규칙에 대 한 포괄적인 정보를 보려면 **사냥**  >  **사용자 지정 감지**의 규칙 목록에서 규칙의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-203">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="2047c-204">이렇게 하면 경고, 실행 상태 및 범위에 대 한 세부 정보를 비롯 하 여 규칙에 대 한 일반 정보를 포함 하는 사용자 지정 검색 규칙에 대 한 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-204">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="2047c-205">또한 트리거된 경고 및 트리거된 작업의 목록만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-205">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="2047c-206">![사용자 지정 검색 규칙 세부 정보 페이지](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="2047c-206">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="2047c-207">*사용자 지정 검색 규칙 세부 정보*</span><span class="sxs-lookup"><span data-stu-id="2047c-207">*Custom detection rule details*</span></span>

<span data-ttu-id="2047c-208">또한이 페이지의 규칙에 대해 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-208">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="2047c-209">**실행** -규칙을 즉시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-209">**Run** — run the rule immediately.</span></span> <span data-ttu-id="2047c-210">또한 다음 실행에 대 한 간격이 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-210">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="2047c-211">**편집** -쿼리를 변경 하지 않고 규칙 수정</span><span class="sxs-lookup"><span data-stu-id="2047c-211">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="2047c-212">**수정 쿼리** -고급 검색에서 쿼리를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-212">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="2047c-213">**켜기**  /  **해제** -규칙을 사용 하도록 설정 하거나 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-213">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="2047c-214">**삭제** -규칙을 해제 하 고 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-214">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="2047c-215">트리거된 알림 보기 및 관리</span><span class="sxs-lookup"><span data-stu-id="2047c-215">View and manage triggered alerts</span></span>

<span data-ttu-id="2047c-216">규칙 세부 정보 화면 (**사냥**  >  **사용자 지정**  >  검색 **[규칙 이름]**)에서 **트리거된 경고** 로 이동 하 여 규칙과 일치 하는 항목에 의해 생성 된 경고 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="2047c-217">경고를 선택 하 여 해당 경고에 대 한 세부 정보를 확인 하 고 해당 경고에 대해 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-217">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="2047c-218">상태 및 분류 (참 또는 거짓 경고)를 설정 하 여 경고를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-218">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="2047c-219">인시던트에 경고 연결</span><span class="sxs-lookup"><span data-stu-id="2047c-219">Link the alert to an incident</span></span>
- <span data-ttu-id="2047c-220">고급 구하기에 대 한 경고를 트리거한 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="2047c-220">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="2047c-221">작업 검토</span><span class="sxs-lookup"><span data-stu-id="2047c-221">Review actions</span></span>
<span data-ttu-id="2047c-222">규칙 세부 정보 화면 (**사냥**  >  **사용자 지정**검색  >  **[규칙 이름]**)에서 **트리거된 작업** 으로 이동 하 여 규칙에 대 한 일치 항목을 기준으로 수행한 작업 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-222">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="2047c-223">테이블의 항목에 대 한 정보를 빠르게 확인 하 고 작업을 수행 하려면 표 왼쪽에 있는 선택 열인 [&#10003;]을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2047c-223">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="2047c-224">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2047c-224">Related topic</span></span>
- [<span data-ttu-id="2047c-225">사용자 지정 검색 개요</span><span class="sxs-lookup"><span data-stu-id="2047c-225">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="2047c-226">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="2047c-226">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2047c-227">고급 헌팅 쿼리 언어 알아보기</span><span class="sxs-lookup"><span data-stu-id="2047c-227">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)