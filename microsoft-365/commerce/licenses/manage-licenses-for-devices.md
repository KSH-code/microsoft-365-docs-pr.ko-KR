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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246354"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="adc47-103">장치에 대 한 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="adc47-103">Manage licenses for devices</span></span>

<span data-ttu-id="adc47-104">교육용 (장치) 용 Office 365 ProPlus가 있는 경우 Azure AD 그룹을 사용 하 여 장치에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="adc47-105">장치에 라이선스가 있으면 해당 장치를 사용 하는 모든 사용자가 Office 365를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="adc47-106">예를 들어 조직의 사용자가 사용 하는 20 개의 랩톱과 태블릿이 있는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="adc47-107">각 장치에 라이선스를 할당 하면 장치 중 하나에 로그인 하는 각 사용자는 자신의 라이선스 없이도 Office 365을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adc47-108">Office 365 ProPlus for 교육용 (장치)은 교육 A3 및 A5 볼륨 라이선스 고객만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="adc47-109">시작 하려면 Azure Active Directory 관리 센터에서 그룹을 만든 다음이 그룹에 장치를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="adc47-110">장치 요구 사항을 비롯 한 장치 라이선스에 대 한 자세한 내용은 사용할 수 있는 그룹 유형 및 장치 라이선스를 사용 하도록 Office 365 ProPlus를 구성 하는 방법에 대 한 자세한 내용은 [교육용 고객을 위한 365 office 라이선스 장치 라이선싱](https://go.microsoft.com/fwlink/p/?linkid=2094216)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adc47-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adc47-111">이 문서의 작업을 완료 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="adc47-112">장치에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="adc47-112">Assign licenses to devices</span></span>

<span data-ttu-id="adc47-113">그룹에 라이선스를 할당 하는 경우 그룹 내의 모든 장치에 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="adc47-114">하나의 구독을 단일 그룹에만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="adc47-115">Microsoft 365 관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="adc47-116">**라이선스** 페이지에서 **교육용 Office 365 ProPlus (장치)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="adc47-117">**Office 365 ProPlus For 교육용 (장치)** 페이지에서 구독을 선택 하 고 **라이선스 할당**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="adc47-118">**그룹에 라이선스 할당** 창에서 그룹 이름을 입력 하 고 결과에서 선택 하 여 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="adc47-119">**할당**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="adc47-120">장치에서 라이선스 할당 해제</span><span class="sxs-lookup"><span data-stu-id="adc47-120">Unassign licenses from devices</span></span>

<span data-ttu-id="adc47-121">그룹의 라이선스 할당을 취소 하는 경우 그룹 내의 모든 장치에서 라이선스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="adc47-122">모든 앱 및 연결 된 데이터는 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="adc47-123">관리 센터에서 **청구** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">라이선스</a> 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="adc47-124">**라이선스** 페이지에서 **교육용 Office 365 ProPlus (장치)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="adc47-125">**Office 365 ProPlus For 교육용 (장치)** 페이지에서 구독을 선택 하 고 **기타 작업**을 선택한 다음 **라이선스 할당**해제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="adc47-126">**라이선스 할당** 해제 대화 상자에서 **할당**해제를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc47-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>