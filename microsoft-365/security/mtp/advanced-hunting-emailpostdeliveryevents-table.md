---
title: 고급 구하기 스키마의 EmailPostDeliveryEvents 테이블
description: 고급 구하기 스키마의 EmailPostDeliveryEvents 테이블에서 Microsoft 365 전자 메일에 대해 수행 된 배달 후 작업에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 요소 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, 첨부 파일 이름, 맬웨어 결과, 피싱 결과, 첨부 파일 수, 링크 수, url 개수
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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198016"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="ea45f-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="ea45f-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ea45f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="ea45f-105">**Applies to:**</span></span>
- <span data-ttu-id="ea45f-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="ea45f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ea45f-107">`EmailPostDeliveryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft 365에서 처리 되는 전자 메일 메시지에 대해 수행 된 배달 후 작업에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="ea45f-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="ea45f-109">테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea45f-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="ea45f-110">개별 전자 메일 메시지에 대 한 자세한 내용을 보려면 [`EmailEvents`](advanced-hunting-emailevents-table.md) , 및 테이블을 사용할 수도 있습니다 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="ea45f-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="ea45f-111">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea45f-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ea45f-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="ea45f-112">Column name</span></span> | <span data-ttu-id="ea45f-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ea45f-113">Data type</span></span> | <span data-ttu-id="ea45f-114">설명</span><span class="sxs-lookup"><span data-stu-id="ea45f-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ea45f-115">datetime</span><span class="sxs-lookup"><span data-stu-id="ea45f-115">datetime</span></span> | <span data-ttu-id="ea45f-116">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="ea45f-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="ea45f-117">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-117">string</span></span> | <span data-ttu-id="ea45f-118">이벤트에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ea45f-119">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-119">string</span></span> | <span data-ttu-id="ea45f-120">Microsoft 365에서 생성 된 전자 메일에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="ea45f-121">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-121">string</span></span> | <span data-ttu-id="ea45f-122">보내는 전자 메일 시스템에서 설정한 전자 메일의 공개 식별자</span><span class="sxs-lookup"><span data-stu-id="ea45f-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="ea45f-123">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-123">string</span></span> | <span data-ttu-id="ea45f-124">엔터티에 대해 수행 된 작업</span><span class="sxs-lookup"><span data-stu-id="ea45f-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="ea45f-125">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-125">string</span></span> | <span data-ttu-id="ea45f-126">이벤트를 트리거한 작업의 유형: 수동 재구성, 피싱 ZAP, 맬웨어 ZAP</span><span class="sxs-lookup"><span data-stu-id="ea45f-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="ea45f-127">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-127">string</span></span> | <span data-ttu-id="ea45f-128">작업이 관리자에 의해 트리거된 지 (수동으로 또는 보류 중인 자동 작업의 승인를 통해) 또는 ZAP 또는 동적 배달과 같은 특수 메커니즘을 통해 트리거 되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="ea45f-129">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-129">string</span></span> | <span data-ttu-id="ea45f-130">작업 결과</span><span class="sxs-lookup"><span data-stu-id="ea45f-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="ea45f-131">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-131">string</span></span> | <span data-ttu-id="ea45f-132">받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="ea45f-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="ea45f-133">문자열</span><span class="sxs-lookup"><span data-stu-id="ea45f-133">string</span></span> | <span data-ttu-id="ea45f-134">전자 메일이 전송된 위치: 받은 편지함/폴더, 온-프레미스/외부, 정크, 격리, 실패, 중단, 삭제된 항목</span><span class="sxs-lookup"><span data-stu-id="ea45f-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="ea45f-135">지원 되는 이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="ea45f-135">Supported event types</span></span>
<span data-ttu-id="ea45f-136">이 테이블은 다음과 같은 값을 갖는 이벤트를 캡처합니다 `ActionType` .</span><span class="sxs-lookup"><span data-stu-id="ea45f-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="ea45f-137">**수동 재구성** – 관리자가 사용자 사서함으로 배달 된 후 수동으로 전자 메일 메시지에 대 한 작업을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="ea45f-138">여기에는 [위협 탐색기](../office-365-security/threat-explorer.md) 를 통해 수동으로 수행 하거나 [자동화 된 조사 및 응답 (AIR) 작업](mtp-autoir-actions.md)을 승인 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="ea45f-139">**피싱 zap** -배달 후 피싱 전자 메일에 대해 [제로 시간 자동 삭제 (ZAP)](../office-365-security/zero-hour-auto-purge.md) 가 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="ea45f-140">**맬웨어 ZAP** -배달 후 맬웨어가 포함 된 전자 메일 메시지에 대해 제로 시간 자동 삭제 (ZAP)가 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea45f-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ea45f-141">Related topics</span></span>
- [<span data-ttu-id="ea45f-142">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="ea45f-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ea45f-143">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="ea45f-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ea45f-144">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="ea45f-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ea45f-145">기기, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ea45f-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ea45f-146">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="ea45f-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ea45f-147">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="ea45f-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
