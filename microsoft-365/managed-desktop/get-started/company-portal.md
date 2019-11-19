---
title: 장치에 Intune 회사 포털 설치
description: Microsoft Managed Desktop 장치에 회사 포털 앱을 설치 하는 방법에 대 한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 회사 포털
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4e83983ae7b8b936b639382f025f1f88eeca0762
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699678"
---
# <a name="install-intune-company-portal-on-on-devices"></a><span data-ttu-id="43632-104">장치에 Intune 회사 포털 설치</span><span class="sxs-lookup"><span data-stu-id="43632-104">Install Intune Company Portal on on devices</span></span>

<span data-ttu-id="43632-105">Microsoft Managed Desktop을 사용 하려면 IT 관리자가 Microsoft Managed Desktop devices 사용자를 위해 Intune 회사 포털을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="43632-106">조직의 몇 가지 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43632-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="43632-107">사용자는 사용 가능한 응용 프로그램을 찾아보고 설치 하기 위한 한 가지 장소를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43632-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="43632-108">IT 관리자는 사용자를 위해 범주별로 응용 프로그램을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43632-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="43632-109">Microsoft Project 및 Microsoft Visio와 같은 일부 응용 프로그램의 경우에는 회사 포털이 Microsoft Managed Desktop을 사용 하 여 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="43632-110">IT 관리자는 조직의 회사 포털을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43632-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="43632-111">여기에는 브랜드 이미징, 로컬 지원 연락처에 추가 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43632-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="43632-112">자세한 내용은 [How To Configure The Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43632-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="43632-113">이 항목에서는 Microsoft Managed Desktop 사용자에 게 Intune 회사 포털을 배포 하는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="43632-114">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43632-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="43632-115">비즈니스를 위해 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화</span><span class="sxs-lookup"><span data-stu-id="43632-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="43632-116">사용자에 게 회사 포털 할당</span><span class="sxs-lookup"><span data-stu-id="43632-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="43632-117">사용자에 게 변경 내용 전달</span><span class="sxs-lookup"><span data-stu-id="43632-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="43632-118">1 단계-비즈니스를 위해 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화</span><span class="sxs-lookup"><span data-stu-id="43632-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="43632-119">앱을 구입 하 고 Intune과 동기화 하는 방법에 대 한 자세한 내용은 microsoft *Managed 데스크톱 장치에 앱 배포*의 [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43632-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="43632-120">이 항목에서는 다음 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="43632-121">비즈니스를 위해 Microsoft Store에서 회사 포털 구매</span><span class="sxs-lookup"><span data-stu-id="43632-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="43632-122">Intune과 Microsoft Store for Business 간 강제 동기화</span><span class="sxs-lookup"><span data-stu-id="43632-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="43632-123">Intune과 Microsoft Store for Business 간의 활성 동기화 확인</span><span class="sxs-lookup"><span data-stu-id="43632-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="43632-124">2 단계-사용자에 게 회사 포털 할당</span><span class="sxs-lookup"><span data-stu-id="43632-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="43632-125">Microsoft Managed Desktop Admin 포털을 통해 Microsoft Managed Desktop 작업에 대 한 지원 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="43632-126">지원 요청에서 회사 포털에 사용자를 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="43632-127">Microsoft Managed Desktop은 회사 포털을 테 넌 트에 배포 하 고 조직의 Microsoft Managed Desktop 장치에 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="43632-128">Microsoft Managed Desktop에서 지원 요청을 제출 하는 방법에 대 한 자세한 내용은 [Microsoft Managed desktop에 대 한 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="43632-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="43632-129">3 단계-사용자에 게 변경 내용 전달</span><span class="sxs-lookup"><span data-stu-id="43632-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="43632-130">조직의 IT 관리자로 서 사용자에 게 조직에서 회사 포털을 사용 하는 방법을 알려 주는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="43632-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="43632-131">Microsoft Managed Desktop이 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43632-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="43632-132">회사 포털에서 응용 프로그램을 설치 하는 단계</span><span class="sxs-lookup"><span data-stu-id="43632-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="43632-133">자세한 내용은 [장치에 앱 설치 및 공유](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43632-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="43632-134">현재 사용할 수 없는 응용 프로그램에 대 한 요청을 IT 관리자에 게 보내는 방법</span><span class="sxs-lookup"><span data-stu-id="43632-134">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="43632-135">자세한 내용은 [회사 또는 학교에 대 한 앱 요청](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43632-135">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="43632-136">Microsoft Managed Desktop을 시작 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="43632-136">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="43632-137">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="43632-137">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="43632-138">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="43632-138">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="43632-139">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="43632-139">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="43632-140">Intune 회사 포털 배포 (이 항목)</span><span class="sxs-lookup"><span data-stu-id="43632-140">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="43632-141">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="43632-141">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="43632-142">장치 설정</span><span class="sxs-lookup"><span data-stu-id="43632-142">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="43632-143">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="43632-143">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="43632-144">앱 배포</span><span class="sxs-lookup"><span data-stu-id="43632-144">Deploy apps</span></span>](deploy-apps.md)
