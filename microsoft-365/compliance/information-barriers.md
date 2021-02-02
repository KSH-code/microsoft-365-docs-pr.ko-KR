---
title: Microsoft 365의 정보 장벽에 대해 자세히 알아보기
description: 정보 장벽을 사용하여 조직 내에서 Microsoft Teams를 사용하여 커뮤니케이션 규정 준수를 보장합니다.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 003347d46bed2529831a92681e73630d58a1f653
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071273"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="ea3c4-103">Microsoft 365의 정보 장벽에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="ea3c4-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="ea3c4-104">Microsoft 클라우드 서비스에는 강력한 통신 및 공동 작업 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="ea3c4-105">그러나 조직에서 이해 관계가 충돌하지 않도록 두 그룹 간의 통신 및 공동 작업을 제한하려는 경우를 가정해 가정해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="ea3c4-106">또는 내부 정보를 보호하기 위해 조직 내부의 특정 사용자 간의 통신 및 공동 작업을 제한하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="ea3c4-107">Microsoft 365를 사용하면 그룹 및 조직 전체에서 통신 및 공동 작업을 할 수 있으므로 필요한 경우 특정 사용자 그룹 간 통신 및 공동 작업을 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ea3c4-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="ea3c4-108">정보 장벽을 통해 할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="ea3c4-108">With information barriers, you can!</span></span>

<span data-ttu-id="ea3c4-109">Microsoft Teams, SharePoint Online 및 비즈니스용 OneDrive는 정보 장벽을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-109">Microsoft Teams, SharePoint Online, and OneDrive for Business support information barriers.</span></span> <span data-ttu-id="ea3c4-110">구독에 정보 [](#required-licenses-and-permissions) 장벽, 준수 관리자 또는 정보 장벽 관리자가 Microsoft Teams의 사용자 그룹 간의 통신을 허용하거나 차단하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator, or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="ea3c4-111">정보 장벽 정책은 다음 상황에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="ea3c4-112">일의 거래자 그룹 사용자는 마케팅 팀과 파일을 통신하거나 공유하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="ea3c4-113">기밀 회사 정보를 작업하는 재무 직원은 조직 내의 특정 그룹과 파일을 통신하거나 공유하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="ea3c4-114">거래 비밀 자료가 있는 내부 팀은 조직 내의 특정 그룹의 사용자와 온라인으로 전화를 걸거나 채팅하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="ea3c4-115">연구 팀이 제품 개발 팀과만 온라인으로 전화하거나 채팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-115">A research team should only call or chat online with a product development team</span></span>
- <span data-ttu-id="ea3c4-116">일 거래자 그룹을 위한 사이트는 해당 일자 거래자 그룹 외부의 모든 사람이 공유하거나 액세스하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-116">A site for day trader group should not be shared or accessed by anyone outside the day trader group</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea3c4-117">정보 장벽 \***는** _양방 제한만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-117">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="ea3c4-118">마케팅과 같은 한 가지 제한은 일 거래자들과 의사 소통하고 공동 작업을 할 수 있지만 매일 거래자는 마케팅 _\*으로 통신하고 공동 작업할 _수_ 없습니다 \*\*.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-118">One way restrictions, such as marketing can communicate and collaborate with day traders, but day traders cannot communicate and collaborate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="ea3c4-119">이러한 모든 예제 시나리오(및 그 이상)에 대해 Microsoft Teams, SharePoint Online 및 OneDrive에서 커뮤니케이션 및 공동 작업을 방지하거나 허용하도록 정보 장벽 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications and collaboration in Microsoft Teams, SharePoint Online and OneDrive.</span></span> <span data-ttu-id="ea3c4-120">이러한 정책은 사용자가 원치 않는 사용자와 통화하거나 채팅하는 것을 방지하거나, 사용자가 Microsoft Teams의 특정 그룹과만 통신할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="ea3c4-121">정보 장벽 정책이 적용된 경우 해당 정책이 적용된 사용자가 Microsoft Teams의 다른 사용자와 통신 및 공동 작업을 시도할 때마다 SharePoint Online 또는 OneDrive 검사가 수행되어 정보 장벽 정책에 의해 정의되는 커뮤니케이션 및 공동 작업을 방지(또는 허용)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate and collaborate with others in Microsoft Teams, SharePoint Online or OneDrive checks are done to prevent (or allow) communication and collaboration (as defined by information barrier policies).</span></span>

<span data-ttu-id="ea3c4-122">정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-122">To learn more about the user experience with information barriers, see:</span></span>

- [<span data-ttu-id="ea3c4-123">Microsoft Teams의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="ea3c4-123">Information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="ea3c4-124">SharePoint Online의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="ea3c4-124">Information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="ea3c4-125">OneDrive의 정보 장벽</span><span class="sxs-lookup"><span data-stu-id="ea3c4-125">Information barriers in OneDrive</span></span>](/onedrive/information-barriers)

> [!IMPORTANT]
> <span data-ttu-id="ea3c4-126">현재 정보 장벽은 전자 메일 통신에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-126">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="ea3c4-127">또한 정보 장벽은 규정 준수 [경계와 독립적입니다.](set-up-compliance-boundaries.md)</span><span class="sxs-lookup"><span data-stu-id="ea3c4-127">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p> <span data-ttu-id="ea3c4-128">정보 장벽 정책을 정의하고 적용하기 전에 조직에 [Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 주소부 정책이 적용되지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-128">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="ea3c4-129">(정보 장벽은 주소부 정책을 기반으로 합니다.)</span><span class="sxs-lookup"><span data-stu-id="ea3c4-129">(Information barriers are based on address book policies.)</span></span>

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="ea3c4-130">정보 장벽으로 발생하는 일</span><span class="sxs-lookup"><span data-stu-id="ea3c4-130">What happens with information barriers</span></span>

<span data-ttu-id="ea3c4-131">정보 장벽 정책이 적용된 경우 다른 특정 사용자와 파일을 통신하거나 공유하면 안되는 사용자는 해당 사용자를 찾고, 선택하거나, 채팅하거나, 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-131">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="ea3c4-132">정보 장벽으로 무단 통신 및 공동 작업을 방지하기 위한 검사가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-132">With information barriers, checks are in place to prevent unauthorized communication and collaboration.</span></span> 

<span data-ttu-id="ea3c4-133">정보 장벽은 Microsoft Teams(채팅 및 채널), SharePoint Online 및 OneDrive에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-133">Information barriers applies to Microsoft Teams (chats and channels), SharePoint Online and OneDrive.</span></span> <span data-ttu-id="ea3c4-134">Microsoft Teams에서 정보 장벽 정책은 다음과 같은 종류의 무단 통신을 결정하고 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-134">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="ea3c4-135">사용자 검색</span><span class="sxs-lookup"><span data-stu-id="ea3c4-135">Searching for a user</span></span>
- <span data-ttu-id="ea3c4-136">팀에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="ea3c4-136">Adding a member to a team</span></span>
- <span data-ttu-id="ea3c4-137">다른 사용자와 채팅 세션 시작</span><span class="sxs-lookup"><span data-stu-id="ea3c4-137">Starting a chat session with someone</span></span>
- <span data-ttu-id="ea3c4-138">그룹 채팅 시작</span><span class="sxs-lookup"><span data-stu-id="ea3c4-138">Starting a group chat</span></span>
- <span data-ttu-id="ea3c4-139">다른 사용자가 모임에 참가할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="ea3c4-139">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="ea3c4-140">화면 공유</span><span class="sxs-lookup"><span data-stu-id="ea3c4-140">Sharing a screen</span></span>
- <span data-ttu-id="ea3c4-141">전화 걸기</span><span class="sxs-lookup"><span data-stu-id="ea3c4-141">Placing a call</span></span>
- <span data-ttu-id="ea3c4-142">다른 사용자와 파일 공유</span><span class="sxs-lookup"><span data-stu-id="ea3c4-142">Sharing a file with another user</span></span>
- <span data-ttu-id="ea3c4-143">공유 링크를 통해 파일에 액세스</span><span class="sxs-lookup"><span data-stu-id="ea3c4-143">Access to file through sharing link</span></span>

<span data-ttu-id="ea3c4-144">관련 사용자가 활동을 방지하기 위해 정보 장벽 정책에 포함된 경우 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-144">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="ea3c4-145">또한 정보 장벽 정책에 포함된 모든 사람이 Microsoft Teams의 다른 사용자와의 통신을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-145">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="ea3c4-146">정보 장벽 정책의 영향을 받는 사람이 동일한 팀 또는 그룹 채팅에 참여하는 경우 해당 채팅 세션에서 제거되고 그룹과의 추가 통신이 허용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-146">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="ea3c4-147">정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 Microsoft Teams의 정보 장벽을 [참조하세요.](/MicrosoftTeams/information-barriers-in-teams)</span><span class="sxs-lookup"><span data-stu-id="ea3c4-147">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="ea3c4-148">SharePoint Online 및 OneDrive에서 정보 장벽 정책은 다음과 같은 종류의 권한이 없는 공동 작업을 결정하고 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-148">In SharePoint Online and OneDrive, information barrier policies determine and prevent the following kinds of unauthorized collaborations:</span></span>

- <span data-ttu-id="ea3c4-149">사이트에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="ea3c4-149">Adding a member to a site</span></span>
- <span data-ttu-id="ea3c4-150">사용자가 사이트 또는 콘텐츠 액세스</span><span class="sxs-lookup"><span data-stu-id="ea3c4-150">Accessing site or content by a user</span></span>
- <span data-ttu-id="ea3c4-151">다른 사용자와 사이트 또는 콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="ea3c4-151">Sharing site or content with another user</span></span>
- <span data-ttu-id="ea3c4-152">사이트 검색</span><span class="sxs-lookup"><span data-stu-id="ea3c4-152">Searching a site</span></span>

<span data-ttu-id="ea3c4-153">정보 장벽이 있는 사용자 경험에 대한 자세한 내용은 [SharePoint Online의](/sharepoint/information-barriers) 정보 장벽을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-153">To learn more about the user experience with information barriers, see [information barriers in SharePoint Online](/sharepoint/information-barriers)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ea3c4-154">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="ea3c4-154">Required licenses and permissions</span></span>

<span data-ttu-id="ea3c4-155">정보 장벽은 이제 출시 중으로, 다음과 같은 구독에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-155">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="ea3c4-156">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="ea3c4-156">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="ea3c4-157">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="ea3c4-157">Office 365 E5/A5</span></span>
- <span data-ttu-id="ea3c4-158">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="ea3c4-158">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="ea3c4-159">Microsoft 365 규정 준수 E5/A5</span><span class="sxs-lookup"><span data-stu-id="ea3c4-159">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="ea3c4-160">Microsoft 365 내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="ea3c4-160">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="ea3c4-161">자세한 내용은 보안 및 규정 준수에 대한 [Microsoft 365 & 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span><span class="sxs-lookup"><span data-stu-id="ea3c4-161">For more information, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="ea3c4-162">정보 장벽 정책을 정의하거나 [편집하려면](information-barriers-policies.md)다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-162">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="ea3c4-163">Microsoft 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ea3c4-163">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="ea3c4-164">Office 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="ea3c4-164">Office 365 global administrator</span></span>
- <span data-ttu-id="ea3c4-165">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="ea3c4-165">Compliance administrator</span></span>
- <span data-ttu-id="ea3c4-166">IB 준수 관리</span><span class="sxs-lookup"><span data-stu-id="ea3c4-166">IB Compliance Management</span></span>

<span data-ttu-id="ea3c4-167">(역할 및 사용 권한에 대한 자세한 내용은 [Office 365 보안](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)및 준수 센터의 사용 & 참조).</span><span class="sxs-lookup"><span data-stu-id="ea3c4-167">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="ea3c4-168">정보 장벽 정책을 정의, 유효성 검사 또는 편집하려면 PowerShell cmdlet에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-168">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="ea3c4-169">방법 문서에서 PowerShell cmdlet의 몇 [](information-barriers-policies.md)가지 예를 제공하겠지만, 조직에 대한 매개 변수와 같은 다른 세부 정보를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-169">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know other details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea3c4-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ea3c4-170">Next steps</span></span>

- [<span data-ttu-id="ea3c4-171">Microsoft Teams의 정보 장벽에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="ea3c4-171">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="ea3c4-172">SharePoint Online의 정보 장벽에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="ea3c4-172">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="ea3c4-173">OneDrive의 정보 장벽에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="ea3c4-173">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="ea3c4-174">정보 장벽 정책에 사용할 수 있는 특성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea3c4-174">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="ea3c4-175">정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="ea3c4-175">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="ea3c4-176">정보 장벽 정책 편집(또는 제거)</span><span class="sxs-lookup"><span data-stu-id="ea3c4-176">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)