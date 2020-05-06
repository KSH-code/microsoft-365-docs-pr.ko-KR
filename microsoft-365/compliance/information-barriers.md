---
title: 정보 장벽에 대해 자세히 알아보기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 정보 장애물을 사용 하 여 조직 내에서 Microsoft 팀을 사용 하 여 통신을 준수 하는지 확인 합니다.
ms.openlocfilehash: c4b4b31de90e8c72c346da5574b8854492de19ba
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048004"
---
# <a name="information-barriers"></a><span data-ttu-id="67d98-103">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="67d98-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="67d98-104">개요</span><span class="sxs-lookup"><span data-stu-id="67d98-104">Overview</span></span>

<span data-ttu-id="67d98-105">Microsoft 클라우드 서비스에는 강력한 통신 및 공동 작업 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="67d98-106">하지만 조직에서 발생할 수 있는 충돌을 방지 하기 위해 두 그룹 간의 통신을 제한 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="67d98-107">아니면 내부 정보를 보호 하기 위해 조직 내부의 특정 사용자 간의 통신을 제한 하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="67d98-108">Microsoft 365을 사용 하면 그룹 및 조직에서 통신 및 공동 작업을 수행할 수 있으므로 필요한 경우 특정 사용자 그룹 간에 통신을 제한할 수 있는 방법이 있나요?</span><span class="sxs-lookup"><span data-stu-id="67d98-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="67d98-109">정보 장벽에서는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-109">With information barriers, you can!</span></span> 

<span data-ttu-id="67d98-110">Microsoft 팀부터 정보 장애물을 즉시 롤아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="67d98-111">[구독](#required-licenses-and-permissions) 에 정보 장애가 포함 된 경우 규정 준수 관리자 또는 정보 장벽 관리자는 Microsoft 팀의 사용자 그룹 간 통신을 허용 하거나 차단 하는 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="67d98-112">정보 장벽 정책은 다음과 같은 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="67d98-113">일일 상인 그룹의 사용자는 마케팅 팀과 의견을 교환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="67d98-114">기밀 회사 정보에 대 한 작업을 수행 하는 금융 직원은 조직 내의 특정 그룹과 통신 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="67d98-115">무역 박람회가 포함 된 내부 팀에서 조직 내의 특정 그룹에 있는 사용자와 통화 하거나 온라인으로 채팅 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="67d98-116">연구 팀은 제품 개발 팀과 온라인 으로만 전화 하거나 채팅을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67d98-117">정보 장벽에서는 두 가지 제한 ***만 지원*** 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="67d98-118">마케팅과 같은 단방향 제한은 하루 상인과 통신할 수 있지만,이 경우에 ***는 상인이***marketing과 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="67d98-119">이러한 모든 시나리오 (및 이상)에서 정보 장벽 정책은 Microsoft 팀의 통신을 방지 하거나 허용 하도록 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="67d98-120">이러한 정책을 사용 하면 사용자가 전화를 걸 수도 있고 채팅을 할 수 없거나, 사용자가 Microsoft 팀의 특정 그룹과 통신 하는 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="67d98-121">정보 장벽 정책을 적용 하면 해당 정책에 포함 된 사용자가 Microsoft 팀의 다른 사람들과 통신을 시도할 때마다 정보 장벽 정책에 정의 된 대로 통신을 방지 하거나 허용 하기 위해 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="67d98-122">정보 장벽에 대 한 사용자 환경에 대 한 자세한 내용은 [Microsoft 팀의 정보 장벽](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67d98-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67d98-123">현재 정보 장애물은 SharePoint Online 또는 OneDrive를 통한 전자 메일 통신 또는 파일 공유에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="67d98-124">또한 정보 장애물은 [준수 경계](set-up-compliance-boundaries.md)와는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="67d98-125">정보 장벽 정책을 정의 하 고 적용 하기 전에 조직에 [Exchange 주소록 정책이](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 적용 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="67d98-126">정보 장애물은 주소록 정책에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="67d98-127">정보 장벽에 따라 수행 되는 작업</span><span class="sxs-lookup"><span data-stu-id="67d98-127">What happens with information barriers</span></span>

<span data-ttu-id="67d98-128">정보 장벽 정책이 적용 되 면 다른 특정 사용자와 통신 하지 않아야 하는 사용자는 해당 사용자를 찾거나, 선택 하거나, 채팅 하거나, 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="67d98-129">정보 장벽에서는 확인이 수행 되어 무단 통신을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="67d98-130">초기 정보 장애물은 Microsoft 팀 채팅 및 채널만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="67d98-131">Microsoft 팀에서 정보 장벽 정책은 다음과 같은 종류의 무단 통신을 결정 하 고 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="67d98-132">사용자 검색</span><span class="sxs-lookup"><span data-stu-id="67d98-132">Searching for a user</span></span>
- <span data-ttu-id="67d98-133">팀에 구성원 추가</span><span class="sxs-lookup"><span data-stu-id="67d98-133">Adding a member to a team</span></span>
- <span data-ttu-id="67d98-134">다른 사용자와의 채팅 세션 시작</span><span class="sxs-lookup"><span data-stu-id="67d98-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="67d98-135">그룹 채팅 시작</span><span class="sxs-lookup"><span data-stu-id="67d98-135">Starting a group chat</span></span>
- <span data-ttu-id="67d98-136">다른 사용자에 게 모임 참가 초대</span><span class="sxs-lookup"><span data-stu-id="67d98-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="67d98-137">화면 공유</span><span class="sxs-lookup"><span data-stu-id="67d98-137">Sharing a screen</span></span>
- <span data-ttu-id="67d98-138">전화 걸기</span><span class="sxs-lookup"><span data-stu-id="67d98-138">Placing a call</span></span> 

<span data-ttu-id="67d98-139">활동을 방지 하기 위해 관련 된 사용자가 정보 장벽 정책에 포함 된 경우에는 작업을 계속할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="67d98-140">또한 정보 장벽 정책에 포함 된 모든 사용자는 Microsoft 팀에서 다른 사람들과의 통신을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="67d98-141">정보 장벽 정책의 영향을 받는 사용자가 같은 팀 또는 그룹 채팅에 속해 있으면 해당 채팅 세션에서 제거 될 수 있으며, 그룹에 대 한 추가 통신을 허용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="67d98-142">정보 장벽에 대 한 사용자 환경에 대 한 자세한 내용은 [Microsoft 팀의 정보 장벽](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67d98-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="67d98-143">필수 라이선스 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="67d98-143">Required licenses and permissions</span></span>

<span data-ttu-id="67d98-144">정보 장애물은 지금 롤아웃 되며 다음과 같은 구독에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="67d98-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="67d98-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="67d98-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="67d98-146">Office 365 E5</span></span>
- <span data-ttu-id="67d98-147">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="67d98-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="67d98-148">Microsoft 365 E5 Information Protection 및 Compliance</span><span class="sxs-lookup"><span data-stu-id="67d98-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="67d98-149">자세한 내용은 [준수 솔루션](https://products.office.com/business/security-and-compliance/compliance-solutions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d98-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="67d98-150">[정보 장벽 정책을 정의 하거나 편집](information-barriers-policies.md)하려면 다음 역할 중 하나를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="67d98-151">Microsoft 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="67d98-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="67d98-152">Office 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="67d98-152">Office 365 global administrator</span></span>
- <span data-ttu-id="67d98-153">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="67d98-153">Compliance administrator</span></span>
- <span data-ttu-id="67d98-154">IB 준수 관리 (새 역할입니다.)</span><span class="sxs-lookup"><span data-stu-id="67d98-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="67d98-155">역할 및 사용 권한에 대 한 자세한 내용은 [Office 365 보안 & 준수 센터의 사용 권한을](../security/office-365-security/protect-against-threats.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67d98-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="67d98-156">정보 장벽 정책을 정의, 유효성 검사 또는 편집 하려면 PowerShell cmdlet을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="67d98-157">[방법 문서에는](information-barriers-policies.md)여러 PowerShell cmdlet 예제가 제공 되지만, 조직에 대 한 매개 변수 등의 추가 정보를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d98-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="67d98-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="67d98-158">Next steps</span></span>

- [<span data-ttu-id="67d98-159">Microsoft 팀의 정보 장벽에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="67d98-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="67d98-160">정보 장벽 정책에 사용할 수 있는 특성 확인</span><span class="sxs-lookup"><span data-stu-id="67d98-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="67d98-161">정보 장벽에 대 한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="67d98-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="67d98-162">정보 장벽 정책 편집 또는 제거</span><span class="sxs-lookup"><span data-stu-id="67d98-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 