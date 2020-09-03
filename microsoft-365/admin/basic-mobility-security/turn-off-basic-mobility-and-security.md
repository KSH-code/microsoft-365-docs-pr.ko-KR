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
description: 기본 이동성 및 보안을 해제 하기 위해 그룹 또는 정책을 제거 합니다.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337000"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="b1eb8-103">기본 이동성 및 보안 해제</span><span class="sxs-lookup"><span data-stu-id="b1eb8-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="b1eb8-104">기본 이동성 및 보안을 효과적으로 해제 하려면 장치 관리 정책에서 보안 그룹으로 정의 된 사용자 그룹을 제거 하거나 정책 자체를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="b1eb8-105">만든 장치 정책에서 사용자 보안 그룹을 제거 하 여 사용자 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="b1eb8-106">모든 기본 이동성 및 보안 장치 정책을 제거 하 여 모든 사용자에 대해 기본 이동성 및 보안을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="b1eb8-107">이러한 옵션은 조직의 장치에 대 한 기본 모바일 및 보안 적용을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="b1eb8-108">아쉽게도 기본 이동성 및 보안을 설정한 후에는이를 "구축 취소" 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="b1eb8-109">정책에서 사용자 보안 그룹을 제거 하거나 정책 자체를 제거할 때 사용자의 장치에 미치는 영향에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="b1eb8-110">예를 들어 장치에 따라 전자 메일 프로필 및 캐시 된 전자 메일이 제거 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="b1eb8-111">자세한 내용은  [정책을 삭제 하거나 정책에서 사용자를 제거 하는 경우 수행 되는 작업](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="b1eb8-112">기본 이동성 및 보안 장치 정책에서 사용자 보안 그룹 제거</span><span class="sxs-lookup"><span data-stu-id="b1eb8-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="b1eb8-113">브라우저에서 다음을 입력  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="b1eb8-114">장치 정책을 선택 하 고 **정책 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="b1eb8-115"> *\*배포**   페이지에서 *\*제거*\*를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="b1eb8-116">  \*\*그룹\*\*에서 보안 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="b1eb8-117"> *\*제거*\*를 선택 하 고 *\*저장*\*을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="b1eb8-118">기본 모바일 및 보안 장치 정책 제거</span><span class="sxs-lookup"><span data-stu-id="b1eb8-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="b1eb8-119">브라우저에서 다음을 입력  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="b1eb8-120">장치 정책을 선택 하 고  **정책 삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="b1eb8-121">경고 대화 상자에서 **예**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="b1eb8-122">조직 장치가 여전히 차단 상태인 경우 장치 차단을 해제 하는 방법에 대 한 자세한 내용은 [Office 365의 모바일 장치 관리에서 블로그 게시물 제거 액세스 제어](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1eb8-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
