---
title: 장치에 대 한 라이선스 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 장치에 사용 하기 위해 그룹에 라이선스를 할당 하는 방법을 알아봅니다.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011188"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="3a499-103">장치에 대 한 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="3a499-103">Manage licenses for devices</span></span>

<span data-ttu-id="3a499-104">Microsoft 365 for enterprise (장치) 또는 교육을 위한 Microsoft 365 앱 (장치)이 있는 경우 Azure AD 그룹을 사용 하 여 장치에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="3a499-105">장치에 라이선스가 있으면 해당 장치를 사용 하는 모든 사용자가 Microsoft 365 앱 (이전 명칭 Office 365 ProPlus)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="3a499-106">예를 들어 조직의 사용자가 사용 하는 20 개의 랩톱과 태블릿이 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="3a499-107">각 장치에 라이선스를 할당 하면 장치 중 하나에 로그인 하는 각 사용자는 자신의 라이선스 없이도 Microsoft 365 앱 for enterprise를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a499-108">Microsoft 365 용 장치 기반 라이선스는 일부 상업용 고객 및 일부 교육 고객의 추가 기능 라이선스로만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="3a499-109">상업용 고객의 경우 라이선스는 *Microsoft 365 Apps for enterprise (장치)* 이며 엔터프라이즈 계약/엔터프라이즈 계약 구독을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="3a499-110">교육 고객의 경우 라이선스는 *교육을 위한 Microsoft 365 앱 (장치)* 이며 EES (교육 솔루션) 등록을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="3a499-111">자세한 내용은 [교육 사용 가능 여부](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)에 대 한 블로그 게시물을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a499-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="3a499-112">상업용 사용 가능 여부는 Microsoft 계정 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a499-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="3a499-113">시작 하려면 Azure Active Directory 관리 센터에서 그룹을 만든 다음이 그룹에 장치를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="3a499-114">장치 요구 사항을 비롯 한 장치 라이선스에 대 한 자세한 내용은 사용할 수 있는 그룹 유형 및 Microsoft 365 Apps for enterprise for enterprise 라이선스를 사용 하도록 구성 하는 방법을 참조 [365](https://go.microsoft.com/fwlink/p/?linkid=2094216)하세요.</span><span class="sxs-lookup"><span data-stu-id="3a499-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a499-115">이 문서의 작업을 완료 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="3a499-116">장치에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="3a499-116">Assign licenses to devices</span></span>

<span data-ttu-id="3a499-117">그룹에 라이선스를 할당 하는 경우 그룹 내의 모든 장치에 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="3a499-118">하나의 구독을 단일 그룹에만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="3a499-119">Microsoft 365 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3a499-120">**라이선스** 페이지에서 **Microsoft 365 for 교육용 (장치)** 또는 **microsoft 365 앱 for enterprise (장치)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="3a499-121">다음 페이지에서 구독을 선택 하 고 **라이선스 할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="3a499-122">**그룹에 라이선스 할당** 창에서 그룹 이름을 입력 하 고 결과에서 선택 하 여 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="3a499-123">**할당**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="3a499-124">장치에서 라이선스 할당 해제</span><span class="sxs-lookup"><span data-stu-id="3a499-124">Unassign licenses from devices</span></span>

<span data-ttu-id="3a499-125">그룹의 라이선스 할당을 취소 하는 경우 그룹 내의 모든 장치에서 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="3a499-126">모든 앱 및 연결 된 데이터는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="3a499-127">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="3a499-128">**라이선스** 페이지에서 **Microsoft 365 for 교육용 (장치)** 또는 **microsoft 365 앱 for enterprise (장치)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="3a499-129">다음 페이지에서 구독을 선택 하 고 **기타 작업**을 선택한 다음 **라이선스 할당**해제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="3a499-130">**라이선스 할당** 해제 대화 상자에서 **할당**해제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a499-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>