---
title: 사례 연구-Contoso는 Microsoft 팀 및 Exchange 통신에 대 한 비속어 (공격적인 언어 정책)를 빠르게 구성 합니다.
description: Contoso에 대 한 사례 연구 및 Microsoft 팀 및 Exchange Online 통신에서 비속어를 모니터링 하기 위한 통신 준수 정책을 신속 하 게 구성 하는 방법
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4a119e0ec082893d393d1b43af76b41dc93c76a1
ms.sourcegitcommit: 144c0f3c2c6112bffc5a9b04392a38123a979ebc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053075"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-and-exchange-communications"></a><span data-ttu-id="00935-103">사례 연구-Contoso는 Microsoft 팀 및 Exchange 통신에 대 한 비속어 (공격적인 언어 정책)를 빠르게 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-103">Case study - Contoso quickly configures an offensive language policy for Microsoft Teams and Exchange communications</span></span>

<span data-ttu-id="00935-104">Microsoft 365의 통신 준수 기능은 조직의 부적절 한 메시지에 대 한 검색, 캡처 및 수정 작업 수행을 지원 하 여 통신 위험을 최소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-104">Communication compliance in Microsoft 365 helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="00935-105">미리 정의 된 정책 및 사용자 지정 정책을 사용 하면 정책 일치에 대 한 내부 및 외부 통신을 검색 하 여 지정한 검토자가 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-105">Pre-defined and custom policies allow you to scan internal and external communications for policy matches so they can be examined by designated reviewers.</span></span> <span data-ttu-id="00935-106">검토자는 조직에서 검사 된 전자 메일, Microsoft 팀 또는 타사 통신을 조사 하 고 적절 한 교정 작업을 수행 하 여 조직의 메시지 표준을 준수 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-106">Reviewers can investigate scanned email, Microsoft Teams, or third-party communications in your organization and take appropriate remediation actions to make sure they're compliant with your organization's message standards.</span></span>

<span data-ttu-id="00935-107">Contoso Corporation은 공격적인 언어를 모니터링 하도록 정책을 빠르게 구성 해야 하는 가상 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-107">The Contoso Corporation is a fictional organization that needs to quickly configure a policy to monitor for offensive language.</span></span> <span data-ttu-id="00935-108">Microsoft 365은 주로 전자 메일 및 Microsoft 팀의 직원을 지원 하기 위해 사용 되었지만 작업 공간 harassment에 회사 정책을 적용 하기 위한 새로운 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-108">They have been using Microsoft 365 primarily for email and Microsoft Teams support for their employees but have new requirements to enforce company policy around workplace harassment.</span></span> <span data-ttu-id="00935-109">Contoso IT 관리자 및 준수 전문가는 Microsoft 365의 기본 작업에 대 한 기본적인 지식을 이해 하 고 있으며, 통신 준수를 빠르게 시작 하는 방법에 대 한 종단 간 지침을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-109">Contoso IT administrators and compliance specialists have a basic understanding of the fundamentals of working with Microsoft 365 and are looking for end-to-end guidance for how to quickly get started with communication compliance.</span></span>

<span data-ttu-id="00935-110">이 사례 연구에서는 악의적인 언어에 대 한 통신을 모니터링 하기 위한 통신 준수 정책을 빠르게 구성 하는 기본 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="00935-110">This case study will cover the basics for quickly configuring a communication compliance policy to monitor communications for offensive language.</span></span> <span data-ttu-id="00935-111">이 지침에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-111">This guidance includes:</span></span>

- <span data-ttu-id="00935-112">1 단계-통신 준수 계획</span><span class="sxs-lookup"><span data-stu-id="00935-112">Step 1 - Planning for communication compliance</span></span>
- <span data-ttu-id="00935-113">2 단계-Microsoft 365의 통신 준수에 액세스</span><span class="sxs-lookup"><span data-stu-id="00935-113">Step 2 - Accessing communication compliance in Microsoft 365</span></span>
- <span data-ttu-id="00935-114">3 단계-필수 구성 요소 구성 및 통신 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="00935-114">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>
- <span data-ttu-id="00935-115">4 단계-알림 조사 및 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="00935-115">Step 4 - Investigation and remediation of alerts</span></span>

## <a name="step-1---planning-for-communication-compliance"></a><span data-ttu-id="00935-116">1 단계-통신 준수 계획</span><span class="sxs-lookup"><span data-stu-id="00935-116">Step 1 - Planning for communication compliance</span></span>

<span data-ttu-id="00935-117">Contoso IT administrators 및 준수 전문가는 Microsoft 365의 규정 준수 솔루션에 대 한 온라인 웹 세미나, 통신 준수 정책을 통해 작업 공간을 줄이기 위해 업데이트 된 회사 정책 요구 사항을 충족 하는 데 도움을 줍니다. harassment.</span><span class="sxs-lookup"><span data-stu-id="00935-117">Contoso IT administrators and compliance specialists attended online webinars about compliance solutions in Microsoft 365 and decided that communication compliance policies will help them meet the updated corporate policy requirements for reducing workplace harassment.</span></span> <span data-ttu-id="00935-118">공동 작업 Exchange Online으로 전송 된 전자 메일 메시지에서 Microsoft 팀으로 전송 되는 채팅에 대 한 악의적인 언어를 모니터링 하는 통신 준수 정책을 만들고 사용 하도록 설정 하는 계획을 개발 했습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-118">Working together, they've developed a plan to create and enable a communication compliance policy that will monitor for offensive language for chats sent in Microsoft Teams in email messages sent in Exchange Online.</span></span> <span data-ttu-id="00935-119">계획에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-119">Their plan includes identifying:</span></span>

- <span data-ttu-id="00935-120">통신 준수 기능에 액세스 해야 하는 IT 관리자</span><span class="sxs-lookup"><span data-stu-id="00935-120">The IT administrators that need access to communication compliance features.</span></span>
- <span data-ttu-id="00935-121">통신 정책을 만들고 관리 해야 하는 준수 전문가</span><span class="sxs-lookup"><span data-stu-id="00935-121">The compliance specialists that need to create and manage communication policies.</span></span>
- <span data-ttu-id="00935-122">준수 전문가 및 기타 부서의 기타 부서 (인적 자원, 법률 등)에서 통신 준수 알림을 조사 하 고 수정 해야 하는 기타 동료입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-122">The compliance specialists and other colleague in other departments (Human Resources, Legal, etc.) that need to investigate and remediate communication compliance alerts.</span></span>
- <span data-ttu-id="00935-123">통신 준수 공격적인 언어 정책에 대 한 범위 내에 속하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-123">The users that will be in-scope for the communication compliance offensive language policy.</span></span>

### <a name="licensing"></a><span data-ttu-id="00935-124">라이선싱</span><span class="sxs-lookup"><span data-stu-id="00935-124">Licensing</span></span>

<span data-ttu-id="00935-125">첫 번째 단계는 Contoso의 Microsoft 365 라이선스에 통신 준수 솔루션에 대 한 지원이 포함 되어 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-125">The first step is to confirm that Contoso's Microsoft 365 licensing includes support for the communication compliance solution.</span></span> <span data-ttu-id="00935-126">통신 준수를 액세스 하 고 사용 하려면 Contoso IT 관리자는 Contoso에 다음 중 하나가 포함 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-126">To access and use communication compliance, Contoso IT administrators need to verify that Contoso has one of the following:</span></span>

- <span data-ttu-id="00935-127">Microsoft 365 E5 구독 (유료 또는 평가판 버전)</span><span class="sxs-lookup"><span data-stu-id="00935-127">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="00935-128">고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스</span><span class="sxs-lookup"><span data-stu-id="00935-128">Office 365 Enterprise E3 license with the Advanced Compliance add-on</span></span>
- <span data-ttu-id="00935-129">Office 365 Enterprise E5 구독 (유료 또는 평가판 버전)</span><span class="sxs-lookup"><span data-stu-id="00935-129">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>

<span data-ttu-id="00935-130">또한 통신 준수 정책에 포함 된 사용자에 게 위에 나열 된 라이선스 중 하나를 할당 해야 한다는 것을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-130">They must also confirm that users included in communication compliance policies must be assigned to one of the licenses listed above.</span></span>

<span data-ttu-id="00935-131">Contoso IT 관리자는 다음 단계를 수행 하 여 Contoso에 대 한 라이선스 지원을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-131">Contoso IT administrators take the following steps to verify the licensing support for Contoso:</span></span>

1. <span data-ttu-id="00935-132">IT 관리자가 **microsoft 365 관리 센터** [https://admin.microsoft.com) ](https://admin.microsoft.com) 에 로그인 하 고 **microsoft 365 관리 센터** > **청구** > **라이선스로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-132">IT administrators sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Billing** > **Licenses**.</span></span>

2. <span data-ttu-id="00935-133">여기서는 통신 준수에 대 한 지원을 포함 하는 [라이선스 옵션](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) 중 하나가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-133">Here they confirm that they have one of the [license options](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) that includes support for communication compliance.</span></span>

![통신 준수 라이선스](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a><span data-ttu-id="00935-135">통신 준수에 대 한 사용 권한</span><span class="sxs-lookup"><span data-stu-id="00935-135">Permissions for communication compliance</span></span>

<span data-ttu-id="00935-136">기본적으로 전역 관리자는 통신 준수 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-136">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="00935-137">Contoso IT 관리자 및 준수 전문가가 통신 준수에 액세스할 수 있도록 [사용 권한을 구성 해야 합니다](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) .</span><span class="sxs-lookup"><span data-stu-id="00935-137">[Permissions must be configured](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#step-1-required-enable-permissions-for-communication-compliance) so that Contoso IT administrators and compliance specialists have access to communication compliance.</span></span>

1. <span data-ttu-id="00935-138">Contoso IT 관리자는 **office 365 보안 및 준수 센터** 사용 권한 페이지 (전역 관리자 계정의 자격 증명을 사용 하 여 [)https://protection.office.com/permissions) ](https://protection.office.com/permissions) 에 로그인 하 고 office 365에서 역할을 보고 관리 하는 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-138">Contoso IT administrators sign into the **Office 365 Security and Compliance center** permissions page [(https://protection.office.com/permissions)](https://protection.office.com/permissions) using credentials for a global administrator account and select the link to view and manage roles in Office 365.</span></span>
2. <span data-ttu-id="00935-139">Create ( **만들기**)를 선택 하면 새 역할 그룹에 "*통신 준수*" 라는 이름이 지정 되 고 **Next (다음**)가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-139">After selecting **Create**, they give the new role group a friendly name of "*Communication compliance*" and select **Next**.</span></span>
3. <span data-ttu-id="00935-140">**역할 선택을** 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-140">They select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="00935-141">*관리 검토 관리자*, *사례 관리*, *준수 관리자*및 *검토*에 대 한 확인란을 선택 하 여 필요한 역할을 추가한 후에 **추가**, **완료,** **다음**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-141">They add the required roles by selecting the checkbox for *Supervisory Review Administrator*, *Case Management*, *Compliance Administrator*, and *Review*, then they select **Add**, **Done,** and **Next**.</span></span>

![통신 준수 역할](../media/communication-compliance-case-roles.png)

4. <span data-ttu-id="00935-143">다음으로, IT 관리자가 **구성원 선택** 을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-143">Next, the IT administrators select **Choose members** then select **Add**.</span></span> <span data-ttu-id="00935-144">정책을 만들고 정책과 일치 하는 메시지를 관리할 모든 사용자 및 그룹의 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-144">The select the checkbox for all the users and groups that they want to create policies and manage messages with policy matches.</span></span> <span data-ttu-id="00935-145">IT 관리자, 규정 준수 전문가 및 다른 동료를 초기 계획에서 식별 한 법률 부서에 추가 하 고 **추가**, **완료**, **다음**을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-145">They add the IT administrators, compliance specialists, and other colleagues in Human Resources and Legal departments that they identified in the initial planning, then select **Add**, **Done**, and **Next**.</span></span>
5. <span data-ttu-id="00935-146">IT 관리자는 사용 권한을 마무리 하 여 마칠 **역할 그룹 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-146">To finalize the permissions, the IT administrators select **Create role group** to finish.</span></span> <span data-ttu-id="00935-147">Contoso의 Microsoft 365 서비스에서 역할이 효과적일 때까지 약 30 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-147">It will take about 30 minutes for the roles to be effective in Contoso's Microsoft 365 service.</span></span>

![통신 준수 검토](../media/communication-compliance-case-review.png)

## <a name="step-2---accessing-communication-compliance-in-microsoft-365"></a><span data-ttu-id="00935-149">2 단계-Microsoft 365의 통신 준수에 액세스</span><span class="sxs-lookup"><span data-stu-id="00935-149">Step 2 - Accessing communication compliance in Microsoft 365</span></span>

<span data-ttu-id="00935-150">통신 준수에 대 한 사용 권한을 구성 하 고 나면 새 역할 그룹에 정의 된 Contoso IT 관리자 및 준수 전문가가 Microsoft 365의 통신 준수 솔루션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-150">After configuring the permissions for communication compliance, Contoso IT administrators and compliance specialists defined in the new role group can access the communication compliance solution in Microsoft 365.</span></span> <span data-ttu-id="00935-151">Contoso IT 관리자 및 준수 전문가는 통신 준수에 액세스 하 고 새 정책 만들기를 시작할 수 있는 몇 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-151">Contoso IT administrators and compliance specialists have several ways to access communication compliance and get started creating a new policy:</span></span>

- <span data-ttu-id="00935-152">통신 준수 솔루션에서 직접 시작</span><span class="sxs-lookup"><span data-stu-id="00935-152">Starting directly from the communication compliance solution</span></span>
- <span data-ttu-id="00935-153">Microsoft 365 준수 센터에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-153">Starting from the Microsoft 365 compliance center</span></span>
- <span data-ttu-id="00935-154">Microsoft 365 솔루션 카탈로그에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-154">Starting from the Microsoft 365 solution catalog</span></span>
- <span data-ttu-id="00935-155">Microsoft 365 관리 센터에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-155">Starting from the Microsoft 365 admin center</span></span>

### <a name="starting-directly-from-the-communication-compliance-solution"></a><span data-ttu-id="00935-156">통신 준수 솔루션에서 직접 시작</span><span class="sxs-lookup"><span data-stu-id="00935-156">Starting directly from the communication compliance solution</span></span>

<span data-ttu-id="00935-157">솔루션에 액세스 하는 가장 빠른 방법은 **Communication 준수** (<https://compliance.microsoft.com/supervisoryreview>) 솔루션에 직접 로그인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-157">The quickest way to access the solution is to sign in directly to the **Communication compliance** (<https://compliance.microsoft.com/supervisoryreview>) solution.</span></span> <span data-ttu-id="00935-158">이 링크를 사용 하 여 Contoso IT 관리자 및 준수 전문가는 알림 상태를 빠르게 검토 하 고 미리 정의 된 템플릿에서 새 정책을 만들 수 있는 통신 준수 개요 대시보드로 향합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-158">Using this link, Contoso IT administrators and compliance specialists will be directed to the communication compliance Overview dashboard where you can quickly review the status of alerts and create new policies from the pre-defined templates.</span></span>

![통신 준수 개요](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a><span data-ttu-id="00935-160">Microsoft 365 준수 센터에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-160">Starting from the Microsoft 365 compliance center</span></span>

<span data-ttu-id="00935-161">Contoso IT 관리자 및 준수 전문가가 통신 준수 솔루션에 액세스 하는 또 다른 쉬운 방법은 **Microsoft 365 준수 센터** [()https://compliance.microsoft.com)](https://compliance.microsoft.com)에 직접 로그인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-161">Another easy way for Contoso IT administrators and compliance specialists to access the communication compliance solution is to sign in directly to the **Microsoft 365 compliance center** [(https://compliance.microsoft.com)](https://compliance.microsoft.com).</span></span> <span data-ttu-id="00935-162">로그인 한 후에는 모든 준수 솔루션을 표시 하려면 **모두 표시** 컨트롤을 선택 하 고 시작 하려면 **통신 준수** 솔루션을 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-162">After signing in, users simply need to select the **Show all** control to display all the compliance solutions and then select the **Communication compliance** solution to get started.</span></span>

![준수 센터](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a><span data-ttu-id="00935-164">Microsoft 365 솔루션 카탈로그에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-164">Starting from the Microsoft 365 solution catalog</span></span>

<span data-ttu-id="00935-165">Contoso IT 관리자 및 규정 준수 전문가는 Microsoft 365 솔루션 카탈로그를 선택 하 여 통신 준수 솔루션에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-165">Contoso IT administrators and compliance specialists could also choose to access the communication compliance solution by selecting the Microsoft 365 solution catalog.</span></span> <span data-ttu-id="00935-166">**Microsoft 365 준수 센터**에서 왼쪽 탐색 창의 **솔루션** 섹션에서 **카탈로그** 를 선택 하면 모든 microsoft 365 준수 솔루션을 나열 하는 솔루션 카탈로그를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-166">By selecting **Catalog** in **Solutions** section of the left navigation while in the **Microsoft 365 compliance center**, they can open the solution catalog listing all Microsoft 365 compliance solutions.</span></span> <span data-ttu-id="00935-167">Contoso IT 관리자는 **참가자 위험 관리** 섹션으로 스크롤한 후 시작 하기 위한 통신 준수를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-167">Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started.</span></span> <span data-ttu-id="00935-168">또한 Contoso IT 관리자는 탐색에 표시 기능을 사용 하 여 통신 준수 솔루션을 왼쪽 탐색 창에 고정 하 여 향후 로그인 할 때 빠르게 액세스할 수 있도록 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-168">Contoso IT administrators also decide to use the Show in navigation control to pin the communication compliance solution to the left-navigation pane for quicker access when they sign in going forward.</span></span>

![솔루션 카탈로그](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a><span data-ttu-id="00935-170">Microsoft 365 관리 센터에서 시작</span><span class="sxs-lookup"><span data-stu-id="00935-170">Starting from the Microsoft 365 admin center</span></span>

<span data-ttu-id="00935-171">Microsoft 365 [관리 센터에서https://admin.microsoft.com) ](https://admin.microsoft.com) 시작할 때의 통신 준수에 액세스 하려면 Contoso IT 관리자 및 준수 전문가가 microsoft 365 관리 센터에 로그인 하 고 **microsoft 365 관리 센터** > **규정 준수**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-171">To access communication compliance when starting from the Microsoft 365 admin center, Contoso IT administrators and compliance specialists sign in to the Microsoft 365 admin center [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Compliance**.</span></span>

![통신 준수 링크](../media/communication-compliance-case-compliance-link.png)

<span data-ttu-id="00935-173">이렇게 하면 **Office 365 보안 및 준수 센터가**열리고 페이지 맨 위에 있는 배너에 제공 된 **Microsoft 365 준수 센터** 에 대 한 링크를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-173">This opens the **Office 365 Security and Compliance center**, and they must select the link to the **Microsoft 365 compliance center** provided in the banner at the top of the page.</span></span>

![Office 365 보안 및 준수 센터](../media/communication-compliance-case-scc.png)

<span data-ttu-id="00935-175">**Microsoft 365 준수 센터**에서 Contoso IT 관리자는 **모두 표시** 를 선택 하 여 준수 솔루션의 전체 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-175">Once in the **Microsoft 365 compliance center**, Contoso IT administrators select **Show all** to display the full list of compliance solutions.</span></span>

![통신 준수 메뉴](../media/communication-compliance-case-show-all.png)

<span data-ttu-id="00935-177">**모두 표시**를 선택한 후에는 Contoso IT 관리자가 통신 준수 솔루션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-177">After selecting **Show all**, the Contoso IT administrators can access the communication compliance solution.</span></span>

![통신 준수 개요](../media/communication-compliance-case-overview.png)

## <a name="step-3---configuring-prerequisites-and-creating-a-communication-compliance-policy"></a><span data-ttu-id="00935-179">3 단계-필수 구성 요소 구성 및 통신 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="00935-179">Step 3 - Configuring prerequisites and creating a communication compliance policy</span></span>

<span data-ttu-id="00935-180">통신 준수 정책을 시작 하려면 Contoso IT 관리자가 공격적인 언어를 모니터링 하기 위해 새 정책을 설정 하기 전에 구성 해야 하는 몇 가지 필수 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-180">To get started with a communication compliance policy, there are several prerequisites that Contoso IT administrators need to configure before setting up the new policy to monitor for offensive language.</span></span> <span data-ttu-id="00935-181">이러한 필수 구성 요소가 완료 되 면 Contoso IT 관리자 및 준수 전문가가 새 정책을 구성 하 고, 규정 준수 전문가는 조사를 시작 하 고 생성 된 모든 경고를 수정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-181">After these prerequisites have been completed, Contoso IT administrators and compliance specialists can configure the new policy and compliance specialists can start investigation and remediating any generated alerts.</span></span>

### <a name="enabling-auditing-in-office-365"></a><span data-ttu-id="00935-182">Office 365에서 감사 사용</span><span class="sxs-lookup"><span data-stu-id="00935-182">Enabling auditing in Office 365</span></span>

<span data-ttu-id="00935-183">통신 준수를 위해서는 감사 로그가 알림을 표시 하 고 검토자가 수행한 업데이트 관리 작업을 추적 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="00935-184">감사 로그는 정의 된 조직 정책과 관련 된 모든 활동을 요약 한 것 이거나, 통신 준수 정책이 변경 된 경우에도 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime there is a change to a communication compliance policy.</span></span>

<span data-ttu-id="00935-185">Contoso IT 관리자는 감사를 설정 하는 단계별 [지침](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) 을 검토 하 고 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-185">Contoso IT administrators review and complete the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) to turn on auditing.</span></span> <span data-ttu-id="00935-186">감사를 설정한 후에는 감사 로그를 준비 중 이며 준비 완료 후 몇 시간 내에 검색을 실행할 수 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-186">After they turn on auditing, a message is displayed that says the audit log is being prepared and that they can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="00935-187">Contoso IT 관리자는이 작업을 한 번만 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-187">The Contoso IT administrators only have to do this action once.</span></span>

### <a name="setting-up-a-group-for-in-scope-users"></a><span data-ttu-id="00935-188">범위 내 사용자에 대 한 그룹 설정</span><span class="sxs-lookup"><span data-stu-id="00935-188">Setting up a group for in-scope users</span></span>

<span data-ttu-id="00935-189">Contoso 준수 전문가가 공격적인 언어를 모니터링할 통신 정책에 모든 직원을 추가 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-189">Contoso compliance specialists want to add all employee to the communication policy that will monitor for offensive language.</span></span> <span data-ttu-id="00935-190">각 직원 사용자 계정을 개별적으로 정책에 추가할지 결정 했지만,이를 통해 더 쉽게 작업할 수 있도록 결정 했으며이 정책에 대 한 사용자의 **모든 직원** 메일 그룹을 사용 하는 데 많은 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="00935-190">They could decide to add each employee user account to the policy separately, but they've decided it is much easier and saves a lot of time to use an **All Employees** distribution group for the users for this policy.</span></span>

<span data-ttu-id="00935-191">모든 Contoso 직원을 포함 하기 위해 새 그룹을 만들어야 하는 경우 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-191">They need to create a new group to include all Contoso employees, so they take the following steps:</span></span>

1. <span data-ttu-id="00935-192">Contoso it 관리자는 **microsoft 365 관리 센터** [https://admin.microsoft.com) ](https://admin.microsoft.com) 에 로그인 하 고 **microsoft 365 관리 센터** > **그룹** > **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-192">Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [(https://admin.microsoft.com)](https://admin.microsoft.com) and navigate to **Microsoft 365 admin center** > **Groups** > **Groups**.</span></span>
2. <span data-ttu-id="00935-193">**그룹 추가** 를 선택 하 고 마법사를 완료 하 여 새 *Office 365 그룹* 또는 *메일 그룹*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00935-193">They select **Add a group** and complete the wizard to create a new *Office 365 group* or *Distribution group*.</span></span>

![그룹](../media/communication-compliance-case-all-employees.png)

3. <span data-ttu-id="00935-195">새 그룹을 만든 후에는 모든 Contoso 사용자를 새 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-195">After the new group is created, they need to add all Contoso users to the new group.</span></span> <span data-ttu-id="00935-196">**Exchange 관리 센터** [https://outlook.office365.com/ecp) 를 열고](https://outlook.office365.com/ecp) **exchange 관리 센터** > **받는 사람** > **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-196">They open the **Exchange admin center** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) and navigate to **Exchange admin center** > **recipients** > **groups**.</span></span> <span data-ttu-id="00935-197">Contoso IT 관리자는 구성원 영역 및 새로 만든 *모든 직원* 그룹을 선택 하 고 **편집** 컨트롤을 선택 하 여 마법사에서 새 그룹에 모든 Contoso 직원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-197">The Contoso IT administrators select the Membership area and the new *All Employees* group they created and select the **Edit** control to add all Contoso employees to the new group in the wizard.</span></span>

![Exchange 관리 센터](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a><span data-ttu-id="00935-199">공격적인 언어에 대해 모니터링할 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="00935-199">Creating the policy to monitor for offensive language</span></span>

<span data-ttu-id="00935-200">모든 필수 구성 요소가 완료 되 면 IT 관리자와 Contoso 규정 준수 전문가가 공격적인 언어를 모니터링 하도록 통신 준수 정책을 구성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00935-200">With all the prerequisites completed, the IT administrators and the compliance specialists for Contoso are ready to configure the communication compliance policy to monitor for offensive language.</span></span> <span data-ttu-id="00935-201">새로운 공격적인 언어 정책 템플릿을 사용 하 여이 정책을 구성 하는 것은 간단 하 고 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-201">Using the new offensive language policy template, configuring this policy is simple and quick.</span></span>

1. <span data-ttu-id="00935-202">Contoso IT 관리자 및 준수 전문가가 **Microsoft 365 준수 센터** 에 로그인 하 고 왼쪽 탐색 창에서 **통신 준수** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-202">The Contoso IT administrators and compliance specialists sign into the **Microsoft 365 compliance center** and select **Communication compliance** from the left navigation pane.</span></span> <span data-ttu-id="00935-203">이 작업을 수행 하면 통신 준수 정책 서식 파일에 대 한 빠른 링크가 있는 **개요** 대시보드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="00935-203">This action opens the **Overview** dashboard that has quick links for communication compliance policy templates.</span></span> <span data-ttu-id="00935-204">서식 파일에 대해 **시작** 을 선택 하 여 **공격적인 언어 서식 파일에 대 한 모니터** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-204">They choose the **Monitor for offensive language** template by selecting **Get started** for the template.</span></span>

![공격에 적합 한 통신 준수 언어 서식 파일](../media/communication-compliance-case-template.png)

2. <span data-ttu-id="00935-206">정책 서식 파일 마법사에서 Contoso IT 관리자 및 준수 전문가가 공동 작업을 통해 **정책 이름**, **사용자 또는 그룹 감독할**및 **검토자**의 세 가지 필수 필드를 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-206">On the policy template wizard, the Contoso IT administrators and compliance specialists work together to complete the three required fields: **Policy name**, **Users or groups to supervise**, and **Reviewers**.</span></span>
3. <span data-ttu-id="00935-207">정책 마법사에서 정책 이름을 이미 제안 했으므로 IT 관리자 및 준수 전문가가 제안 된 이름을 유지 하 고 나머지 필드에 포커스를 둡니다.</span><span class="sxs-lookup"><span data-stu-id="00935-207">Since the policy wizard has already suggested a name for the policy, the IT administrators and compliance specialists decide to keep the suggested name and focus on the remaining fields.</span></span> <span data-ttu-id="00935-208">**감독할 사용자 또는 그룹** 에 대 한 *모든 직원* 그룹을 선택 하 고 **검토자** 필드에 대 한 정책 알림을 조사 및 수정 해야 하는 준수 전문가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-208">They select the *All employees* group for the **Users or groups to supervise** field and select the compliance specialists that should investigate and remediate policy alerts for the **Reviewers** field.</span></span> <span data-ttu-id="00935-209">정책을 구성 하 고 경고 정보 수집을 시작 하는 마지막 단계는 **정책 만들기**를 선택 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-209">The last step to configure the policy and start gathering alert information is to select **Create policy**.</span></span>

![원하지 않는 통신 준수 언어 마법사](../media/communication-compliance-case-wizard.png)

## <a name="step-4--investigate-and-remediate-alerts"></a><span data-ttu-id="00935-211">4 단계-알림 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="00935-211">Step 4 – Investigate and remediate alerts</span></span>

<span data-ttu-id="00935-212">이제 공격적인 언어를 모니터링 하기 위한 통신 준수 정책이 구성 되었으므로 Contoso 준수 전문가의 다음 단계는 정책에 의해 생성 된 경고를 조사 하 고 수정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00935-212">Now that the communication compliance policy to monitor for offensive language is configured, the next step for the Contoso compliance specialists will be to investigate and remediate any alerts generated by the policy.</span></span> <span data-ttu-id="00935-213">정책이 모든 통신 원본 채널의 통신을 완벽 하 게 처리 하 고 경고 **대시보드에**경고가 표시 되는 데 최대 24 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00935-213">It will take up to 24 hours for the policy to fully process communications in all the communication source channels and for alerts to show up in the **Alert dashboard**.</span></span>

<span data-ttu-id="00935-214">경고가 생성 되 면 Contoso 준수 전문가가 [워크플로 지침](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) 에 따라 공격적인 언어 문제를 조사 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00935-214">After alerts are generated, Contoso compliance specialists will follow the [workflow instructions](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) to investigate and remediate offensive language issues.</span></span>
