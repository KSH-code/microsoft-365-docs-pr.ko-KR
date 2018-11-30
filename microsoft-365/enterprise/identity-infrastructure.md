---
title: '2단계: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 ID 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870124"
---
# <a name="phase-2-identity"></a><span data-ttu-id="df03c-103">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="df03c-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="df03c-104">Microsoft 365 Enterprise에서 적절히 계획되고 실행되는 ID 인프라는 인증된 사용자와 장치에서만 생산성 작업 및 데이터에 액세스할 수 있도록 하고 보안을 강화할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="df03c-105">ID 인프라를 이미 배포한 경우 [ID 종료 조건](identity-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="df03c-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="df03c-106">Microsoft 365 Enterprise ID 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="df03c-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="df03c-p101">다음 단계를 사용하여 클라우드에서 새 ID 인프라를 계획 및 배포할 수 있습니다. 또한 이러한 단계를 사용하여 Microsoft 365 Enterprise와 함께 작동하도록 기존 온-프레미스 또는 하이브리드 ID 인프라를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="df03c-109">사용자 및 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="df03c-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="df03c-110">전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="df03c-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="df03c-111">주문형 전역 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="df03c-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="df03c-112">암호 재설정 간소화</span><span class="sxs-lookup"><span data-stu-id="df03c-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="df03c-113">다단계 인증 설정</span><span class="sxs-lookup"><span data-stu-id="df03c-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="df03c-114">자격 증명 손상으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="df03c-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="df03c-115">디렉터리 동기화</span><span class="sxs-lookup"><span data-stu-id="df03c-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="df03c-116">동기화 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="df03c-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="df03c-117">암호 업데이트 간소화</span><span class="sxs-lookup"><span data-stu-id="df03c-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="df03c-118">사용자 로그인 간소화</span><span class="sxs-lookup"><span data-stu-id="df03c-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="df03c-119">Office 365 로그인 페이지 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df03c-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="df03c-120">자동 라이선싱 설정</span><span class="sxs-lookup"><span data-stu-id="df03c-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="df03c-121">테넌트 및 로그인 활동 모니터링</span><span class="sxs-lookup"><span data-stu-id="df03c-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="df03c-122">사용자가 자신의 그룹을 만들고 관리하도록 허용</span><span class="sxs-lookup"><span data-stu-id="df03c-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="df03c-123">동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="df03c-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="df03c-124">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](identity-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="df03c-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="df03c-125">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="df03c-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="df03c-p102">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. ID을 확인하려면 다음 문서의 권장 사항 및 설정과 함께 이 작업 단계의 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="df03c-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="df03c-128">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="df03c-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="df03c-129">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="df03c-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="df03c-130">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="df03c-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="df03c-131">다음 리소스에서는 Microsoft의 IT 전문가가 Microsoft 365 Enterprise의 ID 기능을 계획하고 배포한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="df03c-132">Microsoft에서 사용자 ID 및 보안 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="df03c-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="df03c-133">상승된 액세스 권한에 대해 Azure AD Privileged Identity Management 사용</span><span class="sxs-lookup"><span data-stu-id="df03c-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="df03c-134">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="df03c-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="df03c-135">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스를 위해 [Microsoft 용 하이브리드 ID 인프라를 구축](contoso-identity.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="df03c-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="df03c-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="df03c-137">사용자 및 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="df03c-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
