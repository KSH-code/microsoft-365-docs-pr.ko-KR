---
title: 기본 이동성 및 보안 해제
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 그룹 또는 정책을 제거하여 기본 이동성 및 보안을 해제합니다.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023872"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="231fa-103">기본 이동성 및 보안 해제</span><span class="sxs-lookup"><span data-stu-id="231fa-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="231fa-104">기본 이동성 및 보안을 효과적으로 해제하려면 장치 관리 정책에서 보안 그룹으로 정의된 사용자 그룹을 제거하거나 정책 자체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="231fa-105">만든 장치 정책에서 사용자 보안 그룹을 제거하여 사용자 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="231fa-106">모든 기본 이동성 및 보안 장치 정책을 제거하여 모든 사용자에 대해 기본 이동성 및 보안을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="231fa-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="231fa-107">이러한 옵션은 조직의 장치에 대한 기본 이동성 및 보안 적용을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="231fa-108">아쉽게도 기본 이동성 및 보안을 설정한 후에 단순히 "비프로비전"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="231fa-109">정책에서 사용자 보안 그룹을 제거하거나 정책 자체를 제거할 때 사용자의 장치에 미치는 영향을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="231fa-110">예를 들어 장치에 따라 전자 메일 프로필 및 캐시된 전자 메일이 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="231fa-111">자세한 내용은 정책을 삭제하거나 정책에서 사용자를 제거하면 어떻게  [하나요?를 참조하세요.](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="231fa-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="231fa-112">기본 모바일 및 보안 장치 정책에서 사용자 보안 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="231fa-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="231fa-113">브라우저 유형:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="231fa-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="231fa-114">장치 정책을 선택하고 정책 **편집 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="231fa-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="231fa-115">배포  **페이지에서**   제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="231fa-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="231fa-116">  \*\*그룹에서*\* 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="231fa-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="231fa-117">제거  **를** 선택하고 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="231fa-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="231fa-118">기본 모바일 및 보안 장치 정책 제거</span><span class="sxs-lookup"><span data-stu-id="231fa-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="231fa-119">브라우저 유형:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="231fa-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="231fa-120">장치 정책을 선택한 다음 정책  **삭제 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="231fa-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="231fa-121">경고 대화 상자에서 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="231fa-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="231fa-122">조직 장치가 여전히 차단된 상태인 경우 디바이스 차단을 해제하는 자세한 단계는 다음에서 액세스 제어 제거 블로그 [게시물을 Office 365용 모바일 장치 관리.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="231fa-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
