---
title: 장치에 Intune 회사 포털 설치
description: Microsoft Managed Desktop 디바이스에 회사 포털 앱 설치에 대한 정보
keywords: Microsoft Managed Desktop, Microsoft 365, 회사 포털
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939287"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="8782b-104">장치에 Intune 회사 포털 설치</span><span class="sxs-lookup"><span data-stu-id="8782b-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="8782b-105">Microsoft Managed Desktop을 사용하려면 IT 관리자가 Microsoft Managed Desktop 장치를 사용하여 사용자를 위해 Intune 회사 포털을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8782b-106">다음은 조직에 대한 몇 가지 이점입니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="8782b-107">사용자는 사용 가능한 응용 프로그램을 찾아서 설치할 수 있는 한 곳을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="8782b-108">IT 관리자는 사용자 범주별로 응용 프로그램을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="8782b-109">일부 응용 프로그램(예: Microsoft Project 및 Microsoft Visio)에서는 회사 포털이 Microsoft Managed Desktop과 함께 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="8782b-110">IT 관리자는 조직에 맞게 회사 포털을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="8782b-111">여기에는 브랜드 이미징, 로컬 지원 연락처 추가 등도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="8782b-112">자세한 내용은 Microsoft Intune 회사 포털 앱을 구성하는 [방법을 참조하세요.](https://docs.microsoft.com/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="8782b-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="8782b-113">이 항목에서는 Microsoft Managed Desktop 사용자에게 Intune 회사 포털을 배포하는 프로세스를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8782b-114">전체 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="8782b-115">비즈니스용 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화</span><span class="sxs-lookup"><span data-stu-id="8782b-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="8782b-116">사용자에게 회사 포털 할당</span><span class="sxs-lookup"><span data-stu-id="8782b-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="8782b-117">사용자에게 변경 내용을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="8782b-118">1단계 - 비즈니스용 Microsoft Store에서 회사 포털 구매 및 Intune과 동기화</span><span class="sxs-lookup"><span data-stu-id="8782b-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="8782b-119">앱을 구매하고 Intune과 동기화하는 방법에 대한 자세한 내용은 Microsoft Managed Desktop 디바이스에 앱 배포에서 비즈니스용 [Microsoft Store](deploy-apps.md#msfb-apps) *앱을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="8782b-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="8782b-120">이 항목에서는 다음 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="8782b-121">비즈니스용 Microsoft Store에서 회사 포털 구매</span><span class="sxs-lookup"><span data-stu-id="8782b-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="8782b-122">Intune과 비즈니스용 Microsoft Store 간의 강제 동기화</span><span class="sxs-lookup"><span data-stu-id="8782b-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="8782b-123">Intune과 비즈니스용 Microsoft Store 간의 활성 동기화 확인</span><span class="sxs-lookup"><span data-stu-id="8782b-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="8782b-124">2단계 - 사용자에게 회사 포털 할당</span><span class="sxs-lookup"><span data-stu-id="8782b-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="8782b-125">Microsoft Managed Desktop에 등록한 후 Microsoft Managed Desktop Operations는 테넌트에 회사 포털을 자동으로 배포하고 조직의 Microsoft Managed Desktop 장치에 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="8782b-126">3단계 - 사용자에게 변경 내용을 전달</span><span class="sxs-lookup"><span data-stu-id="8782b-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="8782b-127">조직의 IT 관리자는 조직에서 회사 포털을 사용하는 방법을 사용자에게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="8782b-128">Microsoft Managed Desktop 권장 사항:</span><span class="sxs-lookup"><span data-stu-id="8782b-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="8782b-129">회사 포털에서 응용 프로그램을 설치하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="8782b-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="8782b-130">자세한 내용은 디바이스에서 앱 설치 [및 공유를 참조하세요.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="8782b-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="8782b-131">현재 사용할 수 없는 응용 프로그램에 대한 IT 관리자에게 요청을 보내는 방법</span><span class="sxs-lookup"><span data-stu-id="8782b-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="8782b-132">자세한 내용은 직장 또는 [학교용 앱 요청을 참조하세요.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="8782b-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="8782b-133">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="8782b-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="8782b-134">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="8782b-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="8782b-135">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="8782b-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="8782b-136">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="8782b-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="8782b-137">Intune 회사 포털 배포(이 항목)</span><span class="sxs-lookup"><span data-stu-id="8782b-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="8782b-138">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="8782b-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="8782b-139">장치 설정</span><span class="sxs-lookup"><span data-stu-id="8782b-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="8782b-140">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="8782b-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="8782b-141">앱 배포</span><span class="sxs-lookup"><span data-stu-id="8782b-141">Deploy apps</span></span>](deploy-apps.md)
