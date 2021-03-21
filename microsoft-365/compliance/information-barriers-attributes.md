---
title: 정보 장벽 정책의 속성
description: 이 문서는 정보 장벽 세그먼트를 정의하는 데 사용할 수 있는 Azure Active Directory 사용자 계정 특성에 대한 참조입니다.
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
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919734"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="13e41-103">정보 장벽 정책의 속성</span><span class="sxs-lookup"><span data-stu-id="13e41-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="13e41-104">Azure Active Directory의 특정 특성을 사용하여 사용자를 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="13e41-105">세그먼트가 정의되고 나면 이러한 세그먼트를 정보 장벽 정책에 대한 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="13e41-106">예를 들어 **Department를** 사용하여 조직 내의 부서별로 사용자 세그먼트를 정의할 수 있습니다(한 번의 직원이 두 부서에 동시에 작업하지 않을 경우).</span><span class="sxs-lookup"><span data-stu-id="13e41-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="13e41-107">이 문서에서는 정보 장벽이 있는 특성을 사용하는 방법을 설명하고 사용할 수 있는 특성 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="13e41-108">정보 장벽에 대한 자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e41-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="13e41-109">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="13e41-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="13e41-110">Microsoft Teams에서 정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="13e41-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="13e41-111">정보 장벽 정책 편집(또는 제거)</span><span class="sxs-lookup"><span data-stu-id="13e41-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="13e41-112">정보 장벽 정책에서 특성을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="13e41-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="13e41-113">이 문서에 나열된 특성을 사용하여 사용자 세그먼트를 정의하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="13e41-114">정의된 세그먼트는 정보 장벽 정책에서 매개 변수(UserGroupFilter 값이라고도 합니다.)  [](information-barriers-policies.md)</span><span class="sxs-lookup"><span data-stu-id="13e41-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="13e41-115">세그먼트를 정의하는 데 사용할 특성을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="13e41-116">(이 [문서의 참조](#reference) 섹션을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="13e41-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="13e41-117">사용자 계정에 1단계에서 선택한 특성에 대해 값이 채워진지 확인</span><span class="sxs-lookup"><span data-stu-id="13e41-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="13e41-118">사용자 계정 세부 정보를 보고 필요한 경우 사용자 계정을 편집하여 특성 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="13e41-119">여러 계정을 편집하거나 PowerShell을 사용하여 단일 계정을 편집하려면 [Office 365 PowerShell을](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)사용하여 사용자 계정 속성 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e41-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).</span></span>

    - <span data-ttu-id="13e41-120">단일 계정을 편집하려면 Azure Active Directory를 사용하여 사용자의 프로필 정보 추가 또는 [업데이트를 참조하세요.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="13e41-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="13e41-121">[다음 예제와 유사한 PowerShell을](information-barriers-policies.md#define-segments-using-powershell)사용하여 세그먼트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="13e41-122">**예**</span><span class="sxs-lookup"><span data-stu-id="13e41-122">**Example**</span></span>|<span data-ttu-id="13e41-123">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="13e41-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="13e41-124">Department 특성을 사용하여 Segment1이라는 세그먼트 정의</span><span class="sxs-lookup"><span data-stu-id="13e41-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="13e41-125">MemberOf 특성을 사용하여 SegmentA라는 세그먼트를 정의합니다(이 특성에 "BlueGroup"과 같은 그룹 이름이 포함된 경우)</span><span class="sxs-lookup"><span data-stu-id="13e41-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="13e41-126">ExtensionAttribute1을 사용하여 DayTraders라는 세그먼트를 정의합니다.(이 특성에 "DayTrader"와 같은 직위가 포함되어 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="13e41-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="13e41-127">세그먼트를 정의할 때 모든 세그먼트에 동일한 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="13e41-128">예를 들어 Department를 사용하여 일부 세그먼트를 정의하는 경우 *Department를* 사용하여 모든 세그먼트를 *정의합니다.*</span><span class="sxs-lookup"><span data-stu-id="13e41-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="13e41-129">Department를 사용하여 일부 세그먼트를 정의하고 MemberOf를 사용하는 세그먼트는 *정의하지 않습니다.* </span><span class="sxs-lookup"><span data-stu-id="13e41-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="13e41-130">세그먼트가 겹치지 않는지 확인 각 사용자를 정확히 하나의 세그먼트에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="13e41-131">참조</span><span class="sxs-lookup"><span data-stu-id="13e41-131">Reference</span></span>

<span data-ttu-id="13e41-132">다음 표에는 정보 장벽에 사용할 수 있는 특성이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e41-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="13e41-133">**Azure Active Directory 속성 <br/> 이름(LDAP 표시 이름)**</span><span class="sxs-lookup"><span data-stu-id="13e41-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="13e41-134">**Exchange 속성 이름**</span><span class="sxs-lookup"><span data-stu-id="13e41-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="13e41-135">Co</span><span class="sxs-lookup"><span data-stu-id="13e41-135">Co</span></span> | <span data-ttu-id="13e41-136">Co</span><span class="sxs-lookup"><span data-stu-id="13e41-136">Co</span></span> |
| <span data-ttu-id="13e41-137">Company</span><span class="sxs-lookup"><span data-stu-id="13e41-137">Company</span></span> | <span data-ttu-id="13e41-138">Company</span><span class="sxs-lookup"><span data-stu-id="13e41-138">Company</span></span> |
| <span data-ttu-id="13e41-139">부서</span><span class="sxs-lookup"><span data-stu-id="13e41-139">Department</span></span> | <span data-ttu-id="13e41-140">부서</span><span class="sxs-lookup"><span data-stu-id="13e41-140">Department</span></span> |
| <span data-ttu-id="13e41-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="13e41-141">ExtensionAttribute1</span></span> | <span data-ttu-id="13e41-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="13e41-142">CustomAttribute1</span></span> |
| <span data-ttu-id="13e41-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="13e41-143">ExtensionAttribute2</span></span> | <span data-ttu-id="13e41-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="13e41-144">CustomAttribute2</span></span> |
| <span data-ttu-id="13e41-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="13e41-145">ExtensionAttribute3</span></span> | <span data-ttu-id="13e41-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="13e41-146">CustomAttribute3</span></span> |
| <span data-ttu-id="13e41-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="13e41-147">ExtensionAttribute4</span></span> | <span data-ttu-id="13e41-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="13e41-148">CustomAttribute4</span></span> |
| <span data-ttu-id="13e41-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="13e41-149">ExtensionAttribute5</span></span> | <span data-ttu-id="13e41-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="13e41-150">CustomAttribute5</span></span> |
| <span data-ttu-id="13e41-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="13e41-151">ExtensionAttribute6</span></span> | <span data-ttu-id="13e41-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="13e41-152">CustomAttribute6</span></span> |
| <span data-ttu-id="13e41-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="13e41-153">ExtensionAttribute7</span></span> | <span data-ttu-id="13e41-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="13e41-154">CustomAttribute7</span></span> |
| <span data-ttu-id="13e41-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="13e41-155">ExtensionAttribute8</span></span> | <span data-ttu-id="13e41-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="13e41-156">CustomAttribute8</span></span> |
| <span data-ttu-id="13e41-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="13e41-157">ExtensionAttribute9</span></span> | <span data-ttu-id="13e41-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="13e41-158">CustomAttribute9</span></span> |
| <span data-ttu-id="13e41-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="13e41-159">ExtensionAttribute10</span></span> | <span data-ttu-id="13e41-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="13e41-160">CustomAttribute10</span></span> |
| <span data-ttu-id="13e41-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="13e41-161">ExtensionAttribute11</span></span> | <span data-ttu-id="13e41-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="13e41-162">CustomAttribute11</span></span> |
| <span data-ttu-id="13e41-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="13e41-163">ExtensionAttribute12</span></span> | <span data-ttu-id="13e41-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="13e41-164">CustomAttribute12</span></span> |
| <span data-ttu-id="13e41-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="13e41-165">ExtensionAttribute13</span></span> | <span data-ttu-id="13e41-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="13e41-166">CustomAttribute13</span></span> |
| <span data-ttu-id="13e41-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="13e41-167">ExtensionAttribute14</span></span> | <span data-ttu-id="13e41-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="13e41-168">CustomAttribute14</span></span> |
| <span data-ttu-id="13e41-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="13e41-169">ExtensionAttribute15</span></span> | <span data-ttu-id="13e41-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="13e41-170">CustomAttribute15</span></span> |
| <span data-ttu-id="13e41-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="13e41-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="13e41-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="13e41-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="13e41-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="13e41-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="13e41-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="13e41-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="13e41-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="13e41-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="13e41-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="13e41-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="13e41-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="13e41-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="13e41-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="13e41-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="13e41-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="13e41-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="13e41-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="13e41-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="13e41-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="13e41-181">MailNickname</span></span> | <span data-ttu-id="13e41-182">별칭</span><span class="sxs-lookup"><span data-stu-id="13e41-182">Alias</span></span> |
| <span data-ttu-id="13e41-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="13e41-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="13e41-184">사무실</span><span class="sxs-lookup"><span data-stu-id="13e41-184">Office</span></span> |
| <span data-ttu-id="13e41-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="13e41-185">PostalCode</span></span> | <span data-ttu-id="13e41-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="13e41-186">PostalCode</span></span> |
| <span data-ttu-id="13e41-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="13e41-187">ProxyAddresses</span></span> | <span data-ttu-id="13e41-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="13e41-188">EmailAddresses</span></span> |
| <span data-ttu-id="13e41-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="13e41-189">StreetAddress</span></span> | <span data-ttu-id="13e41-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="13e41-190">StreetAddress</span></span> |
| <span data-ttu-id="13e41-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="13e41-191">TargetAddress</span></span> | <span data-ttu-id="13e41-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="13e41-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="13e41-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="13e41-193">UsageLocation</span></span> | <span data-ttu-id="13e41-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="13e41-194">UsageLocation</span></span> |
| <span data-ttu-id="13e41-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="13e41-195">UserPrincipalName</span></span> | <span data-ttu-id="13e41-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="13e41-196">UserPrincipalName</span></span> |
| <span data-ttu-id="13e41-197">메일</span><span class="sxs-lookup"><span data-stu-id="13e41-197">Mail</span></span> | <span data-ttu-id="13e41-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="13e41-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="13e41-199">설명</span><span class="sxs-lookup"><span data-stu-id="13e41-199">Description</span></span> | <span data-ttu-id="13e41-200">설명</span><span class="sxs-lookup"><span data-stu-id="13e41-200">Description</span></span> |
| <span data-ttu-id="13e41-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="13e41-201">MemberOf</span></span> | <span data-ttu-id="13e41-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="13e41-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="13e41-203">리소스</span><span class="sxs-lookup"><span data-stu-id="13e41-203">Resources</span></span>

- [<span data-ttu-id="13e41-204">Microsoft Teams에서 정보 장벽에 대한 정책 정의</span><span class="sxs-lookup"><span data-stu-id="13e41-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="13e41-205">정보 장벽 문제 해결</span><span class="sxs-lookup"><span data-stu-id="13e41-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="13e41-206">정보 장벽</span><span class="sxs-lookup"><span data-stu-id="13e41-206">Information barriers</span></span>](information-barriers.md)