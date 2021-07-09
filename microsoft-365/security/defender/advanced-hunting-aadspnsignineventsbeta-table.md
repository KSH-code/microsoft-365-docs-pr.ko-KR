---
title: 고급 헌팅chema의 AADSpnSignInEventsBeta 테이블
description: 고급 헌팅 Azure Active Directory 서비스 사용자 및 관리되는 ID 로그인 이벤트 테이블과 관련된 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, AlertInfo, 경고, 엔터티, 증거, 파일, IP 주소, 장치, 컴퓨터, 사용자, 계정, ID, AAD
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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347910"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="8f730-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="8f730-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="8f730-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8f730-105">**Applies to:**</span></span>

- <span data-ttu-id="8f730-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f730-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8f730-107">이 표는 현재 베타 버전이며 단기적으로 제공되어 AAD(Azure Active Directory) 서비스 사용자 및 관리되는 ID 로그인 이벤트를 확인할 `AADSpnSignInEventsBeta` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="8f730-108">결국 모든 로그인 Schema 정보를 테이블로 `IdentityLogonEvents` 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="8f730-109">고급 헌팅 schema의 표에는 서비스 사용자 및 Azure Active Directory 로그인에 대한 정보가 `AADSpnSignInEventsBeta` 포함되어 있습니다. 로그인 활동 보고서 - 미리 보기에서 다양한 종류의 [로그인에 대해 Azure Active Directory 수 있습니다.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="8f730-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="8f730-110">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8f730-111">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f730-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="8f730-112">열 이름</span><span class="sxs-lookup"><span data-stu-id="8f730-112">Column name</span></span> | <span data-ttu-id="8f730-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8f730-113">Data type</span></span> | <span data-ttu-id="8f730-114">설명</span><span class="sxs-lookup"><span data-stu-id="8f730-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="8f730-115">datetime</span><span class="sxs-lookup"><span data-stu-id="8f730-115">datetime</span></span> | <span data-ttu-id="8f730-116">레코드 생성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="8f730-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="8f730-117">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-117">string</span></span> | <span data-ttu-id="8f730-118">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8f730-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="8f730-119">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-119">string</span></span> | <span data-ttu-id="8f730-120">응용 프로그램의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8f730-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="8f730-121">부울</span><span class="sxs-lookup"><span data-stu-id="8f730-121">boolean</span></span>       | <span data-ttu-id="8f730-122">관리되는 ID에서 로그인을 시작한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="8f730-123">int</span><span class="sxs-lookup"><span data-stu-id="8f730-123">int</span></span> | <span data-ttu-id="8f730-124">로그인 오류가 발생하는 경우 오류 코드가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="8f730-125">특정 오류 코드에 대한 설명을 찾으면 을 <https://aka.ms/AADsigninsErrorCodes> 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="8f730-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="8f730-126">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-126">string</span></span>        | <span data-ttu-id="8f730-127">로그인 이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8f730-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="8f730-128">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-128">string</span></span>        | <span data-ttu-id="8f730-129">로그인을 시작한 서비스 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="8f730-130">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-130">string</span></span>        | <span data-ttu-id="8f730-131">로그인을 시작한 서비스 계정의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="8f730-132">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-132">string</span></span>        | <span data-ttu-id="8f730-133">액세스한 리소스의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="8f730-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="8f730-134">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-134">string</span></span>        | <span data-ttu-id="8f730-135">액세스한 리소스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8f730-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="8f730-136">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-136">string</span></span>        | <span data-ttu-id="8f730-137">액세스한 리소스의 테넌트의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f730-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="8f730-138">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-138">string</span></span>        | <span data-ttu-id="8f730-139">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8f730-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="8f730-140">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-140">string</span></span>        | <span data-ttu-id="8f730-141">클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드</span><span class="sxs-lookup"><span data-stu-id="8f730-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="8f730-142">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-142">string</span></span>        | <span data-ttu-id="8f730-143">로그인이 발생한 위치(사용 가능한 경우)</span><span class="sxs-lookup"><span data-stu-id="8f730-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="8f730-144">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-144">string</span></span>        | <span data-ttu-id="8f730-145">계정 사용자가 있는 구</span><span class="sxs-lookup"><span data-stu-id="8f730-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="8f730-146">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-146">string</span></span>        | <span data-ttu-id="8f730-147">로그인 위치의 북-남 좌표</span><span class="sxs-lookup"><span data-stu-id="8f730-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="8f730-148">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-148">string</span></span>        | <span data-ttu-id="8f730-149">로그인 위치의 동쪽에서 서 좌표까지</span><span class="sxs-lookup"><span data-stu-id="8f730-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="8f730-150">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-150">string</span></span>        | <span data-ttu-id="8f730-151">요청의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8f730-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="8f730-152">문자열</span><span class="sxs-lookup"><span data-stu-id="8f730-152">string</span></span> | <span data-ttu-id="8f730-153">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="8f730-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="8f730-154">관련 문서</span><span class="sxs-lookup"><span data-stu-id="8f730-154">Related articles</span></span>

-   [<span data-ttu-id="8f730-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="8f730-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="8f730-156">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="8f730-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="8f730-157">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="8f730-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="8f730-158">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="8f730-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
