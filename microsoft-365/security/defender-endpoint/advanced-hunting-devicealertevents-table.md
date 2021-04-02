---
title: 고급 헌팅Chema의 DeviceAlertEvents 테이블
description: 고급 헌팅 스위마의 DeviceAlertEvents 테이블에서 경고 생성 이벤트에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, DeviceAlertEvents, 경고, 심각도, 범주
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499166"
---
# <a name="devicealertevents"></a><span data-ttu-id="9d1fa-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9d1fa-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d1fa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="9d1fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d1fa-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9d1fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="9d1fa-107">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="9d1fa-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9d1fa-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="9d1fa-109">고급 `DeviceAlertEvents` 헌팅 [Schema의](advanced-hunting-overview.md) 표에는 Microsoft Defender 보안 센터의 경고에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="9d1fa-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9d1fa-111">고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="9d1fa-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="9d1fa-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="9d1fa-112">Column name</span></span> | <span data-ttu-id="9d1fa-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9d1fa-113">Data type</span></span> | <span data-ttu-id="9d1fa-114">설명</span><span class="sxs-lookup"><span data-stu-id="9d1fa-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="9d1fa-115">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-115">string</span></span> | <span data-ttu-id="9d1fa-116">경고의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="9d1fa-117">datetime</span><span class="sxs-lookup"><span data-stu-id="9d1fa-117">datetime</span></span> | <span data-ttu-id="9d1fa-118">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="9d1fa-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9d1fa-119">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-119">string</span></span> | <span data-ttu-id="9d1fa-120">서비스에서 디바이스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="9d1fa-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9d1fa-121">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-121">string</span></span> | <span data-ttu-id="9d1fa-122">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="9d1fa-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="9d1fa-123">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-123">string</span></span> | <span data-ttu-id="9d1fa-124">경고로 식별되는 위협 표시기 또는 위반 활동의 잠재적인 영향(높음, 중간 또는 낮음)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="9d1fa-125">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-125">string</span></span> | <span data-ttu-id="9d1fa-126">경고로 식별되는 위협 표시기 또는 위반 활동 유형</span><span class="sxs-lookup"><span data-stu-id="9d1fa-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="9d1fa-127">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-127">string</span></span> | <span data-ttu-id="9d1fa-128">경고의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="9d1fa-129">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-129">string</span></span> | <span data-ttu-id="9d1fa-130">기록된 조치가 적용된 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="9d1fa-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9d1fa-131">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-131">string</span></span> | <span data-ttu-id="9d1fa-132">기록된 조치가 적용된 파일의 SHA-1</span><span class="sxs-lookup"><span data-stu-id="9d1fa-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="9d1fa-133">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-133">string</span></span> | <span data-ttu-id="9d1fa-134">연결된 URL 또는 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="9d1fa-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="9d1fa-135">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-135">string</span></span> | <span data-ttu-id="9d1fa-136">연결된 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9d1fa-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="9d1fa-137">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-137">string</span></span> | <span data-ttu-id="9d1fa-138">MITRE ATT&트리거한 활동과 관련된 CK 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="9d1fa-139">long</span><span class="sxs-lookup"><span data-stu-id="9d1fa-139">long</span></span> | <span data-ttu-id="9d1fa-140">반복 카운터를 기반으로 하는 이벤트 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9d1fa-141">고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1fa-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="9d1fa-142">문자열</span><span class="sxs-lookup"><span data-stu-id="9d1fa-142">string</span></span> | <span data-ttu-id="9d1fa-143">이벤트에 대한 세부 정보를 포함하는 표</span><span class="sxs-lookup"><span data-stu-id="9d1fa-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9d1fa-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9d1fa-144">Related topics</span></span>
- [<span data-ttu-id="9d1fa-145">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="9d1fa-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9d1fa-146">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="9d1fa-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9d1fa-147">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="9d1fa-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
