---
title: 관리 포털에서 관리자 연락처 추가 및 확인
description: 각 중점 영역에 대해 누구에게 연락해야 하는지 알려주세요.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d34d7082150b4131634fb695ce6664ded50e6f9d
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823840"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="c91d4-104">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="c91d4-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="c91d4-105">Microsoft Managed Desktop 서비스가 고객과 소통하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="c91d4-106">의사 소통이 원활하고 올바른 사용자에게 확인하고 있는지 확인하려면 관리자 연락처 집합을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="c91d4-107">Microsoft Managed Desktop IT 운영팀에서 이 사용자들에게 연락하여 테넌트에 대한 문제 해결에 대한 도움을 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c91d4-108">관리자 포털에서 이미 이 연락처를 추가했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="c91d4-109">이 경우에는 심각한 문제가 발생할 경우 Microsoft Managed Desktop이 연락할 수 **있어야** 하기 때문에 연락처 목록이 정확한지 다시 한 번 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c91d4-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="c91d4-110">Microsoft Managed Desktop 관리 포털에 대한 Azure Active Directory 액세스</span><span class="sxs-lookup"><span data-stu-id="c91d4-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="c91d4-111">Microsoft Managed Desktop 관리 포털을 사용하려면 포털에 액세스 하는 사용자가 다음 Azure AD(Active Directory) 역할 중 하나를 보유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="c91d4-112">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="c91d4-112">Global Administrator</span></span>
- <span data-ttu-id="c91d4-113">Intune 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="c91d4-113">Intune Service Administrator</span></span>
- <span data-ttu-id="c91d4-114">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="c91d4-114">Billing Administrator</span></span>
- <span data-ttu-id="c91d4-115">서비스 지원 관리자</span><span class="sxs-lookup"><span data-stu-id="c91d4-115">Service Support Administrator</span></span>

<span data-ttu-id="c91d4-116">전역 관리자는 Microsoft Managed Desktop에 조직을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c91d4-117">모든 5개 역할은 관리자 포털에서 동일한 액세스 권한을 가지며 작업을 시작하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="c91d4-118">Azure AD에서 역할을 할당하는 방법에 대한 자세한 내용은 [Azure Active Directory에서 관리자 역할 사용 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c91d4-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="c91d4-119">관리자 연락처 포커스 영역</span><span class="sxs-lookup"><span data-stu-id="c91d4-119">Admin contact areas of focus</span></span>

<span data-ttu-id="c91d4-120">관리자 연락처는 질문에 답하고 다양한 중점 영역에 대한 의사 결정을 내릴 수 있는 최고의 사용자나 그룹이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="c91d4-121">**Microsoft Managed Desktop 운영팀이 이러한 관리자 연락처에 연락하여 고객이 제출한 지원 요청과 관련된 질문을 할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c91d4-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="c91d4-122">이 관리자 연락처는 지원 요청 업데이트와 새 메시지에 대한 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="c91d4-123">해당 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-123">These areas include:</span></span>

<span data-ttu-id="c91d4-124">포커스 영역</span><span class="sxs-lookup"><span data-stu-id="c91d4-124">Area of focus</span></span> | <span data-ttu-id="c91d4-125">관련 질문</span><span class="sxs-lookup"><span data-stu-id="c91d4-125">For questions about</span></span>
--- | ---
<span data-ttu-id="c91d4-126">앱 패키징</span><span class="sxs-lookup"><span data-stu-id="c91d4-126">App packaging</span></span> | <span data-ttu-id="c91d4-127">앱 패키징 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c91d4-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="c91d4-128">장치</span><span class="sxs-lookup"><span data-stu-id="c91d4-128">Devices</span></span> | <span data-ttu-id="c91d4-129">장치 상태, Microsoft Managed Desktop 장치를 사용하여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c91d4-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c91d4-130">보안</span><span class="sxs-lookup"><span data-stu-id="c91d4-130">Security</span></span> | <span data-ttu-id="c91d4-131">Microsoft Managed Desktop 장치를 사용하여 보안 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c91d4-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c91d4-132">IT 지원 센터</span><span class="sxs-lookup"><span data-stu-id="c91d4-132">IT help desk</span></span> | <span data-ttu-id="c91d4-133">지원 담당자가 Microsoft Managed Desktop 지원 영역 외부에서 최종 사용자 티켓을 전달하는 경우</span><span class="sxs-lookup"><span data-stu-id="c91d4-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="c91d4-134">기타</span><span class="sxs-lookup"><span data-stu-id="c91d4-134">Other</span></span> | <span data-ttu-id="c91d4-135">다른 영역에서 다루지 않는 문제</span><span class="sxs-lookup"><span data-stu-id="c91d4-135">For issues not covered by other areas</span></span>

<span data-ttu-id="c91d4-136">**이러한 연락처로 선택한 사용자는 Microsoft Managed Desktop 환경을 결정할 수 있는 지식과 권한이 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c91d4-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="c91d4-137">Microsoft Managed Desktop 환경을 온보드하는 경우 로컬 지원 센터 및 보안에 대한 연락처를 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="c91d4-138">[지원 요청을 제출](../service-description/support.md)하는 경우 관리자 연락처가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="c91d4-139">지원 요청의 포커스 영역에 대한 관리자에게 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="c91d4-140">**관리자 연락처 추가하기**</span><span class="sxs-lookup"><span data-stu-id="c91d4-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="c91d4-141">[Microsoft Managed Desktop 관리 포털](https://aka.ms/mwaasportal)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="c91d4-142">**지원**에서 **관리자 연락처**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![지원 메뉴, 상단 근처에서 선택된 관리자 연락처](images/admincontacts.png)

3. <span data-ttu-id="c91d4-144">**추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c91d4-144">Select **Add**.</span></span>

    ![내보내기 및 새로 고침 왼쪽에 관리 포털, 추가 단추](images/adminadd.png)

4.  <span data-ttu-id="c91d4-146">**포커스 영역**을 선택하고 연락처에 대한 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![기타, 앱 및 보안과 같은 포커스 영역 목록](images/areaoffocus.png)

5. <span data-ttu-id="c91d4-148">각 포커스가 영역에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c91d4-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="c91d4-149">Microsoft Managed Desktop을 시작하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="c91d4-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="c91d4-150">관리 포털에서 관리자 연락처 추가 및 확인(이 항목)</span><span class="sxs-lookup"><span data-stu-id="c91d4-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="c91d4-151">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="c91d4-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="c91d4-152">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c91d4-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="c91d4-153">장치에 Intune 회사 포털 설치</span><span class="sxs-lookup"><span data-stu-id="c91d4-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="c91d4-154">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="c91d4-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="c91d4-155">Microsoft Managed Desktop 장치 설정</span><span class="sxs-lookup"><span data-stu-id="c91d4-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="c91d4-156">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="c91d4-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="c91d4-157">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="c91d4-157">Deploy apps to devices</span></span>](deploy-apps.md)