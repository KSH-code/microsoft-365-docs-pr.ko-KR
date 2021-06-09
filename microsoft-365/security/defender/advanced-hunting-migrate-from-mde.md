---
title: 끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션
description: Microsoft Defender에서 끝점 쿼리를 사용할 수 있도록 끝점에 맞게 Microsoft Defender를 조정하는 Microsoft 365 방법
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 끝점용 Microsoft Defender, 검색, 쿼리, 원격 분석, 사용자 지정 검색, 스위마, kusto, 매핑
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470691"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="a3046-104">끝점용 Microsoft Defender에서 고급 헌팅 쿼리 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a3046-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a3046-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a3046-105">**Applies to:**</span></span>
- <span data-ttu-id="a3046-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3046-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a3046-107">끝점용 Microsoft Defender에서 고급 헌팅 워크플로를 이동하여 더 광범위한 데이터 집합을 사용하여 위협을 사전 예방적으로 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="a3046-108">Microsoft 365 Defender에서 다음을 비롯한 다른 Microsoft 365 보안 솔루션의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="a3046-109">끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3046-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a3046-110">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3046-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="a3046-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a3046-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="a3046-112">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a3046-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="a3046-113">끝점용 Microsoft Defender 고객은 추가 라이선스 없이 Microsoft 365 [Defender를 사용할 수 있습니다.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="a3046-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="a3046-114">끝점용 Defender에서 고급 헌팅 워크플로 전환을 시작하고 [Defender를 Microsoft 365 을 하세요.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="a3046-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="a3046-115">끝점 워크플로에 대한 기존 Defender에 영향을 주지 않고 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="a3046-116">저장된 쿼리는 그대로 유지되고 사용자 지정 검색 규칙은 계속 실행되고 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="a3046-117">그러나 이러한 설정은 Defender에서 Microsoft 365 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="a3046-118">Defender 전용의 Microsoft 365 테이블</span><span class="sxs-lookup"><span data-stu-id="a3046-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="a3046-119">Microsoft 365 [Defender 고급 헌팅](advanced-hunting-schema-tables.md) 계획은 다양한 보안 솔루션의 데이터를 포함하는 추가 Microsoft 365 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="a3046-120">다음 표는 Defender에서만 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="a3046-121">테이블 이름</span><span class="sxs-lookup"><span data-stu-id="a3046-121">Table name</span></span> | <span data-ttu-id="a3046-122">설명</span><span class="sxs-lookup"><span data-stu-id="a3046-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="a3046-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="a3046-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="a3046-124">경고와 연결된 파일, IP 주소, URL, 사용자 또는 장치</span><span class="sxs-lookup"><span data-stu-id="a3046-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="a3046-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a3046-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="a3046-126">심각도 정보 및 위협 범주를 포함하여 Microsoft Defender for endpoint, Office 365, Microsoft Cloud App Security 및 ID에 대한 Microsoft Defender의 경고</span><span class="sxs-lookup"><span data-stu-id="a3046-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="a3046-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="a3046-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="a3046-128">전자 메일에 첨부된 파일에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a3046-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="a3046-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a3046-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="a3046-130">Microsoft 365 및 차단 이벤트를 비롯한 전자 메일 이벤트 확인</span><span class="sxs-lookup"><span data-stu-id="a3046-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="a3046-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="a3046-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="a3046-132">배달 후 발생하는 보안 Microsoft 365 받는 사람 사서함에 전자 메일을 배달한 후</span><span class="sxs-lookup"><span data-stu-id="a3046-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="a3046-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="a3046-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="a3046-134">전자 메일의 URL에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a3046-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="a3046-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="a3046-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="a3046-136">AD(Active Directory)를 실행하는 사내 도메인 컨트롤러와 관련된 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="a3046-137">이 표에는 도메인 컨트롤러의 ID 관련 이벤트 및 시스템 이벤트 범위가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="a3046-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="a3046-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="a3046-139">계정 정보를 비롯한 다양한 원본의 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a3046-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="a3046-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="a3046-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="a3046-141">Active Directory 및 Microsoft 온라인 서비스의 인증 이벤트</span><span class="sxs-lookup"><span data-stu-id="a3046-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="a3046-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="a3046-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="a3046-143">사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대한 쿼리</span><span class="sxs-lookup"><span data-stu-id="a3046-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="a3046-144">Microsoft 365 Defender에서만 사용할 수 있는 쿼리 및 사용자 지정 검색은 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="a3046-145">DeviceAlertEvents 테이블 매핑</span><span class="sxs-lookup"><span data-stu-id="a3046-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="a3046-146">및 `AlertInfo` `AlertEvidence` 테이블은 `DeviceAlertEvents` Microsoft Defender for Endpoint schema의 테이블을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="a3046-147">이러한 두 테이블에는 장치 경고에 대한 데이터 외에도 ID, 앱 및 전자 메일에 대한 알림에 대한 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="a3046-148">다음 표를 사용하여 열이 및 테이블의 열에 매핑되는 `DeviceAlertEvents` 방법을 `AlertInfo` 확인할 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="a3046-149">표에는 다음 표의 열 외에도 다양한 원본의 경고에 대한 보다 전체적인 그림을 제공하는 다른 여러 열이 `AlertEvidence` 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="a3046-150">모든 AlertEvidence 열 보기</span><span class="sxs-lookup"><span data-stu-id="a3046-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="a3046-151">DeviceAlertEvents 열</span><span class="sxs-lookup"><span data-stu-id="a3046-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="a3046-152">Defender에서 동일한 데이터를 찾을 Microsoft 365 위치</span><span class="sxs-lookup"><span data-stu-id="a3046-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="a3046-153">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="a3046-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="a3046-154">`AlertInfo` 및  `AlertEvidence` 테이블</span><span class="sxs-lookup"><span data-stu-id="a3046-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="a3046-155">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="a3046-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="a3046-157">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a3046-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="a3046-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a3046-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="a3046-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a3046-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="a3046-160">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="a3046-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="a3046-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="a3046-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="a3046-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="a3046-164">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="a3046-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="a3046-165">이 열은 일반적으로 끝점용 Microsoft Defender에서 다른 테이블에서 관련 레코드를 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="a3046-166">Defender Microsoft 365 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="a3046-167">이 열은 일반적으로 다른 테이블의 추가 이벤트 정보에 대해 끝점용 Microsoft Defender에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="a3046-168">Defender Microsoft 365 테이블에서 직접 관련 데이터를 얻을 수 `AlertEvidence` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="a3046-169">끝점 쿼리에 대한 기존 Microsoft Defender 조정</span><span class="sxs-lookup"><span data-stu-id="a3046-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="a3046-170">Microsoft Defender for Endpoint 쿼리는 테이블을 참조하지 않는 한 있는 것으로 `DeviceAlertEvents` 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="a3046-171">Defender에서 이러한 쿼리를 Microsoft 365 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="a3046-172">으로 `DeviceAlertEvents` `AlertInfo` 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="a3046-173">에 `AlertInfo` 및 `AlertEvidence` 테이블을 조인하여 해당 데이터를 `AlertId` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="a3046-174">원래 쿼리</span><span class="sxs-lookup"><span data-stu-id="a3046-174">Original query</span></span>
<span data-ttu-id="a3046-175">다음 쿼리는 `DeviceAlertEvents` 끝점용 Microsoft Defender를 사용하여 다음과 __ 같은 경고를powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="a3046-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="a3046-176">수정된 쿼리</span><span class="sxs-lookup"><span data-stu-id="a3046-176">Modified query</span></span>
<span data-ttu-id="a3046-177">다음 쿼리는 Defender에서 사용할 수 Microsoft 365 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="a3046-178">에서 직접 파일 이름을 확인하지 않고 해당 테이블의 파일 이름을 조인하고 `DeviceAlertEvents` `AlertEvidence` 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="a3046-179">사용자 지정 검색 규칙 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a3046-179">Migrate custom detection rules</span></span>

<span data-ttu-id="a3046-180">Microsoft Defender for Endpoint 규칙이 Microsoft 365 Defender에서 편집된 경우 결과 쿼리가 장치 테이블만 조회하는 경우 이전과 같은 기능을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="a3046-181">예를 들어 장치 테이블만 쿼리하는 사용자 지정 검색 규칙에 의해 생성된 경고는 끝점용 Microsoft Defender에서 구성한 방법에 따라 SIEM으로 계속 전달되고 전자 메일 알림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a3046-182">Endpoint용 Defender의 기존 제거 규칙도 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="a3046-183">끝점용 Defender 규칙을 편집하여 id 및 전자 메일 테이블(Microsoft 365 Defender에서만 사용 가능)을 쿼리하면 규칙이 자동으로 Microsoft 365 Defender로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="a3046-184">마이그레이션된 규칙에 의해 생성된 경고:</span><span class="sxs-lookup"><span data-stu-id="a3046-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="a3046-185">끝점용 Defender 포털에 더 이상 표시되지 않습니다(Microsoft Defender 보안 센터)</span><span class="sxs-lookup"><span data-stu-id="a3046-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="a3046-186">SIEM으로 배달되는 것을 중지하거나 전자 메일 알림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="a3046-187">이 변경을 해결하기 위해 경고를 Microsoft 365 Defender를 통해 알림을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="a3046-188">Microsoft 365 [Api를](api-incident.md) 사용하여 고객 검색 경고 또는 관련 인시던트에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="a3046-189">끝점 제거 규칙에 대한 Microsoft Defender에 의해 억제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="a3046-190">특정 사용자, 장치 또는 사서함에 대한 알림이 생성되지 않도록 해당 쿼리를 수정하여 해당 엔터티를 명시적으로 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="a3046-191">이러한 방식으로 규칙을 편집하면 변경 내용이 적용되기 전에 확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="a3046-192">Microsoft 365 Defender 포털의 사용자 지정 검색 규칙에 의해 생성된 새 경고는 다음 정보를 제공하는 경고 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="a3046-193">경고 제목 및 설명</span><span class="sxs-lookup"><span data-stu-id="a3046-193">Alert title and description</span></span> 
- <span data-ttu-id="a3046-194">영향을 미치는 자산</span><span class="sxs-lookup"><span data-stu-id="a3046-194">Impacted assets</span></span>
- <span data-ttu-id="a3046-195">경고에 응답하여 수행된 작업</span><span class="sxs-lookup"><span data-stu-id="a3046-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="a3046-196">경고를 트리거한 쿼리 결과</span><span class="sxs-lookup"><span data-stu-id="a3046-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="a3046-197">사용자 지정 검색 규칙에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="a3046-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3046-198">![새 경고 페이지의 이미지](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="a3046-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="a3046-199">DeviceAlertEvents 없이 쿼리 쓰기</span><span class="sxs-lookup"><span data-stu-id="a3046-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="a3046-200">Microsoft 365 Defender schema에서 및 테이블은 다양한 원본의 경고와 함께 제공되는 다양한 정보 집합을 수용할 `AlertInfo` `AlertEvidence` 수 있도록 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="a3046-201">`DeviceAlertEvents`Microsoft Defender for Endpoint schema의 테이블에서 다운로드하는 데 사용한 경고 정보를 얻습니다. 테이블을 필터링한 다음 각 고유 ID를 테이블에 조인하여 자세한 이벤트 및 엔터티 정보를 `AlertInfo` `ServiceSource` `AlertEvidence` 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="a3046-202">아래 샘플 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3046-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="a3046-203">이 쿼리는 `DeviceAlertEvents` Microsoft Defender for Endpoint schema보다 많은 열을 산출합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="a3046-204">결과를 관리하기 쉽게 유지 관리하기 위해 관심 있는 열만 `project` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="a3046-205">조사에서 PowerShell 활동을 감지한 경우 관심 있는 프로젝트 열 아래의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="a3046-206">경고에 관련된 특정 엔터티를 필터링할 경우 엔터티 형식과 필터링할 값을 지정하여 필터링할 `EntityType` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="a3046-207">다음 예에서는 특정 IP 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a3046-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="a3046-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3046-208">See also</span></span>
- [<span data-ttu-id="a3046-209">Microsoft 365 Defender 켜기</span><span class="sxs-lookup"><span data-stu-id="a3046-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a3046-210">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="a3046-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a3046-211">스키마에 대한 이해</span><span class="sxs-lookup"><span data-stu-id="a3046-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a3046-212">끝점용 Microsoft Defender의 고급 헌팅</span><span class="sxs-lookup"><span data-stu-id="a3046-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)