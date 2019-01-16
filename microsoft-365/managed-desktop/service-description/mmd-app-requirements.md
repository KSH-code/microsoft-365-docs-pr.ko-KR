---
title: Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869703"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="c0768-103">Microsoft 관리 되는 데스크톱 응용 프로그램 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0768-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="c0768-104">Microsoft 관리 되는 데스크톱 장치를 배포 하려는 비즈니스 라인 응용 프로그램에는이 항목의 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="c0768-105">응용 프로그램 조건</span><span class="sxs-lookup"><span data-stu-id="c0768-105">Application condition</span></span>

<span data-ttu-id="c0768-p101">것이 중요 응용 프로그램은 Microsoft 관리 되는 데스크톱 환경에 저하 하지 않습니다. 다음은 응용 프로그램 배포를 Microsoft에 대 한 순서 대로 충족 해야 하는 요구 사항입니다. 모든 특정된 응용 프로그램 또는 드라이버에 대 한 Microsoft 여기에 제공 된 모든 요구 사항을 내용도 배제 될 수 있습니다. Microsoft는 모든 응용 프로그램 또는 데스크톱을 관리 하는 Microsoft 장치의 성능 및 안정성에 부정적인 영향을 주는 드라이버를 제거 하려면 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="c0768-110">Microsoft 기술을 사용 하 여 배포 가능</span><span class="sxs-lookup"><span data-stu-id="c0768-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="c0768-p102">Microsoft 관리 되는 데스크톱 응용 프로그램을 배포 하려면 Intune, Microsoft 저장소 및 비즈니스를 위한 Microsoft 저장소를 사용 합니다. 따라서 이러한 서비스의 현재 버전에 따라 배포할 수는 방식으로 응용 프로그램으로 패키지화 할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="c0768-113">금지 된 app 클래스</span><span class="sxs-lookup"><span data-stu-id="c0768-113">Prohibited app classes</span></span>

<span data-ttu-id="c0768-114">특정 응용 프로그램 종류는 Microsoft 관리 되는 데스크톱 장치에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="c0768-115">바이러스 백신 제 3 자, 보안, 또는 감사 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="c0768-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="c0768-116">제 3 자 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="c0768-116">3rd party web browsers</span></span>
- <span data-ttu-id="c0768-117">Office 365 Pro Plus 하기 전에 Microsoft Office의 버전</span><span class="sxs-lookup"><span data-stu-id="c0768-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="c0768-118">응용 프로그램을 설치 하거나 다른 타사 소프트웨어 번들</span><span class="sxs-lookup"><span data-stu-id="c0768-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="c0768-119">제한 된 응용 프로그램 동작</span><span class="sxs-lookup"><span data-stu-id="c0768-119">Restricted app behaviors</span></span>

<span data-ttu-id="c0768-p103">특정 응용 프로그램 동작 사용자 환경이 크게 저하 될 수도 있고 Microsoft 관리 되는 데스크톱 장치에 보안 위험이 초래 수도 있습니다. 응용 프로그램 특성에는 다음 동작을 나타내는 하지 항목과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="c0768-122">사용자 환경을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-122">User Experience:</span></span>
- <span data-ttu-id="c0768-123">백그라운드 서비스를 설치 또는 실행 시간이 긴 백그라운드 프로세스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="c0768-124">Windows 시작 경로에 추가 하는 자체</span><span class="sxs-lookup"><span data-stu-id="c0768-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="c0768-125">보안:</span><span class="sxs-lookup"><span data-stu-id="c0768-125">Security:</span></span>
- <span data-ttu-id="c0768-126">문서화 되지 않은 Windows 또는 Office Api를 호출 하거나 내부 Windows 또는 Office 데이터 구조에 의존 관계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="c0768-127">응용 프로그램 저장소로 act 또는 기본 제공 확장 관리자가</span><span class="sxs-lookup"><span data-stu-id="c0768-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="c0768-128">최종 사용자의 권한을 상승합니다</span><span class="sxs-lookup"><span data-stu-id="c0768-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="c0768-129">보안상 취약점 알려진</span><span class="sxs-lookup"><span data-stu-id="c0768-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="c0768-130">신뢰할 수 있는 루트에 겹쳐서 표시 하지는 인증서를 사용 하 여 서명</span><span class="sxs-lookup"><span data-stu-id="c0768-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="c0768-131">암호화 또는 최종 사용자 데이터에 대 한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="c0768-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="c0768-132">런타임에 운영 체제 코드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="c0768-133">드라이버 배포</span><span class="sxs-lookup"><span data-stu-id="c0768-133">Driver deployment</span></span>

<span data-ttu-id="c0768-134">경우가 아니면 드라이버를 Windows Update에서 사용할 수는 Windows 하드웨어 품질 랩 (WHQL) 서명 별도로, Microsoft 드라이버를 배포 하는 Microsoft 관리 되는 데스크톱 장치를 하기 전에 Microsoft 드라이버를 승인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0768-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
