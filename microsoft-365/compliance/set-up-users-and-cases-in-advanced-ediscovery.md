---
title: 고급 eDiscovery에서 사용자 및 사례 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '고급 eDiscovery에서 사용자 역할을 구성 하 고 사례를 만들고 사용자를 사례에 할당 하는 방법에 대해 알아봅니다.  '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6cfc8e313816c0c01512dd0d4b71f1dbbd6e6505
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819178"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="f185c-103">고급 eDiscovery에서 사용자 및 사례 설정 (클래식)</span><span class="sxs-lookup"><span data-stu-id="f185c-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="f185c-104">이 항목에서는 고급 eDiscovery (클래식)에 대 한 사용자 및 사례를 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f185c-105">최신 버전의 Advanced eDiscovery에 계속 투자함에 따라, Advanced eDiscovery(*Advanced eDiscovery(클래식)* 또는 *Advanced eDiscovery v1.0*이라고도 함)를 발표합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="f185c-106">Advanced eDiscovery v1.0을 계속 사용하고 있는 경우 [Advanced eDiscovery v2.0](overview-ediscovery-20.md)(*Advanced eDiscovery solution in Microsoft 365*라고도 함)으로 전환하세요.</span><span class="sxs-lookup"><span data-stu-id="f185c-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="f185c-107">Advanced eDiscovery 2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있습니다. 또한 보유자 관리, 통신 관리, 검토 집합 등의 새로운 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="f185c-108">Advanced eDiscovery v1.0의 사용 중지에 대한 자세한 내용은 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f185c-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="f185c-109">사용자 및 사례를 설정 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f185c-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="f185c-110">고급 eDiscovery에서 사례와 사용자를 설정 하기 전에 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="f185c-111">고급 eDiscovery를 사용 하 여 사용자 데이터를 분석 하려면 데이터의 custodian 사용자에 게 Office 365 E5 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="f185c-112">또는 Office 365 E1 또는 E3 라이선스를 사용 하는 사용자에 게 고급 eDiscovery 독립 실행형 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="f185c-113">서비스 케이스에 할당 되 고 고급 eDiscovery를 사용 하 여 데이터를 분석 하는 관리자 및 규정 준수 직원은 E5 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="f185c-114">&amp;Ediscovery 사례를 만들고 여기에 구성원을 추가 하려면 보안 및 준수 센터에서 Ediscovery 관리자 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="f185c-115">보안 및 준수 센터에서 eDiscovery 관리자 역할 그룹에 자신을 추가 하려면 &amp; 조직의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="f185c-116">전역 관리자가 아닌 경우에는 전역 관리자에 게 사용자를 eDiscovery 관리자 역할 그룹에 추가 해 달라고 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="f185c-117">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f185c-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="f185c-118">Microsoft 365 보안 및 준수 센터의 사용 권한 &amp;</span><span class="sxs-lookup"><span data-stu-id="f185c-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="f185c-119">Microsoft 365 보안 및 준수 센터에서 eDiscovery 권한 할당 &amp;</span><span class="sxs-lookup"><span data-stu-id="f185c-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="f185c-120">1 단계: 사용자 eDiscovery 권한 할당</span><span class="sxs-lookup"><span data-stu-id="f185c-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="f185c-121">첫 번째 단계는 사용자가 &amp; eDiscovery 사례의 구성원으로 추가할 수 있도록 보안 및 준수 센터의 요구 사항 사용 권한을 할당 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="f185c-122">보안 및 준수 센터에서 사례 구성원으로 추가 된 사용자는 &amp; 고급 eDiscovery의 사례에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="f185c-123">사용자에 게 eDiscovery 사례의 구성원으로 추가할 수 있는 필수 권한을 할당 하려면 [Microsoft 365 보안 및 &amp; 준수 센터의 eDiscovery 사례](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)에서 1 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f185c-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="f185c-124">2 단계: eDiscovery 사례 만들기 및 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="f185c-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="f185c-125">다음 단계에서는 보안 & 준수 센터에서 새 eDiscovery 사례를 만들고 구성원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="f185c-126">그러면 사례 구성원이 Advanced eDiscovery의 사례에 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="f185c-127">새 eDiscovery 사례를 만들려면 [핵심 eDiscovery 시작](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)에서 3 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f185c-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="f185c-128">EDiscovery 사례에 구성원을 추가 하려면 [핵심 eDiscovery 시작](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case) 에 있는 4 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f185c-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="f185c-129">3 단계: Advanced eDiscovery에서 사례 이동</span><span class="sxs-lookup"><span data-stu-id="f185c-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="f185c-130">EDiscovery 사례를 만들고 구성원을 추가 하 고 나면 사용자 (또는 사례 구성원)가 Advanced eDiscovery의 해당 사례에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f185c-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="f185c-131">Advanced eDiscovery에서 사례에 액세스 하려면 [Advanced ediscovery에서 사례 액세스](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f185c-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f185c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f185c-132">See also</span></span>

[<span data-ttu-id="f185c-133">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="f185c-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f185c-134">고급 eDiscovery에 대 한 데이터 준비 (클래식)</span><span class="sxs-lookup"><span data-stu-id="f185c-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 