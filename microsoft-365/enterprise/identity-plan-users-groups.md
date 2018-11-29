---
title: '1단계: 사용자 및 그룹 계획'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 조직을 위해 일할 사용자 및 그룹 집합을 계획합니다.
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869711"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="8decb-103">1단계: 사용자 및 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="8decb-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="8decb-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8decb-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8decb-p101">이 단계에서는 사용자, 그룹 및 그룹 구성원을 보안 기능과 올바른 구성으로 결합하는 ID 인프라를 만듭니다. 이를 통해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="8decb-107">사용자 환경의 리소스에 액세스할 수 있는 사용자에 대한 제어 권한 유지 관리</span><span class="sxs-lookup"><span data-stu-id="8decb-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="8decb-108">강력한 ID 보증(사용자가 본인 소개)과 안전한 장치에서의 액세스를 보장하는 컨트롤로 액세스 보호</span><span class="sxs-lookup"><span data-stu-id="8decb-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="8decb-109">위험 및 데이터 유출 가능성을 줄일 수 있는 적절한 권한으로 사용자 환경의 리소스 프로비전</span><span class="sxs-lookup"><span data-stu-id="8decb-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="8decb-110">사용자 환경에서 비정상적인 사용자 동작을 모니터링하고 자동으로 조치</span><span class="sxs-lookup"><span data-stu-id="8decb-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="8decb-111">기본 ID 공급자 계획</span><span class="sxs-lookup"><span data-stu-id="8decb-111">Plan your primary identity provider</span></span>

<span data-ttu-id="8decb-p102">ID 인프라를 만들려면 기본 ID 공급자를 지정해야 합니다. 이 서비스는 사용자 계정과 해당 특성, 그룹과 해당 구성원을 저장하고 지속적인 관리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="8decb-114">조직에서 Microsoft 365 Enterprise를 도입한 경우 기본 ID 공급자는 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="8decb-p103">**Windows Server AD(Active Directory)** - Windows Server를 실행하는 컴퓨터에서 호스팅되는 인트라넷 ID 공급자입니다. 이는 일반적으로 기존 온-프레미스 ID 공급자를 보유한 조직에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p103">**Windows Server Active Directory (AD)**, an intranet identity provider hosted on computers running Windows Server. This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="8decb-p104">**Azure AD(Azure Active Directory**) - 사용자 환경을 관리 및 보호하는 광범위한 기능을 제공하는 클라우드 기반 IDaaS(Identity as a Service)입니다. 이는 일반적으로 기존 온-프레미스 인프라가 없는 조직에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p104">**Azure Active Directory (Azure AD**), a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment. This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="8decb-p105">조직에 기존 온-프레미스 ID 공급자가 있는 경우 Microsoft 365 Enterprise의 클라우드 기반 서비스에 대한 보다 원활한 액세스를 제공하기 위해 Windows Server AD의 사용자 계정 및 그룹을 Azure AD에 동기화해야 합니다. 또한 Azure AD를 사용하여 Microsoft 클라우드에만 존재하는 그룹을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p105">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Windows Server AD to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise. You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="8decb-121">Azure AD에서 사용자 및 그룹을 만든 후 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="8decb-122">모든 클라우드 응용 프로그램에 대한 모든 Azure AD 계정 관리</span><span class="sxs-lookup"><span data-stu-id="8decb-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="8decb-123">동일한 컨트롤 집합을 사용하여 사용자 환경에서 응용 프로그램에 대한 액세스 보호</span><span class="sxs-lookup"><span data-stu-id="8decb-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="8decb-124">외부 파트너와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="8decb-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="8decb-125">의심스러운 로그인 시도 등 비정상적인 계정 동작을 모니터링하고 자동으로 조치</span><span class="sxs-lookup"><span data-stu-id="8decb-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="8decb-126">사용자 계정 및 그룹을 계획하고 구현하려면 다음 두 섹션의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="8decb-127">사용자 분류</span><span class="sxs-lookup"><span data-stu-id="8decb-127">Categorize your users</span></span>
<span data-ttu-id="8decb-p106">조직의 사용자를 영구 상태인 직원, 임시 상태인 공급업체, 계약자 또는 파트너, 사용자 계정이 없지만 상호 작용 및 공동 작업을 지원하기 위해 특정 서비스 및 리소스에 대한 액세스 권한을 부여해야 하는 외부 사용자 등 여러 가지 방법으로 분류할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="8decb-133">테넌트 계정은 클라우드 서비스에 대한 라이선스를 부여한 조직 내부의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="8decb-134">B2B 계정은 공동 작업에 참여하도록 초대한 조직 외부의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="8decb-p107">조직의 사용자 유형을 조사해 보세요. 어떤 방식으로 그룹화되어 있나요? 예를 들어 개략적인 직무나 목적으로 조직의 사용자를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="8decb-p108">또한 일부 클라우드 서비스는 사용자 계정 없이 조직 외부의 사용자와 공유될 수 있습니다. 이러한 사용자 그룹도 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a><span data-ttu-id="8decb-140">Windows Server AD 및 Azure AD 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="8decb-140">Plan for Windows Server AD and Azure AD groups</span></span>

<span data-ttu-id="8decb-p109">클라우드 환경 관리를 간소화하는 여러 가지 목적으로 Azure AD에서 그룹을 사용할 수 있습니다. 예를 들어 Azure AD 그룹에 대해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="8decb-143">그룹 기반 라이선싱을 사용하여 사용자 계정이 Azure AD에 추가되거나 Windows Server AD에서 동기화되는 즉시 Office 365 및 EMS(Enterprise Mobility + Security)에 대한 라이선스를 자동으로 할당</span><span class="sxs-lookup"><span data-stu-id="8decb-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from Windows Server AD.</span></span> 
- <span data-ttu-id="8decb-144">부서와 같은 사용자 계정 특성에 따라 특정 그룹에 동적으로 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="8decb-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="8decb-145">Saas(Software as a Service) 응용 프로그램에 대해 사용자를 자동으로 프로비전하고 다단계 인증 및 기타 조건부 액세스 규칙을 사용하여 이러한 응용 프로그램에 대한 액세스 보호</span><span class="sxs-lookup"><span data-stu-id="8decb-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="8decb-p110">SharePoint Online 팀 사이트에 대해 사용자 권한 및 액세스 수준을 프로비전할 수 있습니다. 또한 Azure AD 그룹을 범위가 지정된 Azure Information Protection 정책과 함께 사용하여 암호화 및 사용 권한으로 파일을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="8decb-148">결과</span><span class="sxs-lookup"><span data-stu-id="8decb-148">Results</span></span>

<span data-ttu-id="8decb-149">이 단계를 완료하면 다음과 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="8decb-150">조직의 직원과 조직을 위해 일하거나 조직과 협력하는 공급업체, 계약자 및 파트너에게 해당하는 Azure AD의 사용자 계정 목록</span><span class="sxs-lookup"><span data-stu-id="8decb-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="8decb-151">Microsoft 클라우드 서비스 보안 설정의 자동 라이선싱 프로비전을 위해 논리적 사용자 계정 및 기타 그룹 집합을 반영하는 Azure AD의 그룹 및 해당 구성원 집합</span><span class="sxs-lookup"><span data-stu-id="8decb-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="8decb-152">중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-user-groups)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8decb-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="8decb-153">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8decb-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="8decb-154">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="8decb-154">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

