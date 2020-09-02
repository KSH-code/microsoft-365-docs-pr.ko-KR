---
title: 표준 또는 대상 지정 된 릴리스 옵션 설정
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
description: Microsoft 365 관리 센터에서 새 제품 및 기능 업데이트에 대 한 릴리스 옵션을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 110cefa646f7c42c6979a97ca617b015a100866e
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324539"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="11001-103">표준 또는 대상 지정 된 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="11001-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="11001-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-104">The admin center is changing.</span></span> <span data-ttu-id="11001-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11001-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="11001-106">이 문서에서 설명 하는 Microsoft 365 업데이트는 Microsoft 365, SharePoint Online 및 Exchange Online에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11001-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="11001-107">이러한 릴리스 옵션은 Microsoft 365에 대 한 변경 사항을 릴리스할 수 있는 최상의 방법 이지만 항상 또는 모든 업데이트에 대해 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="11001-108">Microsoft 365 앱, 비즈니스용 Skype, Microsoft 팀 및 관련 서비스에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="11001-109">Microsoft 365 앱의 릴리스 옵션에 대 한 자세한 내용은 [microsoft 365 앱에 대 한 업데이트 채널 개요](https://docs.microsoft.com/deployoffice/overview-update-channels)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11001-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="11001-110">Microsoft 365에서는 몇 년 마다 비용이 많이 드는 업데이트를 수행 하는 대신 새로운 제품 업데이트 및 기능을 사용할 수 있을 때 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="11001-111">관리자는 조직에서 이러한 업데이트를 받는 방법을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="11001-112">예를 들어, 조직에서 먼저 업데이트를 받도록 초기 릴리스에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="11001-113">특정 개인만 업데이트를 받도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="11001-114">또는 기본 릴리스 일정을 유지하고 나중에 업데이트를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="11001-115">이 문서에서는 다양 한 릴리스 옵션과 조직에서 이러한 옵션을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="11001-116">방법 - 릴리스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="11001-116">How it works - release validation</span></span>

<span data-ttu-id="11001-117">모든 새 릴리스는 먼저 기능 팀에서 테스트 하 고 유효성을 검사 한 다음 전체 Microsoft 365 기능 팀, 모든 Microsoft에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11001-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="11001-118">내부 테스트 및 유효성 검사 후 다음 단계는 선택한 고객에게 **대상 지정된 릴리스**(이전의 첫 번째 릴리스)입니다.</span><span class="sxs-lookup"><span data-stu-id="11001-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="11001-119">각 릴리스 링에서 Microsoft는 주요 사용 메트릭을 모니터링하여 피드백을 수집하고 품질을 더 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="11001-120">이러한 일련의 점진적인 유효성 검사는 전 세계 릴리스가 가능한 한 견고하도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11001-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="11001-121">릴리스는 다음 그림과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-121">The releases are pictured in the following figure.</span></span> 
  
![Microsoft 365에 대 한 릴리스 유효성 검사 링](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="11001-123">중요 업데이트의 경우 처음에는 [Microsoft 365 로드맵](https://products.office.com/business/office-365-roadmap)에서 고객에 게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11001-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="11001-124">업데이트가 롤아웃에 더 가까이 있으면 [Microsoft 365 메시지 센터](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11001-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="11001-125">[관리 센터](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)를 통해 메시지 센터에 액세스 하려면 Microsoft 365 또는 Azure AD 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="11001-126">Microsoft 365 home 요금제 사용자에 게 관리 센터는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="11001-127">표준 릴리스</span><span class="sxs-lookup"><span data-stu-id="11001-127">Standard release</span></span>

<span data-ttu-id="11001-128">모든 고객에 게 광범위 하 게 출시 될 때 최신 업데이트를 받는 기본 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="11001-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="11001-129">가장 좋은 방법은 대부분의 사용자를 **표준 릴리스** 및 IT 전문가로 지정 하 고 **대상 릴리스의** 고급 사용자에 게 새 기능을 평가 하 고 비즈니스 사용자 및 임원을 지원 하도록 팀을 준비 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11001-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="11001-130">대상 지정된 릴리스에서 표준 릴리스 트랙으로 전환하면 사용자들이 아직 표준 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="11001-131">대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="11001-131">Targeted release</span></span>

<span data-ttu-id="11001-p107">이 옵션을 사용하면 관리자 및 사용자들이 최신 업데이트를 최초로 볼 수 있고 사전에 의견을 제공하여 제품 제작을 지원할 수 있습니다. 개인이나 전체 조직이 조기에 업데이트를 받도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="11001-p108">크거나 복잡한 업데이트는 누구도 부정적인 영향을 받지 않도록 하기 위해 다른 업데이트보다 시간이 오래 걸릴 수 있습니다. 릴리스의 정확한 일정은 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="11001-136">전체 조직에 대해 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="11001-136">Targeted release for entire organization</span></span>

<span data-ttu-id="11001-137">이 옵션에 대 한 [관리 센터에서 릴리스 옵션을 설정](#set-up-the-release-option-in-the-admin-center) 하면 모든 사용자가 대상 지정 된 릴리스 환경을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11001-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="11001-138">사용자가 300명 이상인 조직의 경우 이 옵션에 대한 테스트 구독을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="11001-139">테스트 구독 정보는 Microsoft 담당자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="11001-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="11001-140">선택한 사용자에 대한 대상 지정된 릴리스</span><span class="sxs-lookup"><span data-stu-id="11001-140">Targeted release for selected users</span></span>

<span data-ttu-id="11001-141">이 옵션에 대해 [관리 센터에서 릴리스 옵션을 설정 하는](#set-up-the-release-option-in-the-admin-center) 경우 일반적으로 고급 사용자 인 특정 사용자를 정의 하 여 기능에 대 한 초기 액세스를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="11001-142">대상 지정된 릴리스의 이점</span><span class="sxs-lookup"><span data-stu-id="11001-142">Benefits of Targeted release</span></span>

<span data-ttu-id="11001-143">대상 지정 된 릴리스를 사용 하면 관리자, 변경 관리자 또는 Microsoft 365 업데이트를 담당 하는 모든 사용자가 다음 변경 내용을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="11001-144">새 업데이트가 조직의 모든 사용자에게 릴리스되기 전에 테스트하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="11001-145">업데이트가 전 세계에 릴리스되기 전에 사용자 알림 및 설명서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="11001-146">향후 변경 사항에 대해 내부 지원 센터를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="11001-147">준수 및 보안 검토를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="11001-148">해당하는 경우 기능 제어를 사용하여 최종 사용자에 대한 업데이트 릴리스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="11001-149">관리 센터에서 릴리스 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="11001-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="11001-150">다음 단계를 수행 하 여 조직에서 Microsoft 365 업데이트를 받는 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="11001-151">옵트인 하려면 Microsoft 365의 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="11001-152">아래의 변경 내용이 Microsoft 365에 적용 되려면 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="11001-153">대상 지정된 릴리스를 설정한 후에 취소하는 경우 사용자가 아직 예정된 릴리스에 도달하지 않은 기능에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11001-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="11001-154">관리 센터에서 조직 설정 설정으로 이동 **Settings**  >  **Org Setting**하 고 **조직의 프로필** 탭에서 **기본 설정 릴리스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="11001-155">대상 지정 된 릴리스를 사용 하지 않도록 설정 하려면 **표준 릴리스**를 선택 하 고 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="11001-156">조직의 모든 사용자에 대해 대상 지정 된 릴리스를 사용 하도록 설정 하려면 **모든 사람에 대해 대상**지정 된 릴리스를 선택한 다음 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="11001-157">조직의 일부 사용자에 대해 대상 지정 된 릴리스를 사용 하도록 설정 하려면 **선택한 사용자에 대해 대상**지정 된 릴리스를 선택한 다음 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="11001-158">사용자를 한 번에 하나씩 추가 하려면 사용자 **선택을** 선택 하 고, 대량으로 추가 하려면 사용자를 **업로드** 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="11001-159">사용자 추가가 완료 되 면 **변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11001-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="11001-160">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="11001-160">Learn more</span></span>

<span data-ttu-id="11001-161">[Microsoft 365 메시지 센터](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) 에서 [메시지를 관리](https://docs.microsoft.com/office365/admin/manage/message-center) 하 여 예정 된 Microsoft 365 업데이트 및 릴리스에 대 한 알림을 받는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="11001-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
