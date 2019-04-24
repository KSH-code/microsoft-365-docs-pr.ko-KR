---
title: Microsoft Managed Desktop 응용 프로그램 요구 사항
description: ''
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278338"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="a0f3e-103">Microsoft Managed Desktop 응용 프로그램 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0f3e-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="a0f3e-104">Microsoft Managed Desktop 장치에 배포 하려는 기간 업무 (lob) 응용 프로그램은이 항목의 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="a0f3e-105">응용 프로그램 조건</span><span class="sxs-lookup"><span data-stu-id="a0f3e-105">Application condition</span></span>

<span data-ttu-id="a0f3e-106">응용 프로그램이 Microsoft Managed Desktop 환경에 악영향을 미치지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="a0f3e-107">다음은 Microsoft에서 배포 하기 위해 응용 프로그램에서 충족 해야 하는 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="a0f3e-108">지정 된 응용 프로그램 또는 드라이버의 경우 Microsoft는 여기에 제공 된 모든 요구 사항을 waive 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="a0f3e-109">microsoft는 microsoft 관리 데스크톱 장치의 성능 및 안정성에 부정적인 영향을 주는 응용 프로그램 또는 드라이버를 제거 하는 것을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="a0f3e-110">Microsoft 기술을 사용 하 여 배포 가능</span><span class="sxs-lookup"><span data-stu-id="a0f3e-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="a0f3e-111">microsoft Managed Desktop은 Intune, microsoft store 및 비즈니스용 microsoft store를 사용 하 여 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="a0f3e-112">따라서 응용 프로그램은 해당 서비스의 최신 버전을 통해 배포할 수 있는 방식으로 패키지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="a0f3e-113">금지 되는 앱 클래스</span><span class="sxs-lookup"><span data-stu-id="a0f3e-113">Prohibited app classes</span></span>

<span data-ttu-id="a0f3e-114">특정 응용 프로그램 유형은 Microsoft Managed Desktop 장치에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="a0f3e-115">타사 바이러스 백신, 보안 또는 감사 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a0f3e-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="a0f3e-116">타사 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="a0f3e-116">3rd party web browsers</span></span>
- <span data-ttu-id="a0f3e-117">Office 365 Pro Plus 이전 버전의 Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="a0f3e-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="a0f3e-118">다른 타사 소프트웨어를 설치 하거나 번들 하는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a0f3e-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="a0f3e-119">제한 된 앱 동작</span><span class="sxs-lookup"><span data-stu-id="a0f3e-119">Restricted app behaviors</span></span>

<span data-ttu-id="a0f3e-120">특정 응용 프로그램 동작은 사용자 환경에 부정적인 영향을 주거나 Microsoft 관리 되는 데스크톱 장치에 보안 위험을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0f3e-121">응용 프로그램에는 다음과 같은 동작이 나 특성이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="a0f3e-122">사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="a0f3e-122">User Experience:</span></span>
- <span data-ttu-id="a0f3e-123">백그라운드 서비스 설치 또는 오랫동안 실행 되는 백그라운드 프로세스 생성</span><span class="sxs-lookup"><span data-stu-id="a0f3e-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="a0f3e-124">Windows 시작 경로에 자신 추가</span><span class="sxs-lookup"><span data-stu-id="a0f3e-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="a0f3e-125">보안:</span><span class="sxs-lookup"><span data-stu-id="a0f3e-125">Security:</span></span>
- <span data-ttu-id="a0f3e-126">문서화 되지 않은 windows 또는 office api를 호출 하거나 내부 Windows 또는 office 데이터 구조에 대 한 종속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="a0f3e-127">앱 저장소 역할을 하거나 기본 제공 확장 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="a0f3e-128">최종 사용자의 권한 상승</span><span class="sxs-lookup"><span data-stu-id="a0f3e-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="a0f3e-129">알려진 보안 취약성</span><span class="sxs-lookup"><span data-stu-id="a0f3e-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="a0f3e-130">신뢰할 수 있는 루트에 롤업 하지 않는 인증서를 사용 하 여 서명 됨</span><span class="sxs-lookup"><span data-stu-id="a0f3e-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="a0f3e-131">최종 사용자 데이터에 대 한 액세스 암호화 또는 제한</span><span class="sxs-lookup"><span data-stu-id="a0f3e-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="a0f3e-132">런타임에 운영 체제 코드 수정</span><span class="sxs-lookup"><span data-stu-id="a0f3e-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="a0f3e-133">드라이버 배포</span><span class="sxs-lookup"><span data-stu-id="a0f3e-133">Driver deployment</span></span>

<span data-ttu-id="a0f3e-134">windows Update에서 드라이버를 사용할 수 없거나 windows 하드웨어 품질 실습 (WHQL)에서 별도로 서명 하지 않은 경우 microsoft에서 microsoft Managed Desktop 장치에 드라이버를 배포 하기 전에 드라이버를 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0f3e-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
