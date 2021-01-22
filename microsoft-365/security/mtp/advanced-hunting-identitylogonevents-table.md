---
title: 고급 헌팅chema의 IdentityLogonEvents 테이블
description: 고급 헌팅 구조의 IdentityLogonEvents 표에서 Active Directory에서 기록하는 인증 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, ID
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
ms.technology: m365d
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929925"
---
# <a name="identitylogonevents"></a><span data-ttu-id="7a915-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="7a915-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7a915-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7a915-105">**Applies to:**</span></span>
- <span data-ttu-id="7a915-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a915-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7a915-107">고급 헌팅 계획의 표에는 ID를 위해 Microsoft Defender에서 캡처한 프레미스 Active Directory를 통한 인증 활동 및 Microsoft Cloud App Security에서 캡처한 Microsoft 온라인 서비스와 관련된 인증 활동에 대한 정보가 포함되어 `IdentityLogonEvents` 있습니다. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7a915-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7a915-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="7a915-109">테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="7a915-110">이 표에서는 Cloud App Security에서 추적하는 Azure AD(Active Directory) 로그온 활동, 특히 ActiveSync 및 기타 레거시 프로토콜을 사용하는 대화형 로그인 및 인증 활동에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="7a915-111">이 표에서 사용할 수 없는 비대화형 로그온은 Azure AD 감사 로그에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="7a915-112">Cloud App Security를 Microsoft 365에 연결하는 방법을 자세히 알아보시고</span><span class="sxs-lookup"><span data-stu-id="7a915-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="7a915-113">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a915-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7a915-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="7a915-114">Column name</span></span> | <span data-ttu-id="7a915-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7a915-115">Data type</span></span> | <span data-ttu-id="7a915-116">설명</span><span class="sxs-lookup"><span data-stu-id="7a915-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7a915-117">datetime</span><span class="sxs-lookup"><span data-stu-id="7a915-117">datetime</span></span> | <span data-ttu-id="7a915-118">이벤트가 기록된 날짜와 시간</span><span class="sxs-lookup"><span data-stu-id="7a915-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7a915-119">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-119">string</span></span> | <span data-ttu-id="7a915-120">이벤트를 트리거한 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="7a915-121">자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="7a915-122">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-122">string</span></span> | <span data-ttu-id="7a915-123">특히 로그온 세션의 유형:</span><span class="sxs-lookup"><span data-stu-id="7a915-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="7a915-124">- **대화형** - 사용자가 로컬 키보드 및 화면을 사용하여 컴퓨터와 물리적으로 상호 작용</span><span class="sxs-lookup"><span data-stu-id="7a915-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="7a915-125">- **RDP(원격 대화형)** 로그널 - 사용자가 원격 데스크톱, 터미널 서비스, 원격 지원 또는 기타 RDP 클라이언트를 사용하여 원격으로 컴퓨터와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="7a915-126">- **네트워크** - PsExec을 사용하여 컴퓨터 액세스 또는 컴퓨터의 공유 리소스(예: 프린터 및 공유 폴더)에 액세스할 때 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="7a915-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="7a915-127">- **일괄** 처리 - 예약된 작업으로 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="7a915-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="7a915-128">- **서비스** - 서비스 시작 시 서비스에서 시작된 세션</span><span class="sxs-lookup"><span data-stu-id="7a915-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="7a915-129">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-129">string</span></span> | <span data-ttu-id="7a915-130">기록된 작업을 수행한 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="7a915-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="7a915-131">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-131">string</span></span> | <span data-ttu-id="7a915-132">사용된 네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="7a915-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="7a915-133">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-133">string</span></span> | <span data-ttu-id="7a915-134">기록된 작업이 실패한 이유를 설명하는 정보</span><span class="sxs-lookup"><span data-stu-id="7a915-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="7a915-135">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-135">string</span></span> | <span data-ttu-id="7a915-136">계정의 사용자 이름</span><span class="sxs-lookup"><span data-stu-id="7a915-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7a915-137">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-137">string</span></span> | <span data-ttu-id="7a915-138">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="7a915-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="7a915-139">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-139">string</span></span> | <span data-ttu-id="7a915-140">계정의 UPN(사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="7a915-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7a915-141">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-141">string</span></span> | <span data-ttu-id="7a915-142">계정의 SID(보안 식별자)입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7a915-143">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-143">string</span></span> | <span data-ttu-id="7a915-144">Azure AD에서 계정의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="7a915-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7a915-145">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-145">string</span></span> | <span data-ttu-id="7a915-146">주소부에 표시된 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7a915-147">일반적으로 지정한 이름이나 이름, 중간 초기화 및 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="7a915-148">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-148">string</span></span> | <span data-ttu-id="7a915-149">장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="7a915-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="7a915-150">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-150">string</span></span> | <span data-ttu-id="7a915-151">디바이스 유형</span><span class="sxs-lookup"><span data-stu-id="7a915-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="7a915-152">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-152">string</span></span> | <span data-ttu-id="7a915-153">컴퓨터에서 실행 중인 운영 체제의 플랫폼</span><span class="sxs-lookup"><span data-stu-id="7a915-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7a915-154">이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7a915-155">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-155">string</span></span> | <span data-ttu-id="7a915-156">끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7a915-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="7a915-157">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-157">string</span></span> | <span data-ttu-id="7a915-158">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-158">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="7a915-159">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-159">string</span></span> | <span data-ttu-id="7a915-160">기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="7a915-160">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="7a915-161">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-161">string</span></span> | <span data-ttu-id="7a915-162">기록된 작업이 적용된 장치의 FQDN(FQDN)</span><span class="sxs-lookup"><span data-stu-id="7a915-162">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="7a915-163">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-163">string</span></span> | <span data-ttu-id="7a915-164">기록된 작업이 적용된 계정의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-164">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="7a915-165">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-165">string</span></span> | <span data-ttu-id="7a915-166">이벤트와 관련된 도시, 국가 또는 기타 지리적 위치</span><span class="sxs-lookup"><span data-stu-id="7a915-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="7a915-167">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-167">string</span></span> | <span data-ttu-id="7a915-168">끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자)</span><span class="sxs-lookup"><span data-stu-id="7a915-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="7a915-169">long</span><span class="sxs-lookup"><span data-stu-id="7a915-169">long</span></span> | <span data-ttu-id="7a915-170">이벤트의 고유 식별자</span><span class="sxs-lookup"><span data-stu-id="7a915-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="7a915-171">문자열</span><span class="sxs-lookup"><span data-stu-id="7a915-171">string</span></span> | <span data-ttu-id="7a915-172">엔터티 또는 이벤트에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="7a915-172">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7a915-173">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7a915-173">Related topics</span></span>
- [<span data-ttu-id="7a915-174">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="7a915-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7a915-175">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="7a915-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7a915-176">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="7a915-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7a915-177">장치, 전자 메일, 앱 및 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7a915-177">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7a915-178">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="7a915-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7a915-179">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="7a915-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
