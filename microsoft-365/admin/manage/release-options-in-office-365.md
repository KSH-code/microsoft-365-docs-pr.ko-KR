---
title: 표준 또는 대상 지정 릴리스 옵션 설정
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Microsoft 365 관리 센터에서 새 제품 및 기능 업데이트에 대한 릴리스 옵션을 설정하는 방법을 학습합니다.
ms.openlocfilehash: 6c5d505f0ece47b0a47df8b7ed1dc015afe93e82
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470574"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="3bc63-103">표준 또는 대상 지정 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="3bc63-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bc63-104">이 문서에 설명된 Microsoft 365 업데이트는 Microsoft 365, SharePoint Online 및 Exchange Online에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="3bc63-105">이러한 릴리스 옵션은 Microsoft 365에 대한 변경 내용을 릴리스하는 가장 좋은 방법인 대상이지만, 어떤 경우나 모든 업데이트에 대해 보장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="3bc63-106">Microsoft 365 앱, 비즈니스용 Skype, Microsoft Teams 및 관련 서비스에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="3bc63-107">Microsoft 365 앱의 릴리스 옵션에 대한 자세한 내용은 Microsoft 365 앱 업데이트 채널 [개요를 참조하세요.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="3bc63-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="3bc63-108">Microsoft 365를 사용하면 몇 년마다 비용이 많이 드는 업데이트를 수행하지 않고 새로운 제품 업데이트 및 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="3bc63-109">관리자는 조직에서 이러한 업데이트를 받는 방법을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="3bc63-110">예를 들어, 조직에서 먼저 업데이트를 받도록 초기 릴리스에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="3bc63-111">특정 개인만 업데이트를 받도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="3bc63-112">또는 기본 릴리스 일정을 유지하고 나중에 업데이트를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="3bc63-113">이 문서에서는 다양한 릴리스 옵션과 조직에 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="3bc63-114">방법 - 릴리스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="3bc63-114">How it works - release validation</span></span>

<span data-ttu-id="3bc63-115">모든 새 릴리스는 먼저 기능 팀에서 테스트하고 유효성을 검사한 다음 전체 Microsoft 365 기능 팀이 유효성을 검사한 다음 모든 Microsoft가 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="3bc63-116">내부 테스트 및 유효성 검사 후 다음 단계는 선택한 고객에게 **대상 지정된 릴리스**(이전의 첫 번째 릴리스)입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="3bc63-117">각 릴리스 링에서 Microsoft는 주요 사용 메트릭을 모니터링하여 피드백을 수집하고 품질을 더 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="3bc63-118">이러한 일련의 점진적인 유효성 검사는 전 세계 릴리스가 가능한 한 견고하도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="3bc63-119">릴리스는 다음 그림과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-119">The releases are pictured in the following figure.</span></span> 
  
![Microsoft 365용 릴리스 유효성 검사 링](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="3bc63-121">중요한 업데이트의 경우 처음에 Microsoft [365 로드맵에 의해 고객에게 통보됩니다.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="3bc63-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="3bc63-122">업데이트가 배포될수록 [Microsoft 365 메시지 센터를 통해 전달됩니다.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="3bc63-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="3bc63-123">관리 센터를 통해 메시지 센터에 액세스하려면 Microsoft 365 또는 Azure AD [계정이 필요합니다.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="3bc63-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="3bc63-124">Microsoft 365 Home 요금제 사용자에게는 관리 센터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="3bc63-125">표준 릴리스</span><span class="sxs-lookup"><span data-stu-id="3bc63-125">Standard release</span></span>

<span data-ttu-id="3bc63-126">이는 사용자와 사용자가 모든 고객에게 광범위하게 릴리스될 때 최신 업데이트를 받는 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="3bc63-127">대부분의 사용자를 **표준** 릴리스에 그대로 두고, IT Pros 및  Power Users를 대상 지정 릴리스에 두어 새로운 기능을 평가하고 팀이 비즈니스 사용자 및 임원을 지원할 수 있도록 준비하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3bc63-128">대상 지정된 릴리스에서 표준 릴리스 트랙으로 전환하면 사용자들이 아직 표준 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="3bc63-129">대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="3bc63-129">Targeted release</span></span>

<span data-ttu-id="3bc63-p106">이 옵션을 사용하면 관리자 및 사용자들이 최신 업데이트를 최초로 볼 수 있고 사전에 의견을 제공하여 제품 제작을 지원할 수 있습니다. 개인이나 전체 조직이 조기에 업데이트를 받도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3bc63-p107">크거나 복잡한 업데이트는 누구도 부정적인 영향을 받지 않도록 하기 위해 다른 업데이트보다 시간이 오래 걸릴 수 있습니다. 릴리스의 정확한 일정은 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="3bc63-134">전체 조직에 대해 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="3bc63-134">Targeted release for entire organization</span></span>

<span data-ttu-id="3bc63-135">이 [옵션에 대한](#set-up-the-release-option-in-the-admin-center) 관리 센터에서 릴리스 옵션을 설정하면 모든 사용자에게 대상 지정 릴리스 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="3bc63-136">사용자가 300명 이상인 조직의 경우 이 옵션에 대한 테스트 구독을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="3bc63-137">테스트 구독 정보는 Microsoft 담당자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="3bc63-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="3bc63-138">선택한 사용자에 대한 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="3bc63-138">Targeted release for selected users</span></span>

<span data-ttu-id="3bc63-139">이 [옵션에 대한](#set-up-the-release-option-in-the-admin-center) 관리 센터에서 릴리스 옵션을 설정한 경우 특정 사용자(일반적으로 파워 사용자)를 정의하여 기능 및 기능에 대한 조기 액세스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="3bc63-140">대상 지정된 릴리스의 이점</span><span class="sxs-lookup"><span data-stu-id="3bc63-140">Benefits of Targeted release</span></span>

<span data-ttu-id="3bc63-141">대상이 지정한 릴리스에서는 관리자, 변경 관리자 또는 Microsoft 365 업데이트를 담당하는 모든 사용자가 다음을 허용하여 예정된 변경을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="3bc63-142">새 업데이트가 조직의 모든 사용자에게 릴리스되기 전에 테스트하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="3bc63-143">업데이트가 전 세계에 릴리스되기 전에 사용자 알림 및 설명서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="3bc63-144">향후 변경 사항에 대해 내부 지원 센터를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="3bc63-145">준수 및 보안 검토를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="3bc63-146">해당하는 경우 기능 제어를 사용하여 최종 사용자에 대한 업데이트 릴리스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="3bc63-147">관리 센터에서 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="3bc63-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="3bc63-148">다음 단계에 따라 조직에서 Microsoft 365 업데이트를 받는 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="3bc63-149">옵트인하려면 Microsoft 365에서 전역 관리자 를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3bc63-150">아래 변경 내용이 Microsoft 365에 적용될 경우 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="3bc63-151">대상 지정된 릴리스를 설정한 후에 취소하는 경우 사용자가 아직 예정된 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="3bc63-152">관리 센터에서 설정 조직 설정으로 이동하고 조직 프로필 탭에서  >  릴리스 기본 설정 **을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="3bc63-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="3bc63-153">대상 지정 릴리스를 사용하지 않도록 설정하려면 **표준** 릴리스 를 선택한 다음 변경 **내용 저장 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bc63-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="3bc63-154">조직의 모든 사용자에 대해 대상이 지정된 릴리스를 사용하도록 설정하려면 모든 사용자에 대해 대상 지정 릴리스를 선택한 다음 변경 내용 저장 **을 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="3bc63-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="3bc63-155">조직의 일부 사용자에 대해 대상 지정 릴리스를 사용하도록 설정하려면 선택한 사용자에 대해 대상 지정 릴리스를 선택한 다음 변경 내용 저장 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bc63-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="3bc63-156">사용자를 **한** 번씩 추가하려면 사용자 선택을 선택하거나, 사용자를 대량으로 **추가하려면** 사용자 업로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3bc63-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="3bc63-157">사용자 추가가 완료되면 변경 **내용 저장 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3bc63-157">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="3bc63-158">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="3bc63-158">Learn more</span></span>

<span data-ttu-id="3bc63-159">[Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) 메시지 센터에서 메시지를 관리하여 예정된 Microsoft 365 업데이트 및 릴리스에 대한 알림을 다운로드하는 방법을 확인합니다. [](/office365/admin/manage/message-center)</span><span class="sxs-lookup"><span data-stu-id="3bc63-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3bc63-160">관련 문서</span><span class="sxs-lookup"><span data-stu-id="3bc63-160">Related Articles</span></span>

[<span data-ttu-id="3bc63-161">Office 참가자</span><span class="sxs-lookup"><span data-stu-id="3bc63-161">Office Insider</span></span>](https://insider.office.com/join/windows)
