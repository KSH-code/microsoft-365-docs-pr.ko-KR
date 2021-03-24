---
title: 고급 헌팅chema의 AADSpnSignInEventsBeta 테이블
description: Azure Active Directory 서비스 계정 및 관리되는 ID 로그인 이벤트 테이블과 관련된 정보에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, AlertInfo, 경고, 엔터티, 증거, 파일, IP 주소, 장치, 컴퓨터, 사용자, 계정, ID, AAD
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
ms.openlocfilehash: 64f3e1d51f94c4cd2578a1d512115aa717c3eaa8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071652"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="6d74e-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6d74e-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="6d74e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6d74e-105">**Applies to:**</span></span>

- <span data-ttu-id="6d74e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d74e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6d74e-107">이 표는 현재 베타 상태이며 AAD(Azure Active Directory) 서비스 사용자 및 관리되는 ID 로그인 이벤트를 검색할 수 있도록 단기적으로 `AADSpnSignInEventsBeta` 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="6d74e-108">결국 모든 로그인 Schema 정보를 테이블로 `IdentityLogonEvents` 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="6d74e-109">Azure 보안 센터의 통합된 끝점용 Microsoft Defender 솔루션을 통해 Microsoft 365 Defender에 액세스할 수 있지만 Office용 Microsoft Defender, ID용 Microsoft Defender 또는 Microsoft Cloud App Security에 대한 라이선스가 없는 고객은 이 스마마를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="6d74e-110">고급 헌팅 schema의 표에는 Azure Active Directory 서비스 사용자 및 관리되는 ID 로그인에 대한 `AADSpnSignInEventsBeta` 정보가 포함되어 있습니다. Azure Active Directory 로그인 활동 보고서 - 미리 보기에서 다양한 종류의 로그인에 대해 자세히 [알아보십시오.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="6d74e-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="6d74e-111">이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6d74e-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d74e-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="6d74e-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="6d74e-113">Column name</span></span>     | <span data-ttu-id="6d74e-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6d74e-114">Data type</span></span> | <span data-ttu-id="6d74e-115">설명</span><span class="sxs-lookup"><span data-stu-id="6d74e-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="6d74e-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6d74e-116">datetime</span></span>      | <span data-ttu-id="6d74e-117">레코드 생성 날짜 및 시간</span><span class="sxs-lookup"><span data-stu-id="6d74e-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="6d74e-118">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-118">string</span></span>        | <span data-ttu-id="6d74e-119">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6d74e-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="6d74e-120">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-120">string</span></span>        | <span data-ttu-id="6d74e-121">응용 프로그램의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6d74e-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="6d74e-122">부울</span><span class="sxs-lookup"><span data-stu-id="6d74e-122">boolean</span></span>       | <span data-ttu-id="6d74e-123">관리되는 ID에서 로그인을 시작한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="6d74e-124">int</span><span class="sxs-lookup"><span data-stu-id="6d74e-124">int</span></span>        | <span data-ttu-id="6d74e-125">로그인 오류가 발생하는 경우 오류 코드가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="6d74e-126">특정 오류 코드에 대한 설명을 찾으면 을 <https://aka.ms/AADsigninsErrorCodes> 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="6d74e-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="6d74e-127">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-127">string</span></span>        | <span data-ttu-id="6d74e-128">로그인 이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6d74e-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="6d74e-129">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-129">string</span></span>        | <span data-ttu-id="6d74e-130">로그인을 시작한 서비스 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="6d74e-131">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-131">string</span></span>        | <span data-ttu-id="6d74e-132">로그인을 시작한 서비스 계정의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="6d74e-133">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-133">string</span></span>        | <span data-ttu-id="6d74e-134">액세스한 리소스의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="6d74e-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="6d74e-135">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-135">string</span></span>        | <span data-ttu-id="6d74e-136">액세스한 리소스의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6d74e-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="6d74e-137">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-137">string</span></span>        | <span data-ttu-id="6d74e-138">액세스한 리소스의 테넌트의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6d74e-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="6d74e-139">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-139">string</span></span>        | <span data-ttu-id="6d74e-140">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="6d74e-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="6d74e-141">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-141">string</span></span>        | <span data-ttu-id="6d74e-142">클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드</span><span class="sxs-lookup"><span data-stu-id="6d74e-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="6d74e-143">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-143">string</span></span>        | <span data-ttu-id="6d74e-144">로그인이 발생한 위치(사용 가능한 경우)</span><span class="sxs-lookup"><span data-stu-id="6d74e-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="6d74e-145">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-145">string</span></span>        | <span data-ttu-id="6d74e-146">계정 사용자가 있는 구</span><span class="sxs-lookup"><span data-stu-id="6d74e-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="6d74e-147">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-147">string</span></span>        | <span data-ttu-id="6d74e-148">로그인 위치의 북-남 좌표</span><span class="sxs-lookup"><span data-stu-id="6d74e-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="6d74e-149">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-149">string</span></span>        | <span data-ttu-id="6d74e-150">로그인 위치의 동쪽에서 서 좌표까지</span><span class="sxs-lookup"><span data-stu-id="6d74e-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="6d74e-151">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-151">string</span></span>        | <span data-ttu-id="6d74e-152">요청의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6d74e-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="6d74e-153">문자열</span><span class="sxs-lookup"><span data-stu-id="6d74e-153">string</span></span> | <span data-ttu-id="6d74e-154">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="6d74e-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="6d74e-155">관련 문서</span><span class="sxs-lookup"><span data-stu-id="6d74e-155">Related articles</span></span>

-   [<span data-ttu-id="6d74e-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="6d74e-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="6d74e-157">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="6d74e-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="6d74e-158">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="6d74e-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="6d74e-159">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="6d74e-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)