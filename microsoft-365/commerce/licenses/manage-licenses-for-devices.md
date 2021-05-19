---
title: 장치에 대한 라이선스 관리
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 디바이스에서 사용할 수 있는 그룹에 라이선스를 할당하는 방법을 배워야 합니다.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535665"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="0f897-103">장치에 대한 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="0f897-103">Manage licenses for devices</span></span>

<span data-ttu-id="0f897-104">디바이스(엔터프라이즈용 Microsoft 365 앱) 또는 Microsoft 365 앱(장치)가 있는 경우 Azure AD 그룹을 사용하여 디바이스에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="0f897-105">디바이스에 라이선스가 있는 경우 해당 장치를 사용하는 모든 사용자가 라이선스를 사용할 엔터프라이즈용 Microsoft 365 앱(Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="0f897-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="0f897-106">예를 들어 조직의 사람들이 사용하는 랩톱과 태블릿이 20개라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="0f897-107">각 장치에 라이선스를 할당하면 장치 중 하나에 로그인하는 각 사용자가 고유한 엔터프라이즈용 Microsoft 365 앱 필요 없이 라이선스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f897-108">디바이스 기반 라이선싱은 엔터프라이즈용 Microsoft 365 앱 일부 상용 고객 및 일부 교육 고객을 위한 추가 기능 라이선스로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="0f897-109">상업적 고객의 경우  라이선스는 엔터프라이즈용 Microsoft 365 앱(장치)으로, 기업계약/기업계약 구독을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="0f897-110">교육 고객의 경우 라이선스는 *Microsoft 365 앱(디바이스)에* 등록되어 있으며 EES(Education 솔루션 등록)를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="0f897-111">자세한 내용은 교육 가용성에 대한 블로그 [게시물을 참조하세요.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)</span><span class="sxs-lookup"><span data-stu-id="0f897-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="0f897-112">상업적 가용성을 확인하려면 Microsoft 계정 담당자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f897-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="0f897-113">시작하려면 Azure Active Directory 관리 센터에서 그룹을 만든 다음 그룹에 장치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="0f897-114">장치 요구 사항, 사용할 수 있는 그룹 유형 및 장치 라이선스를 사용하도록 장치 라이선스를 엔터프라이즈용 Microsoft 365 앱 방법을 포함하여 장치 라이선스에 대한 자세한 내용은 장치 기반 라이선싱을 [엔터프라이즈용 Microsoft 365 앱.](/deployoffice/device-based-licensing)</span><span class="sxs-lookup"><span data-stu-id="0f897-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f897-115">이 문서의 작업을 완료하려면 전역 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="0f897-116">장치에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="0f897-116">Assign licenses to devices</span></span>

<span data-ttu-id="0f897-117">그룹에 라이선스를 할당할 때 그룹 내의 모든 장치에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="0f897-118">단일 그룹에 구독을 하나만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="0f897-119">Microsoft 365 관리 센터에서 청구 라이선스   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0f897-120">라이선스 **페이지에서** 교육용 **Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f897-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0f897-121">On the next page, choose a subscription, then choose **Assign licenses**.</span><span class="sxs-lookup"><span data-stu-id="0f897-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="0f897-122">그룹에 **라이선스** 할당 창에서 그룹 이름을 입력하기 시작한 다음 결과에서 선택한 후 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="0f897-123">할당 **을** 선택한 다음 **닫기 를 선택.**</span><span class="sxs-lookup"><span data-stu-id="0f897-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="0f897-124">장치에서 라이선스를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-124">Unassign licenses from devices</span></span>

<span data-ttu-id="0f897-125">그룹에서 라이선스를 배포를 제거하면 그룹 내의 모든 장치에서 라이선스가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="0f897-126">그러면 모든 앱과 관련 데이터가 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="0f897-127">관리 센터에서 청구 라이선스   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">페이지로</a> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f897-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="0f897-128">라이선스 **페이지에서** 교육용 **Microsoft 365 앱(장치)** 또는 **엔터프라이즈용 Microsoft 365 앱(장치)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f897-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="0f897-129">다음 페이지에서 구독을 선택하고 세 개의 점(추가 작업)을 선택한 다음 라이선스 배포 **취소를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f897-129">On the next page, choose a subscription, select the three dots (more actions), and then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="0f897-130">라이선스의 사용 허가 **안 함 대화** 상자에서 **Unassign 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f897-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
