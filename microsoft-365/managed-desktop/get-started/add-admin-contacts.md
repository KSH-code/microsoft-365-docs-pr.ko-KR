---
title: Microsoft 관리 되는 데스크톱 관리 포털에서 Admin 대화 상대를 추가 합니다.
description: 저희에 게 알려주십시오 회의 센터의 각 영역에 대 한 연락할 사람에 있습니다.
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 65dd8709c469826e2696015c13823c58eb10e342
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869898"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="73bff-104">Microsoft 관리 되는 데스크톱 관리 포털에서 Admin 대화 상대를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="73bff-p101">데스크톱을 관리 하는 Microsoft 서비스 고객와 통신 하는 여러 가지가 있습니다. 커뮤니케이션을 간소화 하 고 최상의 연락처를 사용 하 여 확인 하는 확인을 하려면 관리 연락처의 집합을 제공 해야 합니다. Microsoft 관리 되는 데스크톱 IT 작업이이 사용자 들이 테 넌 트에 대 한 문제를 해결에 게 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-p101">There are several ways that Microsoft Managed Desktop service communicates with customers. To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts. Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="73bff-108">Microsoft 관리 되는 데스크톱 관리 포털에 대 한 azure Active Directory 액세스</span><span class="sxs-lookup"><span data-stu-id="73bff-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="73bff-109">Microsoft 관리 되는 데스크톱 관리 포털 포털에 액세스 하는 사용자가 이러한 Azure Active Directory (AD) 역할 중 하나는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="73bff-110">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="73bff-110">Global Administrator</span></span>
- <span data-ttu-id="73bff-111">Intune 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="73bff-111">Intune Service Administrator</span></span>
- <span data-ttu-id="73bff-112">대금 청구 관리자</span><span class="sxs-lookup"><span data-stu-id="73bff-112">Billing Administrator</span></span>
- <span data-ttu-id="73bff-113">서비스 지원 관리자</span><span class="sxs-lookup"><span data-stu-id="73bff-113">Service Support Administrator</span></span>

<span data-ttu-id="73bff-114">Azure AD에 할당 하 고 이러한 역할에 대 한 자세한 내용은 [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73bff-114">For more information on these roles and assigning them in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="73bff-115">관리 연락처 주요 영역</span><span class="sxs-lookup"><span data-stu-id="73bff-115">Admin contact focus areas</span></span>

<span data-ttu-id="73bff-p102">최상의 사용자 또는 그룹 질문에 대답 하 고 다른 주요 영역에 대 한 결정을 내릴 수 있는 대화 상대 관리 해야 합니다. 이러한 영역에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-p102">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas. These areas include:</span></span>

<span data-ttu-id="73bff-118">포커스 영역</span><span class="sxs-lookup"><span data-stu-id="73bff-118">Focus area</span></span> | <span data-ttu-id="73bff-119">에 대 한 질문에 대 한</span><span class="sxs-lookup"><span data-stu-id="73bff-119">For questions about</span></span>
--- | ---
<span data-ttu-id="73bff-120">앱</span><span class="sxs-lookup"><span data-stu-id="73bff-120">Apps</span></span> | <span data-ttu-id="73bff-121">응용 프로그램 패키지를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-121">Troubleshooting App Packaging</span></span>
<span data-ttu-id="73bff-122">장치</span><span class="sxs-lookup"><span data-stu-id="73bff-122">Devices</span></span> | <span data-ttu-id="73bff-123">Microsoft 관리 되는 데스크톱 장치와 문제를 해결 하는 장치 상태</span><span class="sxs-lookup"><span data-stu-id="73bff-123">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="73bff-124">보안</span><span class="sxs-lookup"><span data-stu-id="73bff-124">Security</span></span> | <span data-ttu-id="73bff-125">Microsoft 관리 되는 데스크톱 장치와 보안 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-125">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="73bff-126">기타</span><span class="sxs-lookup"><span data-stu-id="73bff-126">Other</span></span> | <span data-ttu-id="73bff-127">다른 영역을 차지 하지 않는 문제</span><span class="sxs-lookup"><span data-stu-id="73bff-127">For issues not covered by other areas</span></span>

<span data-ttu-id="73bff-p103">선택한 사용자 지식 및 Microsoft 관리 되는 데스크톱 환경에 대 한 결정을 내릴 수 권한을 포함 하도록 이러한 연락처 요구 사항에 대 한 합니다. 때 온보드 Microsoft 관리 하는 데스크톱 환경 하 여 로컬 헬프데스크 및 보안에 대 한 대화 상대를 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-p103">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment. When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="73bff-p104">관리 연락처는 다음과 같은 필요한 경우 [지원 요청을 제출](../working-with-managed-desktop/support.md)합니다. 지원 요청의 포커스 영역에 대 한 관리 연락처를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-p104">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md). You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="73bff-132">**Admin 대화 상대를 추가 하려면**</span><span class="sxs-lookup"><span data-stu-id="73bff-132">**To add admin contacts**</span></span>

1.  <span data-ttu-id="73bff-133">[Microsoft 관리 되는 데스크톱 관리 포털](http://aka.ms/mwaasportal)에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-133">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="73bff-134">**지원** **Admin 대화 상대**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-134">Under **Support**, select **Admin contacts**.</span></span> 

    ![지원 메뉴, 대화 상대 관리](images/admincontacts.png)

3. <span data-ttu-id="73bff-136">**추가**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-136">Select **Add**.</span></span>

    ![관리 포털 추가 단추](images/adminadd.png)

4.  <span data-ttu-id="73bff-138">**회의 센터의 영역** 을 선택 하 고 대화 상대에 대 한 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-138">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![회의 센터의 영역 목록](images/areaoffocus.png)

5. <span data-ttu-id="73bff-140">회의 센터의 각 영역에 대해 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bff-140">Repeat for each area of focus.</span></span> 

