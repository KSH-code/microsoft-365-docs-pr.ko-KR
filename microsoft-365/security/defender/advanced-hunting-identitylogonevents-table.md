---
title: 아이덴티티로곤이벤트 고급 사냥 스키마의 테이블
description: 아이덴티티로곤에서 Active Directory가 기록한 인증 이벤트에 대해 알아보기 고급 사냥 스키마의 이벤트 테이블
keywords: 고급 사냥, 위협 사냥, 사이버 위협 사냥, Microsoft 365 수비수, 마이크로 소프트 365, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, 테이블, 열, 데이터 유형, 설명, IDLogonEvents, Azure AD, 활성 디렉토리, 정체성에 대한 마이크로 소프트 디펜더, ID
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572756"
---
# <a name="identitylogonevents"></a><span data-ttu-id="b738f-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="b738f-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b738f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b738f-105">**Applies to:**</span></span>
- <span data-ttu-id="b738f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b738f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b738f-107">`IdentityLogonEvents` [고급 사냥](advanced-hunting-overview.md) 스키마의 테이블에는 microsoft Defender가 캡처한 온-프레미스 액티브 디렉토리를 통해 이루어진 인증 활동에 대한 정보와 Microsoft Cloud App Security 캡처한 Microsoft 온라인 서비스와 관련된 인증 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="b738f-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="b738f-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 기본 제공 스키마 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference  available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="b738f-110">이 표에서는 Cloud App Security 추적한 Azure Active Directory(Azure AD) 로그온 활동, 특히 ActiveSync 및 기타 레거시 프로토콜을 사용하여 대화형 로그인 및 인증 활동을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-110">This table covers Azure Active Directory (Azure AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="b738f-111">이 테이블에서 사용할 수 없는 비대화형 로그온은 Azure AD 감사 로그에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="b738f-112">Cloud App Security 연결에 대해 자세히 알아보세요 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b738f-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="b738f-113">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b738f-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b738f-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="b738f-114">Column name</span></span> | <span data-ttu-id="b738f-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b738f-115">Data type</span></span> | <span data-ttu-id="b738f-116">설명</span><span class="sxs-lookup"><span data-stu-id="b738f-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b738f-117">datetime</span><span class="sxs-lookup"><span data-stu-id="b738f-117">datetime</span></span> | <span data-ttu-id="b738f-118">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="b738f-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b738f-119">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-119">string</span></span> | <span data-ttu-id="b738f-120">이벤트를 트리거한 활동 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="b738f-121">자세한 내용은 [포털 내 스키마 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b738f-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="b738f-122">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-122">string</span></span> | <span data-ttu-id="b738f-123">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b738f-123">Application that performed the recorded action</span></span> |
| `LogonType` | <span data-ttu-id="b738f-124">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-124">string</span></span> | <span data-ttu-id="b738f-125">특히 로그온 세션 유형:</span><span class="sxs-lookup"><span data-stu-id="b738f-125">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="b738f-126">- **대화형** - 사용자는 로컬 키보드 및 화면을 사용하여 컴퓨터와 물리적으로 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-126">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="b738f-127">- **원격 대화형(RDP) 로그온** - 사용자가 원격 데스크톱, 터미널 서비스, 원격 지원 또는 기타 RDP 클라이언트를 사용하여 원격으로 기계와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-127">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="b738f-128">- **네트워크** - PsExec을 사용하여 컴퓨터에 액세스하거나 프린터 및 공유 폴더와 같은 컴퓨터에서 공유 리소스에 액세스할 때 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="b738f-128">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="b738f-129">- **일괄 처리** - 예약된 작업으로 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="b738f-129">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="b738f-130">- **서비스** - 서비스 시작 시 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="b738f-130">- **Service** - Session initiated by services as they start</span></span> |
| `Protocol` | <span data-ttu-id="b738f-131">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-131">string</span></span> | <span data-ttu-id="b738f-132">사용되는 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="b738f-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="b738f-133">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-133">string</span></span> | <span data-ttu-id="b738f-134">기록된 작업이 실패한 이유를 설명하는 정보</span><span class="sxs-lookup"><span data-stu-id="b738f-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="b738f-135">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-135">string</span></span> | <span data-ttu-id="b738f-136">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="b738f-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b738f-137">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-137">string</span></span> | <span data-ttu-id="b738f-138">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="b738f-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b738f-139">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-139">string</span></span> | <span data-ttu-id="b738f-140">계정의 사용자 주체 이름(UPN)</span><span class="sxs-lookup"><span data-stu-id="b738f-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b738f-141">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-141">string</span></span> | <span data-ttu-id="b738f-142">계정의 보안 식별자(SID)</span><span class="sxs-lookup"><span data-stu-id="b738f-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b738f-143">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-143">string</span></span> | <span data-ttu-id="b738f-144">Azure AD의 계정에 대한 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="b738f-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b738f-145">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-145">string</span></span> | <span data-ttu-id="b738f-146">주소록에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b738f-147">일반적으로 지정된 이름 또는 이름, 중간 개시 및 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b738f-148">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-148">string</span></span> | <span data-ttu-id="b738f-149">장치의 완전 인증 된 도메인 이름 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b738f-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="b738f-150">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-150">string</span></span> | <span data-ttu-id="b738f-151">장치 유형</span><span class="sxs-lookup"><span data-stu-id="b738f-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="b738f-152">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-152">string</span></span> | <span data-ttu-id="b738f-153">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="b738f-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b738f-154">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="b738f-155">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-155">string</span></span> | <span data-ttu-id="b738f-156">끝점에 할당되고 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b738f-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="b738f-157">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-157">string</span></span> | <span data-ttu-id="b738f-158">통신 중에 사용되는 TCP 포트</span><span class="sxs-lookup"><span data-stu-id="b738f-158">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="b738f-159">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-159">string</span></span> | <span data-ttu-id="b738f-160">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름</span><span class="sxs-lookup"><span data-stu-id="b738f-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="b738f-161">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-161">string</span></span> | <span data-ttu-id="b738f-162">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b738f-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="b738f-163">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-163">string</span></span> | <span data-ttu-id="b738f-164">관련 네트워크 통신의 대상 포트</span><span class="sxs-lookup"><span data-stu-id="b738f-164">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="b738f-165">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-165">string</span></span> | <span data-ttu-id="b738f-166">기록된 작업이 적용된 장치의 완전 인증 도메인 이름(FQDN)은</span><span class="sxs-lookup"><span data-stu-id="b738f-166">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="b738f-167">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-167">string</span></span> | <span data-ttu-id="b738f-168">기록된 작업이 적용된 계정의 표시 이름</span><span class="sxs-lookup"><span data-stu-id="b738f-168">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="b738f-169">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-169">string</span></span> | <span data-ttu-id="b738f-170">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="b738f-170">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="b738f-171">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-171">string</span></span> | <span data-ttu-id="b738f-172">끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="b738f-172">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="b738f-173">long</span><span class="sxs-lookup"><span data-stu-id="b738f-173">long</span></span> | <span data-ttu-id="b738f-174">이벤트에 대한 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="b738f-174">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="b738f-175">문자열</span><span class="sxs-lookup"><span data-stu-id="b738f-175">string</span></span> | <span data-ttu-id="b738f-176">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="b738f-176">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b738f-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b738f-177">Related topics</span></span>
- [<span data-ttu-id="b738f-178">지능형 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="b738f-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b738f-179">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="b738f-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b738f-180">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="b738f-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b738f-181">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b738f-181">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b738f-182">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="b738f-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b738f-183">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="b738f-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)