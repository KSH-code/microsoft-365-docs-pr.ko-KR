---
title: '2단계: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise에 대한 ID 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 6acd462a0fcd4169a42a0b1d0e1738ffcba597f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073898"
---
# <a name="phase-2-identity"></a><span data-ttu-id="aed01-103">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="aed01-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="aed01-104">Microsoft 365 Enterprise에서 적절히 계획되고 실행되는 ID 인프라는 인증된 사용자와 장치에서만 생산성 작업 및 데이터에 액세스할 수 있도록 하고 보안을 강화할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aed01-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="aed01-105">ID 인프라를 이미 배포한 경우 [ID 종료 조건](identity-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="aed01-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="aed01-106">Microsoft 365 Enterprise ID 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="aed01-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="aed01-107">시작하기 전에 Microsoft 365에 대한 인증과 ID 모델의 개요에 대한 비디오를 시청하십시오.</span><span class="sxs-lookup"><span data-stu-id="aed01-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="aed01-p101">다음 단계를 사용하여 클라우드에서 새 ID 인프라를 계획 및 배포할 수 있습니다. 또한 이러한 단계를 사용하여 Microsoft 365 Enterprise와 함께 작동하도록 기존 온-프레미스 또는 하이브리드 ID 인프라를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed01-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="aed01-110">사용자 및 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="aed01-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="aed01-111">권한이 부여된 ID 보안</span><span class="sxs-lookup"><span data-stu-id="aed01-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="aed01-112">하이브리드 ID 구성</span><span class="sxs-lookup"><span data-stu-id="aed01-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="aed01-113">안전한 사용자 인증을 구성</span><span class="sxs-lookup"><span data-stu-id="aed01-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="aed01-114">사용자에 대한 액세스 간소화</span><span class="sxs-lookup"><span data-stu-id="aed01-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="aed01-115">더 쉬운 관리를 위한 그룹 사용</span><span class="sxs-lookup"><span data-stu-id="aed01-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="aed01-116">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](identity-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="aed01-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="aed01-117">ID 및 장치 액세스 권장 사항</span><span class="sxs-lookup"><span data-stu-id="aed01-117">Identity and device access recommendations</span></span>

<span data-ttu-id="aed01-p102">Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. ID을 확인하려면 다음 문서의 권장 사항 및 설정과 함께 이 작업 단계의 다음 단계를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="aed01-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="aed01-120">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aed01-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="aed01-121">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="aed01-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="aed01-122">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="aed01-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="aed01-123">Microsoft의 IT 전문가가 [ID와 보안 액세스를 관리하는 방법](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5)을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="aed01-123">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="aed01-124">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="aed01-124">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="aed01-125">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스를 위해 [Microsoft 용 하이브리드 ID 인프라를 구축](contoso-identity.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="aed01-125">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="aed01-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="aed01-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="aed01-127">사용자 및 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="aed01-127">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
