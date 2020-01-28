---
title: Microsoft Managed Desktop 응용 프로그램 요구 사항
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: fd19764ab164373cee1de088ea402b3c46b61b81
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558575"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="5f60e-103">Microsoft Managed Desktop 응용 프로그램 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f60e-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="5f60e-104">Microsoft Managed Desktop 장치에 대 한 성능, 안정성 및 서비스 용이성을 보장 하기 위해 고객의 lob 앱은 최종 사용자 환경에 심각한 영향을 주지 않거나 보안 태세를 수정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="5f60e-105">따라서 Microsoft Managed Desktop 장치에 배포 하려는 기간 업무 (lob) 응용 프로그램은이 항목의 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="5f60e-106">응용 프로그램 조건</span><span class="sxs-lookup"><span data-stu-id="5f60e-106">Application condition</span></span>

<span data-ttu-id="5f60e-107">응용 프로그램이 Microsoft Managed Desktop 환경에 악영향을 미치지 않는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="5f60e-108">응용 프로그램에서 배포 하기 위해 충족 해야 하는 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="5f60e-109">지정 된 응용 프로그램 또는 드라이버의 경우 Microsoft는 여기에 제공 된 모든 요구 사항을 waive 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="5f60e-110">Microsoft는 Microsoft 관리 데스크톱 장치의 성능 및 안정성에 부정적인 영향을 주는 응용 프로그램 또는 드라이버를 제거 하는 것을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="5f60e-111">중앙 집중식으로 관리 되는 앱</span><span class="sxs-lookup"><span data-stu-id="5f60e-111">Centrally managed apps</span></span>

<span data-ttu-id="5f60e-112">Microsoft 관리 장치에 설치 된 모든 응용 프로그램 및 드라이버는 Microsoft Intune, Microsoft Store 또는 비즈니스용 Microsoft Store를 통해 배포 해야 합니다. 사용 가능한 경우 Windows Update 서비스를 통해 드라이버도 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="5f60e-113">금지 되는 앱 클래스</span><span class="sxs-lookup"><span data-stu-id="5f60e-113">Prohibited app classes</span></span>

<span data-ttu-id="5f60e-114">특정 응용 프로그램 유형은 Microsoft Managed Desktop 장치에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="5f60e-115">타사 바이러스 백신, 보안 또는 감사 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="5f60e-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="5f60e-116">Office 365 ProPlus 이전 버전의 Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="5f60e-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="5f60e-117">다른 타사 소프트웨어를 설치 하거나 번들 하는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5f60e-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="5f60e-118">제한 된 앱 동작</span><span class="sxs-lookup"><span data-stu-id="5f60e-118">Restricted app behaviors</span></span>

<span data-ttu-id="5f60e-119">특정 앱 동작은 사용자 환경에 부정적인 영향을 주거나 Microsoft 관리 되는 데스크톱 장치에 보안 위험을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="5f60e-120">다음 동작이 적용 되는 앱은 microsoft와 관련 없는 Microsoft Managed Desktop environment에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="5f60e-121">사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="5f60e-121">User Experience:</span></span>
- <span data-ttu-id="5f60e-122">백그라운드 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="5f60e-122">Install background services</span></span>
- <span data-ttu-id="5f60e-123">Windows 시작 경로에 자신 추가</span><span class="sxs-lookup"><span data-stu-id="5f60e-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="5f60e-124">드라이버에 종속 된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5f60e-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="5f60e-125">타사 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="5f60e-125">3rd party web browsers</span></span>

<span data-ttu-id="5f60e-126">보안:</span><span class="sxs-lookup"><span data-stu-id="5f60e-126">Security:</span></span>
- <span data-ttu-id="5f60e-127">최종 사용자의 권한 상승</span><span class="sxs-lookup"><span data-stu-id="5f60e-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="5f60e-128">앱 스토어 역할을 하거나 기본 제공 확장 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="5f60e-129">알려진 보안 취약성</span><span class="sxs-lookup"><span data-stu-id="5f60e-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="5f60e-130">최종 사용자 데이터에 대 한 액세스 암호화 또는 제한</span><span class="sxs-lookup"><span data-stu-id="5f60e-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="5f60e-131">서명 되지 않았거나 신뢰할 수 있는 루트에 롤업 하지 않는 인증서를 사용 하 여 서명 됨</span><span class="sxs-lookup"><span data-stu-id="5f60e-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="5f60e-132">드라이버 배포</span><span class="sxs-lookup"><span data-stu-id="5f60e-132">Driver deployment</span></span>

<span data-ttu-id="5f60e-133">Microsoft Managed Desktop은 Microsoft 관리 장치를 사용 하 여 Windows Update 또는 설치 된 받은 편지함을 통해 제공 되는 장치 드라이버만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="5f60e-134">응용 프로그램에서 실행 해야 하는 특정 드라이버가 필요한 경우에는 제한 된 응용 프로그램으로 간주 되므로를 Microsoft Managed Desktop에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f60e-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an  to be deployed to Microsoft Managed Desktop.</span></span> 

