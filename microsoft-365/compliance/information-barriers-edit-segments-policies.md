---
title: 정보 장벽 정책 관리
description: 정보 장벽에 대한 정책을 편집하거나 제거하는 방법을 학습합니다.
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925554"
---
# <a name="manage-information-barrier-policies"></a><span data-ttu-id="4459d-103">정보 장벽 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4459d-103">Manage information barrier policies</span></span>

<span data-ttu-id="4459d-104">정보 장벽 정책을 [정의한](information-barriers-policies.md)후 문제 해결의 일부로 또는 정기적인 유지 관리로 해당 정책이나 사용자 세그먼트를 변경해야 할 수 있습니다. [](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="4459d-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="4459d-105">이 문서를 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="4459d-106">무슨 작업을 하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="4459d-106">What do you want to do?</span></span>

|<span data-ttu-id="4459d-107">**작업**</span><span class="sxs-lookup"><span data-stu-id="4459d-107">**Action**</span></span>|<span data-ttu-id="4459d-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="4459d-108">**Description**</span></span>|
|:---------|:--------------|
| [<span data-ttu-id="4459d-109">사용자 계정 특성 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-109">Edit user account attributes</span></span>](#edit-user-account-attributes) | <span data-ttu-id="4459d-110">세그먼트를 정의하는 데 Azure Active Directory 특성을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="4459d-111">사용자가 포함되어야 하는 세그먼트에 포함되지 않은 경우 사용자 계정 특성을 편집하여 사용자가 있는 세그먼트를 변경하거나, 다른 특성을 사용하여 세그먼트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span> |
| [<span data-ttu-id="4459d-112">세그먼트 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-112">Edit a segment</span></span>](#edit-a-segment) | <span data-ttu-id="4459d-113">세그먼트의 정의 방법을 변경하려는 경우 세그먼트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="4459d-114">예를 들어 Department를 사용하여 원래 세그먼트를 정의한 다음 *MemberOf와* 같은 다른 특성을 *사용하려는 경우를* 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span> |
| [<span data-ttu-id="4459d-115">정책 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-115">Edit a policy</span></span>](#edit-a-policy) | <span data-ttu-id="4459d-116">정책의 작동 방법을 변경하려는 경우 정보 장벽 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="4459d-117">예를 들어 두 세그먼트 간의 통신을 차단하는 대신 특정 세그먼트 간에만 통신이 발생하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span> |
| [<span data-ttu-id="4459d-118">정책을 비활성 상태로 설정</span><span class="sxs-lookup"><span data-stu-id="4459d-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status) |<span data-ttu-id="4459d-119">정책을 변경하거나 정책을 적용하지 못하게 하려는 경우 정책을 비활성 상태로 설정</span><span class="sxs-lookup"><span data-stu-id="4459d-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span> |
| [<span data-ttu-id="4459d-120">정책 제거</span><span class="sxs-lookup"><span data-stu-id="4459d-120">Remove a policy</span></span>](#remove-a-policy) | <span data-ttu-id="4459d-121">더 이상 특정 정책을 적용하지 필요가 없는 경우 정보 장벽 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span> |
| [<span data-ttu-id="4459d-122">정책 응용 프로그램 중지</span><span class="sxs-lookup"><span data-stu-id="4459d-122">Stop a policy application</span></span>](#stop-a-policy-application) | <span data-ttu-id="4459d-123">정보 장벽 정책을 적용하는 프로세스를 중지하려는 경우 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-123">Take this action when you want to stop the process of applying information barrier policies.</span></span><br/> <span data-ttu-id="4459d-124">정책 응용 프로그램을 중지하는 것은 즉각적인 것이 아니며 사용자에게 이미 적용된 정책을 실행 취소하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-124">Stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span> |
| [<span data-ttu-id="4459d-125">정보 장벽을 위한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="4459d-125">Define policies for information barriers</span></span>](information-barriers-policies.md) | <span data-ttu-id="4459d-126">이러한 정책이 아직 설정되지 않은 경우 정보 장벽 정책을 정의하고 특정 사용자 그룹 간의 통신을 제한하거나 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span> |
| [<span data-ttu-id="4459d-127">정보 장벽 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4459d-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md) | <span data-ttu-id="4459d-128">정보 장벽으로 예기치 않은 문제가 발생할 경우 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-128">Refer to this article when you run into unexpected issues with information barriers.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="4459d-129">이 문서에 설명된 작업을 수행하려면 다음 중 하나와 같은 적절한 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="4459d-130">- Microsoft 365 Enterprise 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="4459d-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="4459d-131">- 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="4459d-131">- Global Administrator</span></span><br/><span data-ttu-id="4459d-132">- 준수 관리자</span><span class="sxs-lookup"><span data-stu-id="4459d-132">- Compliance Administrator</span></span><br/><span data-ttu-id="4459d-133">- IB 준수 관리(새로운 역할입니다!)</span><span class="sxs-lookup"><span data-stu-id="4459d-133">- IB Compliance Management (this is a new role!)</span></span><br><br><span data-ttu-id="4459d-134">정보 장벽의 선행 준비에 대한 자세한 내용은 [Prerequisites (for information barrier policies)을 참조하십시오.](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4459d-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><br><br> <span data-ttu-id="4459d-135">보안 및 준수 센터 [PowerShell에 & 합니다.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="4459d-135">Make sure to [connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="4459d-136">사용자 계정 특성 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-136">Edit user account attributes</span></span>

<span data-ttu-id="4459d-137">다음 절차에 따라 사용자를 분할하는 데 사용되는 특성을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> <span data-ttu-id="4459d-138">예를 들어 Department 특성을 사용하는 경우 하나 이상의 사용자 계정에 현재 Department에 대해 나열된 값이 없는 경우 부서 정보를 포함하도록 해당 사용자 계정을 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> <span data-ttu-id="4459d-139">사용자 계정 특성은 정보 장벽 정책을 할당할 수 있도록 세그먼트를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="4459d-140">특성 값 및 할당된 세그먼트와 같은 특정 사용자 계정에 대한 세부 정보를 확인하려면 Identity 매개 변수와 **함께 Get-InformationBarrierRecipientStatus** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="4459d-141">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4459d-141">**Syntax**</span></span>|<span data-ttu-id="4459d-142">**예**</span><span class="sxs-lookup"><span data-stu-id="4459d-142">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="4459d-143">이름, 별칭, 고유 이름, 정식 도메인 이름, 전자 메일 주소 또는 GUID와 같이 각 사용자를 고유하게 식별하는 모든 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p> <span data-ttu-id="4459d-144">(단일 사용자에 대해 이 cmdlet을 사용할 수도 있습니다. `Get-InformationBarrierRecipientStatus -Identity <value>` )</span><span class="sxs-lookup"><span data-stu-id="4459d-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="4459d-145">이 예제에서는 2개의 사용자 계정인 Office 365 *meganb* 및 *Alex의 alexw를* *참조합니다.*</span><span class="sxs-lookup"><span data-stu-id="4459d-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

2. <span data-ttu-id="4459d-146">사용자 계정 프로필에 대해 편집할 특성을 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4459d-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="4459d-147">자세한 내용은 정보 장벽 [정책에 대한 특성을 참조하세요.](information-barriers-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="4459d-147">For more information, see [Attributes for information barrier policies](information-barriers-attributes.md).</span></span> 

3. <span data-ttu-id="4459d-148">이전 단계에서 선택한 특성의 값을 포함하도록 하나 이상의 사용자 계정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="4459d-149">이 작업을 수행하기 위해 다음 절차 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-149">To take this action, use one of the following procedures:</span></span>

    - <span data-ttu-id="4459d-150">단일 계정을 편집하려면 [를](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)사용하여 사용자 프로필 정보 추가 또는 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4459d-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="4459d-151">여러 계정을 편집하거나 PowerShell을 사용하여 단일 계정을 편집하려면 [PowerShell을](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)사용하여 사용자 계정 속성 Office 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="4459d-152">세그먼트 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-152">Edit a segment</span></span>

<span data-ttu-id="4459d-153">다음 절차에 따라 사용자 세그먼트의 정의를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="4459d-154">예를 들어 세그먼트의 이름을 변경하거나 세그먼트에 포함되는 대상을 확인하는 데 사용되는 필터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="4459d-155">모든 기존 세그먼트를 보시고 **Get-OrganizationSegment** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>

    <span data-ttu-id="4459d-156">구문: `Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="4459d-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="4459d-157">세그먼트 유형, 해당 UserGroupFilter 값, 이를 만들거나 마지막으로 수정한 사람, GUID 등 각 세그먼트 및 세부 정보 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="4459d-158">나중에 참조할 수 있도록 세그먼트 목록을 인쇄하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="4459d-159">예를 들어 세그먼트를 편집하려는 경우 해당 이름을 알거나 값을 식별해야 합니다(Identity 매개 변수와 함께 사용됩니다).</span><span class="sxs-lookup"><span data-stu-id="4459d-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="4459d-160">세그먼트를 편집하려면 **Set-OrganizationSegment** cmdlet을 **Identity** 매개 변수 및 관련 세부 정보와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span>

    |<span data-ttu-id="4459d-161">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4459d-161">**Syntax**</span></span>|<span data-ttu-id="4459d-162">**예**</span><span class="sxs-lookup"><span data-stu-id="4459d-162">**Example**</span></span>|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> <span data-ttu-id="4459d-163">이 예제에서는 *GUID가 c96e0837-c232-4a8a-841e-ef45787d8fcd인* 세그먼트의 경우 부서 이름을 "HRDept"로 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span> |

<span data-ttu-id="4459d-164">조직에 대한 세그먼트 편집을 마치면 정보 장벽 [](information-barriers-policies.md#part-2-define-information-barrier-policies) 정책을 정의하거나 [편집할](#edit-a-policy) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="4459d-165">정책 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-165">Edit a policy</span></span>

1. <span data-ttu-id="4459d-166">현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="4459d-167">구문: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="4459d-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="4459d-168">결과 목록에서 변경할 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="4459d-169">정책의 GUID 및 이름을 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="4459d-170">**Set-InformationBarrierPolicy** cmdlet을 **Identity** 매개 변수와 함께 사용하여 변경 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="4459d-171">예: 리서치 세그먼트가  영업 및 마케팅 세그먼트와 통신하는 것을 차단하기 위해 정책이 정의되어 있는 *경우를 가정해* 보겠습니다. </span><span class="sxs-lookup"><span data-stu-id="4459d-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="4459d-172">정책은 다음 cmdlet을 사용하여 정의했습니다. `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="4459d-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>

    <span data-ttu-id="4459d-173">리서치 부문의 사용자가 HR  세그먼트의 사용자와만 통신할 수 있도록 변경하려는 *경우를 가정해* 가정해 5000명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="4459d-174">이 변경을 위해 다음 cmdlet을 사용 합니다. `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="4459d-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="4459d-175">이 예제에서는 "SegmentsBlocked"를 "SegmentsAllowed"로 변경하고 *HR 세그먼트를 지정했습니다.*</span><span class="sxs-lookup"><span data-stu-id="4459d-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="4459d-176">정책 편집을 마치면 변경 내용을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="4459d-177">(정보 [장벽 정책 적용을](information-barriers-policies.md#part-3-apply-information-barrier-policies)참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="4459d-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="4459d-178">정책을 비활성 상태로 설정</span><span class="sxs-lookup"><span data-stu-id="4459d-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="4459d-179">현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="4459d-180">구문: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="4459d-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="4459d-181">결과 목록에서 변경하거나 제거할 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="4459d-182">정책의 GUID 및 이름을 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="4459d-183">정책의 상태를 비활성으로 설정하기 위해 Identity 매개 변수와 **함께 Set-InformationBarrierPolicy** cmdlet을 사용하며 State 매개 변수를 비활성으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4459d-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="4459d-184">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4459d-184">**Syntax**</span></span>|<span data-ttu-id="4459d-185">**예**</span><span class="sxs-lookup"><span data-stu-id="4459d-185">**Example**</span></span>|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> <span data-ttu-id="4459d-186">이 예에서는 GUID가 *43c37853-ea10-4b90-a23d-ab8c9377247인* 정보 장벽 정책을 비활성 상태로 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span> |

3. <span data-ttu-id="4459d-187">변경 내용을 적용하기 위해 **Start-InformationBarrierPoliciesApplication** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="4459d-188">구문: `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="4459d-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="4459d-189">조직에 대한 변경 내용은 사용자에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="4459d-190">조직 규모가 큰 경우 이 프로세스를 완료하는 데 24시간 이상이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="4459d-191">일반적으로 사용자 계정 5,000개가 처리되는 데 1시간 정도 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="4459d-192">이때 하나 이상의 정보 장벽 정책이 비활성 상태로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="4459d-193">여기에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-193">From here, you can do any of the following actions:</span></span>

- <span data-ttu-id="4459d-194">그대로 유지(비활성 상태로 설정된 정책은 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="4459d-195">정책 편집</span><span class="sxs-lookup"><span data-stu-id="4459d-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="4459d-196">정책 제거</span><span class="sxs-lookup"><span data-stu-id="4459d-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="4459d-197">정책 제거</span><span class="sxs-lookup"><span data-stu-id="4459d-197">Remove a policy</span></span>

1. <span data-ttu-id="4459d-198">현재 정보 장벽 정책 목록을 보기 위해 **Get-InformationBarrierPolicy** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="4459d-199">구문: `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="4459d-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="4459d-200">결과 목록에서 제거할 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="4459d-201">정책의 GUID 및 이름을 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="4459d-202">정책이 비활성 상태로 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4459d-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="4459d-203">**Remove-InformationBarrierPolicy** cmdlet을 Identity 매개 변수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="4459d-204">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4459d-204">**Syntax**</span></span>|<span data-ttu-id="4459d-205">**예**</span><span class="sxs-lookup"><span data-stu-id="4459d-205">**Example**</span></span>|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> <span data-ttu-id="4459d-206">이 예에서는 GUID가 *43c37853-ea10-4b90-a23d-ab8c93772471인* 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> |

    <span data-ttu-id="4459d-207">메시지가 표시되면 변경을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="4459d-208">제거할 각 정책에 대해 1-2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="4459d-209">정책 제거가 완료되면 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="4459d-210">이 작업을 수행하기 위해 **Start-InformationBarrierPoliciesApplication** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-210">To take this action, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="4459d-211">구문: `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="4459d-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="4459d-212">조직에 대한 변경 내용은 사용자에 따라 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="4459d-213">조직 규모가 큰 경우 이 프로세스를 완료하는 데 24시간 이상이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="4459d-214">정책 응용 프로그램 중지</span><span class="sxs-lookup"><span data-stu-id="4459d-214">Stop a policy application</span></span>

<span data-ttu-id="4459d-215">정보 장벽 정책 적용을 시작한 후 해당 정책이 적용되지 못하게 하려는 경우 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-215">After you have started applying information barrier policies, if you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="4459d-216">프로세스를 시작하는 데 약 30~35분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-216">It will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="4459d-217">최신 정보 장벽 정책 응용 프로그램의 상태를 확인하기 위해 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4459d-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="4459d-218">구문: `Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="4459d-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="4459d-219">응용 프로그램의 GUID를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="4459d-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="4459d-220">**Stop-InformationBarrierPoliciesApplication** cmdlet을 Identity 매개 변수와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="4459d-221">**다중값 속성 구문 표에서 선택하는 구문은 cmdlet에 대한 매개 변수 값으로 지정됩니다. 예를 들어 다음 명령을 통해 다중값 속성에 여러 값을 추가할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4459d-221">**Syntax**</span></span>|<span data-ttu-id="4459d-222">**예**</span><span class="sxs-lookup"><span data-stu-id="4459d-222">**Example**</span></span>|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> <span data-ttu-id="4459d-223">이 예에서는 정보 장벽 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4459d-223">In this example, we are stopping information barrier policies from being applied.</span></span> |

## <a name="resources"></a><span data-ttu-id="4459d-224">리소스</span><span class="sxs-lookup"><span data-stu-id="4459d-224">Resources</span></span>

- [<span data-ttu-id="4459d-225">정보 장벽 개요 보기</span><span class="sxs-lookup"><span data-stu-id="4459d-225">Get an overview of information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="4459d-226">정보 장벽을 위한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="4459d-226">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="4459d-227">정보 장벽에 대해 자세히 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4459d-227">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="4459d-228">온라인에서 정보 장벽에 대해 SharePoint 정보</span><span class="sxs-lookup"><span data-stu-id="4459d-228">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="4459d-229">정보 장벽에 대해 자세히 OneDrive</span><span class="sxs-lookup"><span data-stu-id="4459d-229">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="4459d-230">정보 장벽 정책의 속성</span><span class="sxs-lookup"><span data-stu-id="4459d-230">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="4459d-231">정보 장벽 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4459d-231">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)