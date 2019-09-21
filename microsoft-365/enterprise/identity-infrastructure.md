---
title: '2단계: ID'
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
ms.openlocfilehash: 2d9ffcc5122b5a5dfc94fb007167655e879d6799
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071697"
---
# <a name="phase-2-identity"></a><span data-ttu-id="bafc5-103">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="bafc5-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="bafc5-104">Microsoft 365 Enterprise에서 적절히 계획되고 실행되는 ID 인프라는 인증된 사용자와 장치에서만 생산성 작업 및 데이터에 액세스할 수 있도록 하고 보안을 강화할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bafc5-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="bafc5-105">Microsoft 365 Enterprise에 대한 인증과 ID 모델의 개요에 대한 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="bafc5-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="bafc5-106"><p> </p></span><span class="sxs-lookup"><span data-stu-id="bafc5-106"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="bafc5-107">ID 인프라를 이미 배포한 경우 [ID 종료 조건](identity-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bafc5-107">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="bafc5-108">각 Microsoft 365 Enterprise 요금제의 ID 기능, Azure AD(Active Directory)의 역할, 온-프레미스 및 클라우드 기반 구성 요소, 가장 일반적인 인증 구성에 대한 자세한 내용은 [ID 인프라 포스터](media/identity-infrastructure/M365E-ID-Infra.pdf)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bafc5-108">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="bafc5-109">[![ID 인프라 포스터](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="bafc5-109">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="bafc5-110">이 두 페이지 포스터는 Microsoft 365 Enterprise에 대한 ID 개념과 구성을 빠르게 향상시킬 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bafc5-110">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="bafc5-111">[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bafc5-111">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="bafc5-112">Microsoft 365 Enterprise ID 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="bafc5-112">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="bafc5-p101">다음 단계를 사용하여 클라우드에서 새 ID 인프라를 계획 및 배포할 수 있습니다. 또한 이러한 단계를 사용하여 Microsoft 365 Enterprise와 함께 작동하도록 기존 온-프레미스 또는 하이브리드 ID 인프라를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bafc5-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="bafc5-115">전역 관리자 계정 생성 및 보호</span><span class="sxs-lookup"><span data-stu-id="bafc5-115">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="bafc5-116">암호를 보호</span><span class="sxs-lookup"><span data-stu-id="bafc5-116">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="bafc5-117">사용자 로그인 보안 및 관리</span><span class="sxs-lookup"><span data-stu-id="bafc5-117">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="bafc5-118">사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="bafc5-118">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="bafc5-119">그룹을 사용하여 관리</span><span class="sxs-lookup"><span data-stu-id="bafc5-119">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="bafc5-120">ID 거버넌스 구성</span><span class="sxs-lookup"><span data-stu-id="bafc5-120">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="bafc5-121">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](identity-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise ID에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bafc5-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="bafc5-122">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="bafc5-122">Identity and device access recommendations</span></span>

<span data-ttu-id="bafc5-p102">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. ID을 확인하려면 다음 문서의 권장 사항 및 설정과 함께 이 작업 단계의 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="bafc5-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="bafc5-125">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bafc5-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="bafc5-126">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="bafc5-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="bafc5-127">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="bafc5-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bafc5-128">Microsoft의 IT 전문가가 [ID와 보안 액세스를 관리하는 방법](https://www.microsoft.com/ko-KR/itshowcase/deploying-and-managing-microsoft-365#primaryR5)을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bafc5-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/ko-KR/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="bafc5-129">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="bafc5-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bafc5-130">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스를 위해 [Microsoft 용 하이브리드 ID 인프라를 구축](contoso-identity.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bafc5-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="bafc5-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bafc5-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="bafc5-132">전역 관리자 계정 생성 및 보호</span><span class="sxs-lookup"><span data-stu-id="bafc5-132">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
