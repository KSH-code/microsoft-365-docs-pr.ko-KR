---
title: 정보 장벽 문제 해결
description: 이 문서를 정보 장벽 문제 해결을 위한 가이드로 사용하세요.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126565"
---
# <a name="troubleshooting-information-barriers"></a><span data-ttu-id="c1a35-103">정보 장벽 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c1a35-103">Troubleshooting information barriers</span></span>

<span data-ttu-id="c1a35-104">[정보 장벽은](information-barriers.md) 조직이 법적 요구 사항 및 산업 규정을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-104">[Information barriers](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="c1a35-105">예를 들어 정보 장벽이 있는 경우 이해 상충이나 기타 문제를 방지하기 위해 특정 사용자 그룹 간의 통신을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="c1a35-106">정보 장벽을 설정하는 방법에 대한 자세한 내용은 정보 장벽에 대한 정책 [정의를](information-barriers-policies.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1a35-106">(To learn more about how to set up information barriers, see [Define policies for information barriers](information-barriers-policies.md).)</span></span>

<span data-ttu-id="c1a35-107">정보 장벽이 발생하면 예기치 않은 문제가 발생할 경우 몇 가지 단계를 수행하여 이러한 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="c1a35-108">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a35-108">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1a35-109">이 문서에 설명된 작업을 수행하려면 다음 중 하나와 같은 적절한 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="c1a35-110">- Microsoft 365 Enterprise Global Administrator</span><span class="sxs-lookup"><span data-stu-id="c1a35-110">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="c1a35-111">- 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="c1a35-111">- global administrator</span></span><br/><span data-ttu-id="c1a35-112">- 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="c1a35-112">- Compliance Administrator</span></span><br/><span data-ttu-id="c1a35-113">- IB 규정 준수 관리(새 역할입니다!)</span><span class="sxs-lookup"><span data-stu-id="c1a35-113">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="c1a35-114">정보 장벽의 선행 준비에 대한 자세한 내용은 사전 준비(정보 장벽 정책의 경우)를 [참조하세요.](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="c1a35-114">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="c1a35-115">Security & [준수 센터 PowerShell에 연결해야 합니다.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="c1a35-115">Make sure to [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a><span data-ttu-id="c1a35-116">문제: 사용자가 Microsoft Teams의 다른 사용자와 예기치 않게 통신하지 못하게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-116">Issue: Users are unexpectedly blocked from communicating with others in Microsoft Teams</span></span> 

<span data-ttu-id="c1a35-117">이 경우 Microsoft Teams의 다른 사용자와 통신하는 예기치 않은 문제가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-117">In this case, people are reporting unexpected issues communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="c1a35-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-118">Some examples are:</span></span>

- <span data-ttu-id="c1a35-119">사용자가 Microsoft Teams에서 다른 사용자를 검색하지만 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-119">A user searches for, but is unable to find, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="c1a35-120">사용자는 Microsoft Teams에서 다른 사용자를 찾을 수 있지만 선택할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-120">A user can find, but cannot select, another user in Microsoft Teams.</span></span>
- <span data-ttu-id="c1a35-121">사용자는 다른 사용자를 볼 수 있지만 Microsoft Teams의 다른 사용자에게 메시지를 보낼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-121">A user can see another user, but cannot send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-122">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-122">What to do</span></span>

<span data-ttu-id="c1a35-123">사용자가 정보 장벽 정책의 영향을 받는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-123">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="c1a35-124">정책 구성 방법에 따라 정보 장벽이 예상대로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-124">Depending on how policies are configured, information barriers might be working as expected.</span></span> <span data-ttu-id="c1a35-125">또는 조직의 정책을 구체화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-125">Or, you might have to refine your organization's policies.</span></span>

1. <span data-ttu-id="c1a35-126">Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-126">Use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="c1a35-127">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-127">**Syntax**</span></span>|<span data-ttu-id="c1a35-128">**예**</span><span class="sxs-lookup"><span data-stu-id="c1a35-128">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> <span data-ttu-id="c1a35-129">이름, 별칭, DN(고유 이름), 정식 DN, 전자 메일 주소 또는 GUID와 같이 각 받는 사람을 고유하게 식별하는 모든 ID 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-129">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> <span data-ttu-id="c1a35-130">이 예제에서는 Identity 매개 변수에 *별칭(meganb)을* 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-130">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="c1a35-131">이 cmdlet은 사용자가 정보 장벽 정책의 영향을 받는지 여부를 나타내는 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-131">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="c1a35-132">(\*ExoPolicyId: \<GUID> .)</span><span class="sxs-lookup"><span data-stu-id="c1a35-132">(Look for \*ExoPolicyId: \<GUID>.)</span></span> |

    <span data-ttu-id="c1a35-133">사용자가 정보 장벽 정책에 포함되지 않은 경우 **고객 지원에 문의하세요.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-133">**If the users are not included in information barrier policies, contact support**.</span></span> <span data-ttu-id="c1a35-134">그렇지 않은 경우 다음 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-134">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="c1a35-135">정보 장벽 정책에 포함되는 세그먼트를 찾아 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a35-135">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="c1a35-136">이 작업을 위해 Identity 매개 변수와 `Get-InformationBarrierPolicy` 함께 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-136">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> 

    |<span data-ttu-id="c1a35-137">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-137">**Syntax**</span></span>|<span data-ttu-id="c1a35-138">**예**</span><span class="sxs-lookup"><span data-stu-id="c1a35-138">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> <span data-ttu-id="c1a35-139">이전 단계에서 받은 정책 GUID(ExoPolicyId)와 같은 세부 정보를 ID 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-139">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span> | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> <span data-ttu-id="c1a35-140">이 예에서는 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f가* 있는 정보 장벽 정책에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-140">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span> |

    <span data-ttu-id="c1a35-141">cmdlet을 실행한 후 결과에서 **AssignedSegment,** **SegmentsAllowed** 및 **SegmentsBlocked 값을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-141">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="c1a35-142">예를 들어 cmdlet을 실행한 후 결과 목록에서 `Get-InformationBarrierPolicy` 다음을 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-142">For example, after running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    <span data-ttu-id="c1a35-143">이 경우 정보 장벽 정책이 판매 및 리서치 부문에 있는 사용자에 영향을 주는 것으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-143">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="c1a35-144">이 경우 Sales의 사용자가 리서치의 사용자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-144">In this case, people in Sales are prevented from communicating with people in Research.</span></span>

    <span data-ttu-id="c1a35-145">문제가 해결된 것 같은 경우 정보 장벽이 예상대로 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-145">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="c1a35-146">로그인하지 않은 경우에는 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-146">If not, proceed to the next step.</span></span>

3. <span data-ttu-id="c1a35-147">세그먼트가 올바르게 정의되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-147">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="c1a35-148">이 작업을 위해 `Get-OrganizationSegment` cmdlet을 사용하여 결과 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-148">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span>

    |<span data-ttu-id="c1a35-149">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-149">**Syntax**</span></span>|<span data-ttu-id="c1a35-150">**예**</span><span class="sxs-lookup"><span data-stu-id="c1a35-150">**Example**</span></span>|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> <span data-ttu-id="c1a35-151">이 cmdlet을 Identity 매개 변수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-151">Use this cmdlet with an Identity parameter.</span></span> | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> <span data-ttu-id="c1a35-152">이 예제에서는 *GUID가 c96e0837-c232-4a8a-841e-ef45787d8fcd인* 세그먼트에 대한 정보를 받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-152">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span> |

    <span data-ttu-id="c1a35-153">세그먼트에 대한 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-153">Review the details for the segment.</span></span> <span data-ttu-id="c1a35-154">필요한 경우 [세그먼트를 편집한](information-barriers-edit-segments-policies.md#edit-a-segment)다음 `Start-InformationBarrierPoliciesApplication` cmdlet을 다시 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c1a35-154">If necessary, [edit a segment](information-barriers-edit-segments-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="c1a35-155">정보 장벽 정책에 여전히 문제가 있는 경우 **고객 지원에 문의하세요.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-155">**If you are still having issues with your information barrier policy, contact support**.</span></span>

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="c1a35-156">문제: Microsoft Teams에서 차단해야 하는 사용자 간에 통신이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-156">Issue: Communications are allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="c1a35-157">이 경우 정보 장벽이 정의, 활성 및 적용되어도 서로 통신하지 못하게 해야 하는 사람은 Microsoft Teams에서 채팅하고 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-157">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other are somehow able to chat with and call each other in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-158">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-158">What to do</span></span>

<span data-ttu-id="c1a35-159">해당 사용자가 정보 장벽 정책에 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c1a35-159">Verify that the users in question are included in an information barrier policy.</span></span> 

1. <span data-ttu-id="c1a35-160">Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-160">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="c1a35-161">**구문** _</span><span class="sxs-lookup"><span data-stu-id="c1a35-161">**Syntax** _</span></span>|<span data-ttu-id="c1a35-162">_ *예제*\*</span><span class="sxs-lookup"><span data-stu-id="c1a35-162">_ *Example*\*</span></span>|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="c1a35-163">이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-163">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="c1a35-164">이 예에서는 Office 365의 두 사용자 계정인 *Meganb과* *Alex의 alexw를* *참조합니다.* </span><span class="sxs-lookup"><span data-stu-id="c1a35-164">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

    > [!TIP]
    > <span data-ttu-id="c1a35-165">단일 사용자에 대해 이 cmdlet을 사용할 수도 있습니다. `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="c1a35-165">You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`</span></span>

2. <span data-ttu-id="c1a35-166">결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-166">Review the findings.</span></span> <span data-ttu-id="c1a35-167">**Get-InformationBarrierRecipientStatus** cmdlet은 특성 값 및 적용되는 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-167">The **Get-InformationBarrierRecipientStatus** cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    <span data-ttu-id="c1a35-168">다음 표에 설명된 결과를 검토한 후 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-168">Review the results, and then take your next steps, as described in the following table:</span></span>

    |<span data-ttu-id="c1a35-169">**결과**</span><span class="sxs-lookup"><span data-stu-id="c1a35-169">**Results**</span></span>|<span data-ttu-id="c1a35-170">**다음에 할 일**</span><span class="sxs-lookup"><span data-stu-id="c1a35-170">**What to do next**</span></span>|
    |:----------|:------------------|
    | <span data-ttu-id="c1a35-171">선택한 사용자에 대한 세그먼트가 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-171">No segments are listed for the selected user(s)</span></span> | <span data-ttu-id="c1a35-172">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-172">Do one of the following:</span></span><br/><span data-ttu-id="c1a35-173">- Azure Active Directory에서 사용자 프로필을 편집하여 기존 세그먼트에 사용자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-173">- Assign users to an existing segment by editing their user profiles in Azure Active Directory.</span></span> <span data-ttu-id="c1a35-174">(Office [365 PowerShell을](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)사용하여 사용자 계정 속성 구성을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="c1a35-174">(See [Configure user account properties with Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).)</span></span><br/><span data-ttu-id="c1a35-175">- 정보 장벽에 대해 지원되는 특성을 [사용하여 세그먼트를 정의합니다.](information-barriers-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="c1a35-175">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md).</span></span> <span data-ttu-id="c1a35-176">그런 다음 새 정책을 [정의하거나](information-barriers-policies.md#part-2-define-information-barrier-policies) 해당 세그먼트를 포함하기 [위해](information-barriers-edit-segments-policies.md#edit-a-policy) 기존 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-176">Then, either [define a new policy](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit an existing policy](information-barriers-edit-segments-policies.md#edit-a-policy) to include that segment.</span></span> |
    | <span data-ttu-id="c1a35-177">세그먼트가 나열되지만 이러한 세그먼트에 정보 장벽 정책이 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-177">Segments are listed but no information barrier policies are assigned to those segments</span></span> | <span data-ttu-id="c1a35-178">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-178">Do one of the following:</span></span><br/><span data-ttu-id="c1a35-179">- [해당 세그먼트마다](information-barriers-policies.md#part-2-define-information-barrier-policies) 새로운 정보 장벽 정책 정의</span><span class="sxs-lookup"><span data-stu-id="c1a35-179">- [Define a new information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span> <br/><span data-ttu-id="c1a35-180">- [기존 정보 장벽](information-barriers-edit-segments-policies.md#edit-a-policy) 정책을 편집하여 올바른 세그먼트에 할당</span><span class="sxs-lookup"><span data-stu-id="c1a35-180">- [Edit an existing information barrier policy](information-barriers-edit-segments-policies.md#edit-a-policy) to assign it to the correct segment</span></span> |
    | <span data-ttu-id="c1a35-181">세그먼트가 나열되어 있으며 각 세그먼트는 정보 장벽 정책에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-181">Segments are listed and each is included in an information barrier policy</span></span> | <span data-ttu-id="c1a35-182">- `Get-InformationBarrierPolicy` cmdlet을 실행하여 정보 장벽 정책이 활성 상태인지 확인</span><span class="sxs-lookup"><span data-stu-id="c1a35-182">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="c1a35-183">- `Get-InformationBarrierPoliciesApplicationStatus` cmdlet을 실행하여 정책이 적용되는지 확인</span><span class="sxs-lookup"><span data-stu-id="c1a35-183">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="c1a35-184">- `Start-InformationBarrierPoliciesApplication` cmdlet을 실행하여 모든 활성 정보 장벽 정책 적용</span><span class="sxs-lookup"><span data-stu-id="c1a35-184">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span> |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a><span data-ttu-id="c1a35-185">문제: 정보 장벽 정책에서 단일 사용자를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-185">Issue: I need to remove a single user from an information barrier policy</span></span>

<span data-ttu-id="c1a35-186">이 경우 정보 장벽 정책이 적용 중일 때 한 개 이상의 사용자가 Microsoft Teams의 다른 사용자와 통신하지 못하게 예기치 않게 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-186">In this case, information barrier policies are in effect, and a one or more users are unexpectedly blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="c1a35-187">정보 장벽 정책을 모두 제거하는 대신 정보 장벽 정책에서 하나 이상의 개별 사용자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-187">Rather than remove information barrier policies altogether, you can remove one or more individual users from information barrier policies.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-188">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-188">What to do</span></span>

<span data-ttu-id="c1a35-189">정보 장벽 정책은 사용자 세그먼트에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-189">Information barrier policies are assigned to segments of users.</span></span> <span data-ttu-id="c1a35-190">세그먼트는 사용자 계정 프로필에서 특정 특성을 사용하여 [정의됩니다.](information-barriers-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="c1a35-190">Segments are defined by using certain [attributes in user account profiles](information-barriers-attributes.md).</span></span> <span data-ttu-id="c1a35-191">단일 사용자에서 정책을 제거해야 하는 경우 사용자가 정보 장벽의 영향을 받는 세그먼트에 더 이상 포함되지 못하도록 Azure Active Directory에서 해당 사용자의 프로필을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-191">If you must remove a policy from a single user, consider editing that user's profile in Azure Active Directory such that the user is no longer included in a segment affected by information barriers.</span></span>

1. <span data-ttu-id="c1a35-192">Identity 매개 변수와 함께 **Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-192">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <span data-ttu-id="c1a35-193">이 cmdlet은 특성 값 및 적용되는 정보 장벽 정책과 같은 사용자에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-193">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>

    |<span data-ttu-id="c1a35-194">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-194">**Syntax**</span></span>|<span data-ttu-id="c1a35-195">**예**</span><span class="sxs-lookup"><span data-stu-id="c1a35-195">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="c1a35-196">이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-196">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="c1a35-197">이 예에서는 Office 365의 두 사용자 계정인 *Meganb과* *Alex의 alexw를* *참조합니다.* </span><span class="sxs-lookup"><span data-stu-id="c1a35-197">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> <span data-ttu-id="c1a35-198">이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-198">You can use any value that uniquely identifies the user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span>|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> <span data-ttu-id="c1a35-199">이 예에서는 Office 365의 단일 *계정, 즉 을(를) 참조합니다.*</span><span class="sxs-lookup"><span data-stu-id="c1a35-199">In this example, we refer to a single account in Office 365: *jeanp*.</span></span> |

2. <span data-ttu-id="c1a35-200">결과를 검토하여 정보 장벽 정책이 할당되어 있으며 사용자가 속한 세그먼트를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-200">Review the results to see if information barrier policies are assigned, and to which segment(s) the user(s) belong.</span></span>

3. <span data-ttu-id="c1a35-201">정보 장벽의 영향을 받는 세그먼트에서 사용자를 제거하려면 Azure Active Directory에서 사용자의 프로필 정보를 [업데이트합니다.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="c1a35-201">To remove a user from a segment affected by information barriers, [update the user's profile information in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

4. <span data-ttu-id="c1a35-202">FwdSync가 발생할 때까지 약 30분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-202">Wait about 30 minutes for FwdSync to occur.</span></span> <span data-ttu-id="c1a35-203">또는 `Start-InformationBarrierPoliciesApplication` cmdlet을 실행하여 모든 활성 정보 장벽 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-203">Or, run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies.</span></span>

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="c1a35-204">문제: 정보 장벽 응용 프로그램 프로세스 시간이 너무 오래 늦습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-204">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="c1a35-205">**Start-InformationBarrierPoliciesApplication** cmdlet을 실행한 후 프로세스가 완료되는 데 시간이 매우 오래 지난 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-205">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-206">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-206">What to do</span></span>

<span data-ttu-id="c1a35-207">정책 응용 프로그램 cmdlet을 실행하면 조직의 모든 계정에 대해 사용자에 의해 정보 장벽 정책이 적용되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-207">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="c1a35-208">사용자가 많은 경우 처리하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-208">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="c1a35-209">(일반적으로 사용자 계정 5,000개 처리에 1시간 정도 소요됩니다.)</span><span class="sxs-lookup"><span data-stu-id="c1a35-209">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="c1a35-210">**Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하여 최신 정책 응용 프로그램의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-210">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    |<span data-ttu-id="c1a35-211">**최신 정책 응용 프로그램을 보시고**</span><span class="sxs-lookup"><span data-stu-id="c1a35-211">**To view the most recent policy application**</span></span>|<span data-ttu-id="c1a35-212">**모든 정책 응용 프로그램의 상태를 확인**</span><span class="sxs-lookup"><span data-stu-id="c1a35-212">**To view status for all policy applications**</span></span>|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    <span data-ttu-id="c1a35-213">그러면 정책 응용 프로그램이 완료, 실패 또는 진행 중인지 여부에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-213">This will display information about whether policy application completed, failed, or is in progress.</span></span>

2. <span data-ttu-id="c1a35-214">이전 단계의 결과에 따라 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-214">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="c1a35-215">**상태**</span><span class="sxs-lookup"><span data-stu-id="c1a35-215">**Status**</span></span>|<span data-ttu-id="c1a35-216">**다음 단계**</span><span class="sxs-lookup"><span data-stu-id="c1a35-216">**Next step**</span></span>|
    |:---------|:------------|
    | <span data-ttu-id="c1a35-217">**시작되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="c1a35-217">**Not started**</span></span> | <span data-ttu-id="c1a35-218">**Start-InformationBarrierPoliciesApplication** cmdlet이 실행된 지 45분 이상이 지난 경우 감사 로그를 검토하여 정책 정의에 오류가 발생하거나 응용 프로그램이 시작되지 않은 다른 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-218">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    | <span data-ttu-id="c1a35-219">**실패**</span><span class="sxs-lookup"><span data-stu-id="c1a35-219">**Failed**</span></span> | <span data-ttu-id="c1a35-220">응용 프로그램이 실패한 경우 감사 로그를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-220">If the application has failed, review your audit log.</span></span> <span data-ttu-id="c1a35-221">또한 세그먼트 및 정책을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-221">Also review your segments and policies.</span></span> <span data-ttu-id="c1a35-222">두 개 이상의 세그먼트에 할당된 사용자가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c1a35-222">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="c1a35-223">세그먼트에 두 개 이상의 정치적이 할당되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="c1a35-223">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="c1a35-224">필요한 경우 세그먼트를 [편집하고](information-barriers-edit-segments-policies.md#edit-a-segment) 정책을 편집한 다음 **Start-InformationBarrierPoliciesApplication** cmdlet을 다시 실행합니다. [](information-barriers-edit-segments-policies.md#edit-a-policy)</span><span class="sxs-lookup"><span data-stu-id="c1a35-224">If necessary, [edit segments](information-barriers-edit-segments-policies.md#edit-a-segment) and/or [edit policies](information-barriers-edit-segments-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span> |
    | <span data-ttu-id="c1a35-225">**진행 중**</span><span class="sxs-lookup"><span data-stu-id="c1a35-225">**In progress**</span></span> | <span data-ttu-id="c1a35-226">응용 프로그램이 아직 진행 중이면 완료할 시간을 더 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-226">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="c1a35-227">며칠이 지난 경우 감사 로그를 수집한 다음 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-227">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a><span data-ttu-id="c1a35-228">문제: 정보 장벽 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-228">Issue: Information barrier policies are not being applied at all</span></span>

<span data-ttu-id="c1a35-229">이 경우 세그먼트를 정의하고 정보 장벽 정책을 정의하고 해당 정책을 적용하려고 시도했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-229">In this case, you have defined segments, defined information barrier policies, and have attempted to apply those policies.</span></span> <span data-ttu-id="c1a35-230">그러나 cmdlet을 실행하면 정책 응용 프로그램이 실패한 `Get-InformationBarrierPoliciesApplicationStatus` 것으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-230">However, when you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, you can see that policy application has failed.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-231">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-231">What to do</span></span>

<span data-ttu-id="c1a35-232">조직에 [Exchange](/exchange/address-books/address-book-policies/address-book-policies) 주소 책 정책이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="c1a35-232">Make sure that your organization does not have [Exchange address book policies](/exchange/address-books/address-book-policies/address-book-policies) in place.</span></span> <span data-ttu-id="c1a35-233">이러한 정책은 정보 장벽 정책이 적용되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-233">Such policies will prevent information barrier policies from being applied.</span></span>

1. <span data-ttu-id="c1a35-234">Exchange [Online PowerShell에 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="c1a35-234">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c1a35-235">[Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet을 실행하고 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-235">Run the [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) cmdlet, and review the results.</span></span>

    |<span data-ttu-id="c1a35-236">**결과**</span><span class="sxs-lookup"><span data-stu-id="c1a35-236">**Results**</span></span>|<span data-ttu-id="c1a35-237">**다음 단계**</span><span class="sxs-lookup"><span data-stu-id="c1a35-237">**Next step**</span></span>|
    |:----------|:------------|
    | <span data-ttu-id="c1a35-238">Exchange 주소부 정책 나열</span><span class="sxs-lookup"><span data-stu-id="c1a35-238">Exchange address book policies are listed</span></span> | [<span data-ttu-id="c1a35-239">주소부 정책 제거</span><span class="sxs-lookup"><span data-stu-id="c1a35-239">Remove address book policies</span></span>](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | <span data-ttu-id="c1a35-240">주소부 정책이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-240">No address book policies exist</span></span> |<span data-ttu-id="c1a35-241">감사 로그를 검토하여 정책 응용 프로그램이 실패하는 이유 확인</span><span class="sxs-lookup"><span data-stu-id="c1a35-241">Review your audit logs to find out why policy application is failing</span></span> |

3. <span data-ttu-id="c1a35-242">[사용자 계정, 세그먼트,](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)정책 또는 정책 응용 프로그램의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-242">[View status of user accounts, segments, policies, or policy application](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).</span></span>

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a><span data-ttu-id="c1a35-243">문제: 지정된 모든 사용자에게 적용되지 않는 정보 장벽 정책</span><span class="sxs-lookup"><span data-stu-id="c1a35-243">Issue: Information barrier policy not applied to all designated users</span></span>

<span data-ttu-id="c1a35-244">세그먼트를 정의하고, 정보 장벽 정책을 정의하고, 해당 정책을 적용하려고 시도한 후 정책이 일부 받는 사람에게 적용되고 다른 받는 사람에게는 적용되지 않는 것을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-244">After you have defined segments, defined information barrier policies, and have attempted to apply those policies, you may find that the policy is applying to some recipients, but not to others.</span></span>
<span data-ttu-id="c1a35-245">cmdlet을 실행할 때 출력에서 `Get-InformationBarrierPoliciesApplicationStatus` 다음 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-245">When you run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, search the output for text like this.</span></span>

> <span data-ttu-id="c1a35-246">ID: `<application guid>`</span><span class="sxs-lookup"><span data-stu-id="c1a35-246">Identity: `<application guid>`</span></span>
>
> <span data-ttu-id="c1a35-247">총 받는 사람: 81527</span><span class="sxs-lookup"><span data-stu-id="c1a35-247">Total Recipients: 81527</span></span>
>
> <span data-ttu-id="c1a35-248">실패한 받는 사람: 2</span><span class="sxs-lookup"><span data-stu-id="c1a35-248">Failed Recipients: 2</span></span>
>
> <span data-ttu-id="c1a35-249">오류 범주: 없음</span><span class="sxs-lookup"><span data-stu-id="c1a35-249">Failure Category: None</span></span>
>
> <span data-ttu-id="c1a35-250">상태: 완료</span><span class="sxs-lookup"><span data-stu-id="c1a35-250">Status: Complete</span></span>

### <a name="what-to-do"></a><span data-ttu-id="c1a35-251">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="c1a35-251">What to do</span></span>

1. <span data-ttu-id="c1a35-252">감사 로그에서 `<application guid>` .를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-252">Search in the audit log for `<application guid>`.</span></span> <span data-ttu-id="c1a35-253">이 PowerShell 코드를 복사하고 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-253">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. <span data-ttu-id="c1a35-254">감사 로그의 자세한 출력에서 해당 필드 및 필드의 값을 `"UserId"` 확인할 수 `"ErrorDetails"` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-254">Check the detailed output from the audit log for the values of the `"UserId"` and `"ErrorDetails"` fields.</span></span> <span data-ttu-id="c1a35-255">이렇게 하면 실패의 이유가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-255">This will give you the reason for the failure.</span></span> <span data-ttu-id="c1a35-256">이 PowerShell 코드를 복사하고 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-256">You can copy this PowerShell code and modify for your variables.</span></span>

```powershell
   $DetailedLogs[1] |fl
```

<span data-ttu-id="c1a35-257">예:</span><span class="sxs-lookup"><span data-stu-id="c1a35-257">For example:</span></span>

> <span data-ttu-id="c1a35-258">"UserId": User1</span><span class="sxs-lookup"><span data-stu-id="c1a35-258">"UserId":  User1</span></span>
>
><span data-ttu-id="c1a35-259">"ErrorDetails":"Status: IBPolicyConflict.</span><span class="sxs-lookup"><span data-stu-id="c1a35-259">"ErrorDetails":"Status: IBPolicyConflict.</span></span> <span data-ttu-id="c1a35-260">오류: IB 세그먼트 "segment id1" 및 IB 세그먼트 "segment id2"에 충돌이 있으며 받는 사람에게 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-260">Error: IB  segment "segment id1" and IB segment "segment id2" has conflict and cannot be assigned to the recipient.</span></span>

3. <span data-ttu-id="c1a35-261">일반적으로 사용자가 두 개 이상의 세그먼트에 포함되어 있는 것을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-261">Usually, you will find that a user has been included in more than one segment.</span></span> <span data-ttu-id="c1a35-262">에서 값을 업데이트하여 이 문제를 `-UserGroupFilter` 해결할 수 `OrganizationSegments` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a35-262">You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments`.</span></span>

4. <span data-ttu-id="c1a35-263">다음 절차에 따라 정보 장벽 정책을 [다시 적용합니다.](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="c1a35-263">Re-apply information barrier policies using these procedures [Information Barriers policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).</span></span>

## <a name="resources"></a><span data-ttu-id="c1a35-264">리소스</span><span class="sxs-lookup"><span data-stu-id="c1a35-264">Resources</span></span>

- [<span data-ttu-id="c1a35-265">Microsoft Teams의 정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="c1a35-265">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="c1a35-266">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="c1a35-266">Information barriers</span></span>](information-barriers.md)
