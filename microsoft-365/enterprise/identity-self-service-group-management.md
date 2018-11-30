---
title: '14단계: 사용자가 자신의 그룹을 만들고 관리하도록 허용'
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
description: Azure AD 그룹 셀프 서비스 관리를 이해하고 구성합니다.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870048"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="e148b-103">14단계: 사용자가 자신의 그룹을 만들고 관리하도록 허용</span><span class="sxs-lookup"><span data-stu-id="e148b-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="e148b-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="e148b-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e148b-p101">이 단계에서는 IT 관리자 대신 그룹 소유자가 관리할 수 있는 Azure AD(Active Directory) 그룹을 식별합니다. *셀프 서비스 그룹 관리*라는 이 기능은 관리 역할이 할당되지 않은 그룹 소유자가 보안 그룹을 만들고 관리하도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e148b-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="e148b-p102">사용자는 보안 그룹에서 구성원을 요청할 수 있으며, 이 요청은 IT 관리자가 아니라 그룹 소유자에게 전달됩니다. 이를 통해 그룹의 비즈니스 사용을 이해하고 해당 구성원을 관리할 수 있는 팀, 프로젝트 또는 비즈니스 소유자에게 일상적인 그룹 구성원 제어를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e148b-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="e148b-p103">셀프 서비스 그룹 관리는 Azure AD 보안 및 Office 365 그룹에만 사용할 수 있습니다. 메일 사용이 가능한 그룹, 메일 그룹 또는 온-프레미스 Windows Server AD(Active Directory)에서 동기화 된 그룹에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e148b-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="e148b-111">자세한 내용은 [셀프 서비스 관리에 대한 Azure AD 구성 지침](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e148b-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="e148b-112">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-self-service-groups)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e148b-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e148b-113">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e148b-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="e148b-114">동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="e148b-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
