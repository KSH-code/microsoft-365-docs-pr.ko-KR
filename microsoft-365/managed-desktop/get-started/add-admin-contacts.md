---
title: 관리 포털에서 관리자 연락처 추가 및 확인
description: 각 포커스 영역에 대해 문의할 사람을 알려주십시오.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012069"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="787b5-104">관리 포털에서 관리자 연락처 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="787b5-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="787b5-105">Microsoft Managed Desktop service가 고객과 통신 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="787b5-106">통신을 합리화 하 고 적절 한 사용자가 확인 하는 일이 없도록 하려면 관리자 연락처 집합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="787b5-107">Microsoft Managed Desktop IT 작업에서는 해당 사용자에 게 연락 하 여 테 넌 트에 대 한 문제 해결 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="787b5-108">관리자 포털에서 이러한 연락처를 이미 추가 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="787b5-109">이 경우 심각한 사고가 발생 하는 경우 Microsoft Managed Desktop이 연락할 수 **있어야** 하므로 연락처 목록이 정확한 지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="787b5-110">Microsoft Managed Desktop Admin 포털에 대 한 Azure Active Directory 액세스</span><span class="sxs-lookup"><span data-stu-id="787b5-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="787b5-111">Microsoft Managed Desktop Administration portal을 사용 하려면 포털에 액세스 하는 사용자에 게 다음 Azure AD (Active Directory) 역할 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="787b5-112">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="787b5-112">Global Administrator</span></span>
- <span data-ttu-id="787b5-113">Intune 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="787b5-113">Intune Service Administrator</span></span>
- <span data-ttu-id="787b5-114">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="787b5-114">Billing Administrator</span></span>
- <span data-ttu-id="787b5-115">서비스 지원 관리자</span><span class="sxs-lookup"><span data-stu-id="787b5-115">Service Support Administrator</span></span>

<span data-ttu-id="787b5-116">전역 관리자는 Microsoft Managed Desktop에서 조직을 등록할 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="787b5-117">관리 포털 내에서 모든 5 개의 역할이 동일한 액세스 권한을 가지 며 작업을 시작 하 고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="787b5-118">Azure AD에서 이러한 역할을 할당 하는 방법에 대 한 자세한 내용은 [Azure Active Directory에서 관리자 역할 권한을](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="787b5-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="787b5-119">포커스의 관리자 연락처 영역</span><span class="sxs-lookup"><span data-stu-id="787b5-119">Admin contact areas of focus</span></span>

<span data-ttu-id="787b5-120">관리자 연락처는 질문에 답하고 각 영역에 대 한 의사 결정을 내릴 수 있는 가장 좋은 사용자나 그룹 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="787b5-121">**Microsoft Managed Desktop 작업은 해당 관리자 연락처에 연락 하 여 고객의 지원 요청을 포함 하는 질문을 제공 합니다.**</span><span class="sxs-lookup"><span data-stu-id="787b5-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="787b5-122">이러한 관리 연락처는 지원 요청 업데이트 및 새 메시지에 대 한 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="787b5-123">이러한 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-123">These areas include:</span></span>

<span data-ttu-id="787b5-124">포커스 영역</span><span class="sxs-lookup"><span data-stu-id="787b5-124">Area of focus</span></span> | <span data-ttu-id="787b5-125">에 대 한 질문</span><span class="sxs-lookup"><span data-stu-id="787b5-125">For questions about</span></span>
--- | ---
<span data-ttu-id="787b5-126">앱 패키징</span><span class="sxs-lookup"><span data-stu-id="787b5-126">App packaging</span></span> | <span data-ttu-id="787b5-127">앱 패키징 문제 해결</span><span class="sxs-lookup"><span data-stu-id="787b5-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="787b5-128">장치</span><span class="sxs-lookup"><span data-stu-id="787b5-128">Devices</span></span> | <span data-ttu-id="787b5-129">장치 상태, Microsoft Managed Desktop devices 문제 해결</span><span class="sxs-lookup"><span data-stu-id="787b5-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="787b5-130">보안</span><span class="sxs-lookup"><span data-stu-id="787b5-130">Security</span></span> | <span data-ttu-id="787b5-131">Microsoft Managed Desktop 장치에 대 한 보안 문제 해결</span><span class="sxs-lookup"><span data-stu-id="787b5-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="787b5-132">IT 지원 센터</span><span class="sxs-lookup"><span data-stu-id="787b5-132">IT help desk</span></span> | <span data-ttu-id="787b5-133">지원 직원이 Microsoft 관리 되는 데스크톱 지원 영역을 벗어나는 최종 사용자 티켓을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="787b5-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="787b5-134">기타</span><span class="sxs-lookup"><span data-stu-id="787b5-134">Other</span></span> | <span data-ttu-id="787b5-135">다른 영역에 포함 되지 않는 문제의 경우</span><span class="sxs-lookup"><span data-stu-id="787b5-135">For issues not covered by other areas</span></span>

<span data-ttu-id="787b5-136">**이러한 연락처에 대해 선택한 사람은 Microsoft Managed Desktop 환경에 대 한 의사 결정을 내리는 데 필요한 지식과 권한을가지고 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="787b5-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="787b5-137">Microsoft Managed Desktop environment를 온보드 하면 로컬 헬프데스크 및 보안에 대 한 연락처를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="787b5-138">[지원 요청을 제출](../working-with-managed-desktop/support.md)하는 경우 관리자 연락처가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-138">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="787b5-139">지원 요청의 포커스 영역에 대 한 관리자 연락처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="787b5-140">**관리자 연락처를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="787b5-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="787b5-141">[Microsoft Managed 데스크톱 관리 포털](https://aka.ms/mwaasportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="787b5-142">**지원**에서 **관리자 연락처**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![지원 메뉴, 관리자 연락처](images/admincontacts.png)

3. <span data-ttu-id="787b5-144">**추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-144">Select **Add**.</span></span>

    ![관리 포털 추가 단추](images/adminadd.png)

4.  <span data-ttu-id="787b5-146">**포커스 영역** 을 선택 하 고 연락처에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![포커스 영역 목록](images/areaoffocus.png)

5. <span data-ttu-id="787b5-148">포커스의 각 영역에 대해 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="787b5-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="787b5-149">Microsoft Managed Desktop을 시작 하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="787b5-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="787b5-150">관리자 포털에서 관리자 연락처 추가 및 확인 (이 항목)</span><span class="sxs-lookup"><span data-stu-id="787b5-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="787b5-151">조건부 액세스 조정</span><span class="sxs-lookup"><span data-stu-id="787b5-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="787b5-152">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="787b5-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="787b5-153">장치에 Intune 회사 포털 설치</span><span class="sxs-lookup"><span data-stu-id="787b5-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="787b5-154">엔터프라이즈 상태 로밍 사용</span><span class="sxs-lookup"><span data-stu-id="787b5-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="787b5-155">Microsoft Managed Desktop 장치 설정</span><span class="sxs-lookup"><span data-stu-id="787b5-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="787b5-156">사용자들이 장치를 사용할 수 있도록 준비시키기</span><span class="sxs-lookup"><span data-stu-id="787b5-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="787b5-157">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="787b5-157">Deploy apps to devices</span></span>](deploy-apps.md)