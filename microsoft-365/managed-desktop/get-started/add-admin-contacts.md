---
title: Microsoft Managed Desktop administration 포털에서 관리자 연락처 추가
description: 각 포커스 영역에 대해 문의할 사람을 알려주십시오.
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277553"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="cb529-104">Microsoft Managed Desktop administration 포털에서 관리자 연락처 추가</span><span class="sxs-lookup"><span data-stu-id="cb529-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="cb529-105">Microsoft Managed Desktop service가 고객과 통신 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="cb529-106">통신을 합리화 하 고 최상의 연락처를 사용 하 여 확인 하 고 있는지 확인 하려면 관리자 연락처 집합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-106">To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="cb529-107">Microsoft Managed Desktop IT 작업에서는 해당 사용자에 게 연락 하 여 테 넌 트에 대 한 문제 해결 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="cb529-108">Microsoft Managed Desktop Admin 포털에 대 한 Azure Active Directory 액세스</span><span class="sxs-lookup"><span data-stu-id="cb529-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="cb529-109">Microsoft Managed Desktop administration portal을 사용 하려면 포털에 액세스 하는 사용자에 게 다음 Azure AD (Active Directory) 역할 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="cb529-110">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="cb529-110">Global Administrator</span></span>
- <span data-ttu-id="cb529-111">Intune 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="cb529-111">Intune Service Administrator</span></span>
- <span data-ttu-id="cb529-112">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="cb529-112">Billing Administrator</span></span>
- <span data-ttu-id="cb529-113">서비스 지원 관리자</span><span class="sxs-lookup"><span data-stu-id="cb529-113">Service Support Administrator</span></span>

<span data-ttu-id="cb529-114">전역 관리자는 Microsoft Managed Desktop에서 고객을 등록 하기 위한 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-114">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.</span></span>  <span data-ttu-id="cb529-115">관리 포털 내에서 모든 5 개의 역할이 동일한 액세스 권한을 가지 며 작업을 시작 하 고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-115">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span>  <span data-ttu-id="cb529-116">azure AD에서 이러한 역할을 할당 하는 방법에 대 한 자세한 내용은 [azure Active Directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cb529-116">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="cb529-117">관리자 접촉 포커스 영역</span><span class="sxs-lookup"><span data-stu-id="cb529-117">Admin contact focus areas</span></span>

<span data-ttu-id="cb529-118">관리자 연락처는 질문에 답하고 다양 한 포커스 영역에 대 한 의사 결정을 내릴 수 있는 가장 좋은 사용자나 그룹 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-118">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.</span></span>  <span data-ttu-id="cb529-119">Microsoft Managed Desktop 작업은 해당 관리자 연락처에 연락 하 여 고객의 지원 요청을 포함 하는 질문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-119">Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.</span></span>  <span data-ttu-id="cb529-120">이러한 관리 연락처는 지원 요청 업데이트 및 새 메시지에 대 한 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-120">These Admin contacts will receive notifications for support request updates and new messages.</span></span>  <span data-ttu-id="cb529-121">이러한 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-121">These areas include:</span></span>

<span data-ttu-id="cb529-122">포커스 영역</span><span class="sxs-lookup"><span data-stu-id="cb529-122">Focus area</span></span> | <span data-ttu-id="cb529-123">에 대 한 질문</span><span class="sxs-lookup"><span data-stu-id="cb529-123">For questions about</span></span>
--- | ---
<span data-ttu-id="cb529-124">앱</span><span class="sxs-lookup"><span data-stu-id="cb529-124">Apps</span></span> | <span data-ttu-id="cb529-125">앱 패키징 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cb529-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="cb529-126">장치</span><span class="sxs-lookup"><span data-stu-id="cb529-126">Devices</span></span> | <span data-ttu-id="cb529-127">장치 상태, Microsoft Managed Desktop devices 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cb529-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="cb529-128">보안</span><span class="sxs-lookup"><span data-stu-id="cb529-128">Security</span></span> | <span data-ttu-id="cb529-129">Microsoft Managed Desktop 장치에 대 한 보안 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cb529-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="cb529-130">기타</span><span class="sxs-lookup"><span data-stu-id="cb529-130">Other</span></span> | <span data-ttu-id="cb529-131">다른 영역에 포함 되지 않는 문제의 경우</span><span class="sxs-lookup"><span data-stu-id="cb529-131">For issues not covered by other areas</span></span>

<span data-ttu-id="cb529-132">이러한 연락처에 대해 선택한 사람은 Microsoft Managed Desktop 환경에 대 한 의사 결정을 내리는 데 필요한 지식과 권한을가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-132">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="cb529-133">Microsoft Managed Desktop environment를 온보드 하면 로컬 헬프데스크 및 보안에 대 한 연락처를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-133">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="cb529-134">[지원 요청을 제출](../working-with-managed-desktop/support.md)하는 경우 관리자 연락처가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-134">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="cb529-135">지원 요청의 포커스 영역에 대 한 관리자 연락처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-135">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="cb529-136">**관리자 연락처를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="cb529-136">**To add admin contacts**</span></span>

1.  <span data-ttu-id="cb529-137">[Microsoft Managed 데스크톱 관리 포털](http://aka.ms/mwaasportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-137">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="cb529-138">**지원**에서 **관리자 연락처**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-138">Under **Support**, select **Admin contacts**.</span></span> 

    ![지원 메뉴, 관리자 연락처](images/admincontacts.png)

3. <span data-ttu-id="cb529-140">**추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-140">Select **Add**.</span></span>

    ![관리 포털 추가 단추](images/adminadd.png)

4.  <span data-ttu-id="cb529-142">**포커스 영역** 을 선택 하 고 연락처에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-142">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![포커스 영역 목록](images/areaoffocus.png)

5. <span data-ttu-id="cb529-144">포커스의 각 영역에 대해 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb529-144">Repeat for each area of focus.</span></span> 

