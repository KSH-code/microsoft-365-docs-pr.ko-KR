---
title: Microsoft Defender ATP에서 고급 구하기 쿼리 마이그레이션
description: Microsoft Threat Protection에서 사용할 수 있도록 Microsoft Defender ATP 쿼리를 조정 하는 방법을 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, 원격 분석, 사용자 지정 검색, 스키마, kusto, microsoft 365, mapping
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
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429698"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="ee3c6-104">Microsoft Defender ATP에서 고급 구하기 쿼리 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ee3c6-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ee3c6-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ee3c6-105">**Applies to:**</span></span>
- <span data-ttu-id="ee3c6-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ee3c6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ee3c6-107">더 넓은 데이터 집합을 사용 하 여 Microsoft Defender ATP에서 위협에 대 한 사전 사냥으로 고급 구하기 워크플로를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="ee3c6-108">Microsoft Threat Protection에서는 다음을 비롯 한 다른 Microsoft 365 보안 솔루션의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="ee3c6-109">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee3c6-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="ee3c6-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee3c6-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="ee3c6-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ee3c6-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ee3c6-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee3c6-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="ee3c6-113">대부분의 Microsoft Defender ATP 고객은 [추가 라이선스 없이 Microsoft 위협 보호를 사용할](prerequisites.md#licensing-requirements)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="ee3c6-114">Microsoft Defender ATP에서 고급 구하기 워크플로 전환을 시작 하려면 [Microsoft Threat Protection을 켜십시오](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="ee3c6-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="ee3c6-115">기존 Microsoft Defender ATP 워크플로에 영향을 주지 않으면 서 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="ee3c6-116">저장 된 쿼리는 그대로 유지 되며 사용자 지정 검색 규칙은 계속 실행 되 고 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="ee3c6-117">그러나 Microsoft Threat Protection에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="ee3c6-118">Microsoft Threat Protection의 스키마 테이블만</span><span class="sxs-lookup"><span data-stu-id="ee3c6-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="ee3c6-119">[Microsoft Threat Protection 고급 구하기 스키마](advanced-hunting-schema-tables.md) 는 다양 한 Microsoft 365 보안 솔루션의 데이터를 포함 하는 추가 테이블을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="ee3c6-120">다음 테이블은 Microsoft Threat Protection 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="ee3c6-121">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="ee3c6-121">Table name</span></span> | <span data-ttu-id="ee3c6-122">설명</span><span class="sxs-lookup"><span data-stu-id="ee3c6-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="ee3c6-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ee3c6-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="ee3c6-124">알림과 연결 된 파일, IP 주소, Url, 사용자 또는 장치</span><span class="sxs-lookup"><span data-stu-id="ee3c6-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="ee3c6-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="ee3c6-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="ee3c6-126">심각도 정보 및 위협 범주를 포함 하 여 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security 및 Azure ATP의 알림</span><span class="sxs-lookup"><span data-stu-id="ee3c6-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="ee3c6-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="ee3c6-128">클라우드 앱 및 서비스의 파일 관련 활동</span><span class="sxs-lookup"><span data-stu-id="ee3c6-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="ee3c6-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="ee3c6-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="ee3c6-130">전자 메일에 첨부 된 파일에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="ee3c6-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="ee3c6-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="ee3c6-132">전자 메일 배달 및 차단 이벤트를 비롯 한 Microsoft 365 전자 메일 이벤트</span><span class="sxs-lookup"><span data-stu-id="ee3c6-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="ee3c6-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="ee3c6-134">Microsoft 365이 전자 메일을 받는 사람 사서함으로 배달 한 후 배달 후 발생 하는 보안 이벤트</span><span class="sxs-lookup"><span data-stu-id="ee3c6-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="ee3c6-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="ee3c6-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="ee3c6-136">전자 메일의 Url에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="ee3c6-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="ee3c6-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="ee3c6-138">AD (Active Directory)를 실행 하는 온-프레미스 도메인 컨트롤러를 포함 하는 이벤트</span><span class="sxs-lookup"><span data-stu-id="ee3c6-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="ee3c6-139">이 표에서는 도메인 컨트롤러의 id 관련 이벤트 및 시스템 이벤트 범위를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="ee3c6-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="ee3c6-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="ee3c6-141">Azure Active Directory를 비롯 한 다양 한 원본의 계정 정보</span><span class="sxs-lookup"><span data-stu-id="ee3c6-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="ee3c6-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="ee3c6-143">Active Directory 및 Microsoft online services의 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="ee3c6-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="ee3c6-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="ee3c6-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="ee3c6-145">Active Directory 개체에 대 한 쿼리 (예: 사용자, 그룹, 장치 및 도메인)</span><span class="sxs-lookup"><span data-stu-id="ee3c6-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="ee3c6-146">지도 DeviceAlertEvents 테이블</span><span class="sxs-lookup"><span data-stu-id="ee3c6-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="ee3c6-147">`AlertInfo`및 `AlertEvidence` 테이블은 `DeviceAlertEvents` Microsoft Defender ATP 스키마의 테이블을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="ee3c6-148">이러한 두 테이블은 장치 경고에 대 한 데이터 외에도 id, 앱 및 전자 메일에 대 한 경고에 대 한 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="ee3c6-149">다음 표를 사용 하 여 `DeviceAlertEvents` 열이 및 테이블의 열에 매핑되는 방식을 확인 `AlertInfo` `AlertEvidence` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="ee3c6-150">다음 표에는 열 외에도 `AlertEvidence` 다양 한 원본의 알림을 보다 광범위 하 게 나타내는 다양 한 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="ee3c6-151">모든 AlertEvidence 열 보기</span><span class="sxs-lookup"><span data-stu-id="ee3c6-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="ee3c6-152">DeviceAlertEvents 열</span><span class="sxs-lookup"><span data-stu-id="ee3c6-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="ee3c6-153">Microsoft Threat Protection에서 동일한 데이터를 찾을 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="ee3c6-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="ee3c6-154">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="ee3c6-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="ee3c6-155">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="ee3c6-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="ee3c6-156">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="ee3c6-157">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="ee3c6-158">`AlertInfo` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="ee3c6-159">`AlertInfo` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="ee3c6-160">`AlertInfo` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="ee3c6-161">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="ee3c6-162">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="ee3c6-163">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="ee3c6-164">`AlertEvidence` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="ee3c6-165">`AlertInfo` 목차가</span><span class="sxs-lookup"><span data-stu-id="ee3c6-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="ee3c6-166">이 열은 일반적으로 Microsoft Defender ATP에서 다른 테이블에 있는 관련 레코드를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="ee3c6-167">Microsoft Threat Protection에서는 표에서 관련 데이터를 직접 가져올 수 있습니다 `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="ee3c6-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="ee3c6-168">이 열은 일반적으로 Microsoft Defender ATP에서 다른 테이블의 추가 이벤트 정보를 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="ee3c6-169">Microsoft Threat Protection에서는 표에서 관련 데이터를 직접 가져올 수 있습니다 `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="ee3c6-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="ee3c6-170">기존 Microsoft Defender ATP 쿼리 조정</span><span class="sxs-lookup"><span data-stu-id="ee3c6-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="ee3c6-171">Microsoft Defender ATP 쿼리는 테이블을 참조 하지 않는 한 그대로 작동 `DeviceAlertEvents` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="ee3c6-172">Microsoft Threat Protection에서 이러한 쿼리를 사용 하려면 다음 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="ee3c6-173">`DeviceAlertEvents`로 대체 `AlertInfo` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="ee3c6-174">`AlertInfo`와 테이블을 조인 `AlertEvidence` 하 여 `AlertId` 동등한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="ee3c6-175">원래 쿼리</span><span class="sxs-lookup"><span data-stu-id="ee3c6-175">Original query</span></span>
<span data-ttu-id="ee3c6-176">다음 쿼리는 `DeviceAlertEvents` Microsoft DEFENDER ATP에서 _powershell.exe_를 포함 하는 경고를 가져오는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="ee3c6-177">수정 된 쿼리</span><span class="sxs-lookup"><span data-stu-id="ee3c6-177">Modified query</span></span>
<span data-ttu-id="ee3c6-178">다음 쿼리는 Microsoft Threat Protection에서 사용 하도록 조정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="ee3c6-179">파일 이름을 직접 확인 하는 대신 `DeviceAlertEvents` `AlertEvidence` 해당 테이블에서 파일 이름을 조인 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3c6-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="ee3c6-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ee3c6-180">Related topics</span></span>
- [<span data-ttu-id="ee3c6-181">Microsoft 위협 방지 설정</span><span class="sxs-lookup"><span data-stu-id="ee3c6-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ee3c6-182">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="ee3c6-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ee3c6-183">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="ee3c6-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ee3c6-184">Microsoft Defender ATP의 고급 구하기</span><span class="sxs-lookup"><span data-stu-id="ee3c6-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)