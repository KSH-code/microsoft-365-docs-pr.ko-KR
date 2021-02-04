---
title: 끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션
description: Microsoft 365 Defender에서 사용할 수 있도록 끝점용 Microsoft Defender 쿼리를 조정하는 방법에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, microsoft defender atp, mdatp, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, microsoft 365, 매핑
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094810"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="a960a-104">끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a960a-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a960a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a960a-105">**Applies to:**</span></span>
- <span data-ttu-id="a960a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a960a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a960a-107">끝점용 Microsoft Defender의 고급 헌팅 워크플로를 이동하여 광범위한 데이터 집합을 사용하여 위협을 사전 예방적으로 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="a960a-108">Microsoft 365 Defender에서 다음을 비롯한 다른 Microsoft 365 보안 솔루션의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="a960a-109">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a960a-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a960a-110">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a960a-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="a960a-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a960a-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a960a-112">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a960a-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="a960a-113">대부분의 엔드포인트용 Microsoft Defender 고객은 추가 라이선스 없이 [Microsoft 365 Defender를 사용할 수 있습니다.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="a960a-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="a960a-114">끝점용 Defender에서 고급 헌팅 워크플로 전환을 시작하고 [Microsoft 365 Defender를 켜야 합니다.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="a960a-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="a960a-115">끝점 워크플로에 대한 기존 Defender에 영향을 주지 않고 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="a960a-116">저장된 쿼리는 그대로 유지되고 사용자 지정 검색 규칙은 계속 실행되고 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="a960a-117">그러나 Microsoft 365 Defender에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="a960a-118">Microsoft 365 Defender의 Schema 테이블만</span><span class="sxs-lookup"><span data-stu-id="a960a-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="a960a-119">[Microsoft 365 Defender 고급 헌팅](advanced-hunting-schema-tables.md) 계획은 다양한 Microsoft 365 보안 솔루션의 데이터를 포함하는 추가 테이블을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="a960a-120">다음 표는 Microsoft 365 Defender에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="a960a-121">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="a960a-121">Table name</span></span> | <span data-ttu-id="a960a-122">설명</span><span class="sxs-lookup"><span data-stu-id="a960a-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="a960a-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a960a-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="a960a-124">경고와 연결된 파일, IP 주소, URL, 사용자 또는 장치</span><span class="sxs-lookup"><span data-stu-id="a960a-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="a960a-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a960a-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="a960a-126">심각도 정보 및 위협 범주를 포함하여 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender의 알림</span><span class="sxs-lookup"><span data-stu-id="a960a-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="a960a-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="a960a-128">클라우드 앱 및 서비스의 파일 관련 활동</span><span class="sxs-lookup"><span data-stu-id="a960a-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="a960a-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="a960a-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="a960a-130">전자 메일에 첨부된 파일에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a960a-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="a960a-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="a960a-132">Microsoft 365 전자 메일 이벤트(전자 메일 배달 및 차단 이벤트 포함)</span><span class="sxs-lookup"><span data-stu-id="a960a-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="a960a-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="a960a-134">Microsoft 365에서 받는 사람 사서함으로 전자 메일을 배달한 후의 배달 후 발생하는 보안 이벤트</span><span class="sxs-lookup"><span data-stu-id="a960a-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="a960a-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="a960a-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="a960a-136">전자 메일의 URL에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a960a-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="a960a-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="a960a-138">AD(Active Directory)를 실행하는 On-프레미스 도메인 컨트롤러와 관련된 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="a960a-139">이 표에는 도메인 컨트롤러의 ID 관련 이벤트 및 시스템 이벤트 범위가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="a960a-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="a960a-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="a960a-141">Azure Active Directory를 비롯한 다양한 원본의 계정 정보</span><span class="sxs-lookup"><span data-stu-id="a960a-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="a960a-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="a960a-143">Active Directory 및 Microsoft 온라인 서비스의 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="a960a-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="a960a-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="a960a-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="a960a-145">사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대한 쿼리</span><span class="sxs-lookup"><span data-stu-id="a960a-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="a960a-146">DeviceAlertEvents 맵 테이블</span><span class="sxs-lookup"><span data-stu-id="a960a-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="a960a-147">테이블과 `AlertInfo` `AlertEvidence` `DeviceAlertEvents` 테이블은 끝점용 Microsoft Defender의 테이블을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="a960a-148">이러한 두 테이블에는 장치 경고에 대한 데이터 외에도 ID, 앱 및 전자 메일에 대한 경고에 대한 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="a960a-149">다음 표를 사용하여 열이 열과 표의 열에 `DeviceAlertEvents` 매핑되는 방법을 `AlertInfo` 확인할 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="a960a-150">이 표에는 다음 표의 열 외에도 다양한 원본의 경고에 대한 보다 전체적인 그림을 제공하는 다른 여러 `AlertEvidence` 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="a960a-151">모든 AlertEvidence 열 보기</span><span class="sxs-lookup"><span data-stu-id="a960a-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="a960a-152">DeviceAlertEvents 열</span><span class="sxs-lookup"><span data-stu-id="a960a-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="a960a-153">Microsoft 365 Defender에서 동일한 데이터를 찾을 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="a960a-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="a960a-154">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="a960a-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="a960a-155">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="a960a-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="a960a-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="a960a-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="a960a-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a960a-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="a960a-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a960a-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="a960a-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a960a-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="a960a-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="a960a-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="a960a-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="a960a-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a960a-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="a960a-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a960a-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="a960a-166">이 열은 일반적으로 끝점용 Microsoft Defender에서 다른 테이블의 관련 레코드를 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="a960a-167">Microsoft 365 Defender에서 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="a960a-168">이 열은 일반적으로 다른 테이블의 추가 이벤트 정보에 대해 끝점용 Microsoft Defender에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="a960a-169">Microsoft 365 Defender에서 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="a960a-170">끝점 쿼리에 대한 기존 Microsoft Defender 조정</span><span class="sxs-lookup"><span data-stu-id="a960a-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="a960a-171">끝점용 Microsoft Defender 쿼리는 테이블을 참조하지 않는 한 있는 것으로 `DeviceAlertEvents` 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="a960a-172">Microsoft 365 Defender에서 이러한 쿼리를 사용 하 고 다음 변경 내용을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="a960a-173">`DeviceAlertEvents`.로 바꾸기 `AlertInfo`</span><span class="sxs-lookup"><span data-stu-id="a960a-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="a960a-174">해당 데이터를 얻기 위해 테이블과 `AlertInfo` `AlertEvidence` `AlertId` 테이블을 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="a960a-175">원래 쿼리</span><span class="sxs-lookup"><span data-stu-id="a960a-175">Original query</span></span>
<span data-ttu-id="a960a-176">다음 쿼리는 `DeviceAlertEvents` 끝점용 Microsoft Defender에서 다음을 __ 사용하여 다음과 같은 경고를powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="a960a-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="a960a-177">수정된 쿼리</span><span class="sxs-lookup"><span data-stu-id="a960a-177">Modified query</span></span>
<span data-ttu-id="a960a-178">다음 쿼리는 Microsoft 365 Defender에서 사용하기 위해 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="a960a-179">파일 이름을 직접 확인하지 않고 해당 테이블의 파일 이름을 조인하고 `DeviceAlertEvents` `AlertEvidence` 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a960a-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="a960a-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a960a-180">See also</span></span>
- [<span data-ttu-id="a960a-181">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="a960a-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a960a-182">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="a960a-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a960a-183">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="a960a-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a960a-184">끝점용 Microsoft Defender의 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="a960a-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)