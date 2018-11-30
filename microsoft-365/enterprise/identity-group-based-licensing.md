---
title: '12단계: 자동 라이선싱 설정'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 그룹 기반 라이선싱을 이해하고 Azure AD 그룹에 대해 구성합니다.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869701"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="631f0-103">12단계: 자동 라이선싱 설정</span><span class="sxs-lookup"><span data-stu-id="631f0-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="631f0-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="631f0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="631f0-p101">이 단계에서는 구독 집합의 라이선스를 그룹의 모든 구성원에게 자동으로 할당하도록 Azure AD에서 보안 그룹을 구성합니다. 이를 *그룹 기반 라이선싱*이라고 합니다. 그룹에서 사용자 계정이 추가되거나 제거된 경우 해당 그룹의 구독에 대한 라이선스가 사용자 계정에서 자동으로 할당되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="631f0-108">Microsoft 365 Enterprise의 경우 다음 두 라이선스를 모두 할당하도록 Azure AD 보안 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="631f0-109">Office 365 Enterprise E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="631f0-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="631f0-110">EMS(Enterprise Mobility + Security) E3 또는 E5</span><span class="sxs-lookup"><span data-stu-id="631f0-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="631f0-p102">2단계에서 식별한 그룹을 사용하여 해당 그룹의 모든 사용자에게 Office 365 및 EMS 라이선스가 있어야 하는 계정 목록이 포함된 그룹을 찾습니다. 모든 그룹 구성원을 위한 라이선스가 충분한지 확인합니다. 라이선스가 부족하면 라이선스를 사용할 수 있을 때까지 새 사용자에게 라이선스가 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="631f0-114">Azure B2B 계정이 포함된 그룹에 대해 *그룹 기반 라이선싱*을 구성해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="631f0-115">추가 정보는 [Azure Active Directory의 그룹 기반 라이선싱 기본 사항](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631f0-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="631f0-116">[Azure 보안 그룹에 대해 그룹 기반 라이선싱을 구성하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="631f0-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="631f0-117">이 단계의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-117">The results of this step are:</span></span>

- <span data-ttu-id="631f0-118">그룹 기반 라이선싱에 적합한 보안 그룹을 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="631f0-119">그룹 기반 라이선싱에 대해 이러한 그룹을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="631f0-121">테스트 랩 가이드: 라이선스 및 그룹 등록 자동화</span><span class="sxs-lookup"><span data-stu-id="631f0-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="631f0-122">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-group-license)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="631f0-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="631f0-123">다음 단계</span><span class="sxs-lookup"><span data-stu-id="631f0-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="631f0-124">테넌트 및 로그인 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="631f0-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

