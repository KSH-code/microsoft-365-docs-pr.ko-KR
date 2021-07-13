---
title: 표준 또는 대상 지정 릴리스 옵션 설정
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 새 제품 및 기능 업데이트에 대한 릴리스 옵션을 설정하는 방법을 Microsoft 365 관리 센터.
ms.openlocfilehash: ba9c3a71807728e18b612f0b63aff80d04a46a90
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392530"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="5d467-103">표준 또는 대상 지정 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="5d467-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d467-104">이 Microsoft 365 설명하는 업데이트는 Microsoft 365, SharePoint Online 및 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5d467-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="5d467-105">이러한 릴리스 옵션은 대상이 지정되어 있는 최상의 방법으로 Microsoft 365 변경 내용을 릴리스하는 가장 좋은 방법이지만 모든 업데이트에 대해 보장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="5d467-106">이러한 서비스는 Microsoft 365 앱, 비즈니스용 Skype, Microsoft Teams 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="5d467-107">에 대한 릴리스 옵션에 대한 Microsoft 365 앱 에 대한 업데이트 채널 [개요를 Microsoft 365 앱.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="5d467-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="5d467-108">이 Microsoft 365 사용하면 몇 년마다 비용이 많이 드는 업데이트를 수행하지 않고 사용할 수 있는 새로운 제품 업데이트 및 기능을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="5d467-109">관리자는 조직에서 이러한 업데이트를 받는 방법을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="5d467-110">예를 들어, 조직에서 먼저 업데이트를 받도록 초기 릴리스에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="5d467-111">특정 개인만 업데이트를 받도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="5d467-112">또는 기본 릴리스 일정을 유지하고 나중에 업데이트를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="5d467-113">이 문서에서는 다양한 릴리스 옵션과 조직에 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="5d467-114">방법 - 릴리스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5d467-114">How it works - release validation</span></span>

<span data-ttu-id="5d467-115">모든 새 릴리스는 먼저 기능 팀에서 테스트하고 유효성을 검사한 다음 전체 Microsoft 365 기능 팀이 테스트한 다음 모든 Microsoft가 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="5d467-116">내부 테스트 및 유효성 검사 후 다음 단계는 선택한 고객에게 **대상 지정된 릴리스**(이전의 첫 번째 릴리스)입니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="5d467-117">각 릴리스 링에서 Microsoft는 주요 사용 메트릭을 모니터링하여 피드백을 수집하고 품질을 더 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="5d467-118">이러한 일련의 점진적인 유효성 검사는 전 세계 릴리스가 가능한 한 견고하도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="5d467-119">릴리스는 다음 그림과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-119">The releases are pictured in the following figure.</span></span> 
  
![사용자에 대한 유효성 검사 Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="5d467-121">중요한 업데이트의 경우 초기에는 2016년 8월 1일 [로드맵을 통해 Microsoft 365 합니다.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="5d467-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="5d467-122">업데이트가 롤아웃에 가까워지고 나면 업데이트가 메시지 센터 를 [통해 Microsoft 365 전달됩니다.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="5d467-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="5d467-123">관리 센터를 Microsoft 365 액세스하려면 관리자 또는 Azure AD [계정이 필요합니다.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="5d467-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="5d467-124">Microsoft 365 요금제 사용자에게 관리 센터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="5d467-125">표준 릴리스</span><span class="sxs-lookup"><span data-stu-id="5d467-125">Standard release</span></span>

<span data-ttu-id="5d467-126">이는 사용자와 사용자가 모든 고객에게 광범위하게 릴리스될 때 최신 업데이트를 받는 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="5d467-127">대부분의 사용자를 **표준** 릴리스에 그대로 두고, IT Pros 및  Power Users를 대상 지정 릴리스에 두어 새로운 기능을 평가하고 팀이 비즈니스 사용자 및 임원을 지원할 수 있도록 준비하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5d467-128">대상 지정된 릴리스에서 표준 릴리스 트랙으로 전환하면 사용자들이 아직 표준 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="5d467-129">대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="5d467-129">Targeted release</span></span>

<span data-ttu-id="5d467-p106">이 옵션을 사용하면 관리자 및 사용자들이 최신 업데이트를 최초로 볼 수 있고 사전에 의견을 제공하여 제품 제작을 지원할 수 있습니다. 개인이나 전체 조직이 조기에 업데이트를 받도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d467-p107">크거나 복잡한 업데이트는 누구도 부정적인 영향을 받지 않도록 하기 위해 다른 업데이트보다 시간이 오래 걸릴 수 있습니다. 릴리스의 정확한 일정은 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="5d467-134">전체 조직에 대해 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="5d467-134">Targeted release for entire organization</span></span>

<span data-ttu-id="5d467-135">이 [옵션에 대한](#set-up-the-release-option-in-the-admin-center) 관리 센터에서 릴리스 옵션을 설정하면 모든 사용자에게 대상 지정 릴리스 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="5d467-136">사용자가 300명 이상인 조직의 경우 이 옵션에 대한 테스트 구독을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="5d467-137">테스트 구독 정보는 Microsoft 담당자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="5d467-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="5d467-138">선택한 사용자에 대한 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="5d467-138">Targeted release for selected users</span></span>

<span data-ttu-id="5d467-139">이 [옵션에 대한](#set-up-the-release-option-in-the-admin-center) 관리 센터에서 릴리스 옵션을 설정한 경우 특정 사용자(일반적으로 파워 사용자)를 정의하여 기능 및 기능에 대한 조기 액세스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="5d467-140">대상 지정된 릴리스의 이점</span><span class="sxs-lookup"><span data-stu-id="5d467-140">Benefits of Targeted release</span></span>

<span data-ttu-id="5d467-141">대상이 지정한 릴리스에서는 관리자, 변경 관리자 또는 Microsoft 365 업데이트를 담당하는 모든 사용자가 다음을 허용하여 예정된 변경을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="5d467-142">새 업데이트가 조직의 모든 사용자에게 릴리스되기 전에 테스트하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="5d467-143">업데이트가 전 세계에 릴리스되기 전에 사용자 알림 및 설명서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="5d467-144">향후 변경 사항에 대해 내부 지원 센터를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="5d467-145">준수 및 보안 검토를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="5d467-146">해당하는 경우 기능 제어를 사용하여 최종 사용자에 대한 업데이트 릴리스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="5d467-147">관리 센터에서 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="5d467-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="5d467-148">다음 단계를 수행하여 조직에서 업데이트 Microsoft 365 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="5d467-149">옵트인하려면 옵트인(opt in)에서 전역 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5d467-150">아래 변경 내용을 적용하는 데 최대 24시간이 걸릴 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d467-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="5d467-151">대상 지정된 릴리스를 설정한 후에 취소하는 경우 사용자가 아직 예정된 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="5d467-152">관리 센터에서 조직 **설정** 로 이동하고 조직 프로필 탭에서 릴리스 기본 설정  >   **을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="5d467-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="5d467-153">대상 지정 릴리스를 사용하지 않도록 설정하려면 **표준** 릴리스 를 선택한 다음 변경 **내용 저장 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d467-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="5d467-154">조직의 모든 사용자에 대해 대상이 지정된 릴리스를 사용하도록 설정하려면 모든 사용자에 대해 대상 지정 릴리스를 선택한 다음 변경 내용 저장 **을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="5d467-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="5d467-155">조직의 일부 사용자에 대해 대상 지정 릴리스를 사용하도록 설정하려면 선택한 사용자에 대해 대상 지정 릴리스를 선택한 다음 변경 내용 저장 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d467-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="5d467-156">사용자를 **한에** 하나씩 추가하려면 사용자 선택을 선택하거나, 업로드 **대량으로** 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d467-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="5d467-157">사용자 추가가 완료되면 변경 **내용 저장 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d467-157">When you're done adding users, select **Save changes**.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="5d467-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5d467-158">Next steps</span></span>

<span data-ttu-id="5d467-159">예정된 [](/office365/admin/manage/message-center) 업데이트 및 릴리스에 대한 알림을 Microsoft 365 메시지 센터에서 메시지를 관리하는 Microsoft 365 방법을 확인합니다. [](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="5d467-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-content"></a><span data-ttu-id="5d467-160">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5d467-160">Related content</span></span>

<span data-ttu-id="5d467-161">[Office 프로그램](https://insider.office.com/join/windows) 참가(문서)</span><span class="sxs-lookup"><span data-stu-id="5d467-161">[Join the Office Insider Program](https://insider.office.com/join/windows) (article)</span></span>
