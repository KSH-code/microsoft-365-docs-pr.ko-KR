---
title: '2단계: ID'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 사용자의 ID 인프라를 배포하는 단계입니다.
ms.openlocfilehash: f32df9a35e09b438b5034ad963523879a639a3fc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067332"
---
# <a name="phase-2-identity"></a><span data-ttu-id="b9e45-103">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="b9e45-103">Phase 2: Identity</span></span>

![2단계: ID](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="b9e45-105">Microsoft 365 Enterprise에서 적절히 계획되고 실행되는 ID 인프라는 인증된 사용자와 장치에서만 생산성 작업 및 데이터에 액세스할 수 있도록 하고 보안을 강화할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e45-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="b9e45-106">Microsoft 365 Enterprise에 대한 인증과 ID 모델의 개요에 대한 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9e45-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b9e45-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="b9e45-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="b9e45-108">ID 인프라를 이미 배포한 경우 [ID 종료 조건](identity-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e45-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="b9e45-109">각 Microsoft 365 Enterprise 요금제의 ID 기능, Azure AD(Active Directory)의 역할, 온-프레미스 및 클라우드 기반 구성 요소, 가장 일반적인 인증 구성에 대한 자세한 내용은 [ID 인프라 포스터](../media/identity-infrastructure/M365E-ID-Infra.pdf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e45-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="b9e45-110">[![ID 인프라 포스터](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="b9e45-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="b9e45-111">이 두 페이지 포스터는 Microsoft 365 Enterprise에 대한 ID 개념과 구성을 빠르게 향상시킬 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e45-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b9e45-112">[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e45-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="b9e45-113">Microsoft 365 Enterprise ID 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="b9e45-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="b9e45-p101">다음 단계를 사용하여 클라우드에서 새 ID 인프라를 계획 및 배포할 수 있습니다. 또한 이러한 단계를 사용하여 Microsoft 365 Enterprise와 함께 작동하도록 기존 온-프레미스 또는 하이브리드 ID 인프라를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e45-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![1단계](../media/stepnumbers/Step1.png)| [<span data-ttu-id="b9e45-117">전역 관리자 계정 생성 및 보호</span><span class="sxs-lookup"><span data-stu-id="b9e45-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![2단계](../media/stepnumbers/Step2.png)| [<span data-ttu-id="b9e45-119">암호 보호</span><span class="sxs-lookup"><span data-stu-id="b9e45-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![3단계](../media/stepnumbers/Step3.png)| [<span data-ttu-id="b9e45-121">사용자 로그인 보안 및 관리</span><span class="sxs-lookup"><span data-stu-id="b9e45-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![4단계](../media/stepnumbers/Step4.png)| [<span data-ttu-id="b9e45-123">사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="b9e45-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![5단계](../media/stepnumbers/Step5.png)| [<span data-ttu-id="b9e45-125">그룹을 사용하여 관리</span><span class="sxs-lookup"><span data-stu-id="b9e45-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![6단계](../media/stepnumbers/Step6.png)| [<span data-ttu-id="b9e45-127">ID 거버넌스 구성</span><span class="sxs-lookup"><span data-stu-id="b9e45-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="b9e45-128">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](identity-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise ID에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e45-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="b9e45-129">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="b9e45-129">Identity and device access recommendations</span></span>

<span data-ttu-id="b9e45-p102">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. ID을 확인하려면 다음 문서의 권장 사항 및 설정과 함께 이 작업 단계의 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e45-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="b9e45-132">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b9e45-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="b9e45-133">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="b9e45-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="b9e45-134">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="b9e45-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b9e45-135">Microsoft의 IT 전문가가 [ID와 보안 액세스를 관리하는 방법](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5)을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b9e45-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="b9e45-136">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="b9e45-136">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b9e45-137">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스를 위해 [Microsoft 용 하이브리드 ID 인프라를 구축](contoso-identity.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b9e45-137">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="b9e45-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b9e45-139">Next step</span></span>

|||
|:-------|:-----|
|![1단계](../media/stepnumbers/Step1.png)| [<span data-ttu-id="b9e45-141">전역 관리자 계정 생성 및 보호</span><span class="sxs-lookup"><span data-stu-id="b9e45-141">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
