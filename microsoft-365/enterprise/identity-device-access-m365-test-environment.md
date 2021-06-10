---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: 5a9e9ef9ea6b8f6dc80aa7fea225f3573b8fcadc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197878"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5d754-103">Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="5d754-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5d754-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경에 Microsoft 365 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="5d754-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5d754-105">[ID 및 장치 액세스](../security/office-365-security/microsoft-365-policies-configurations.md) 구성은 Azure AD(Azure AD)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 권장 구성 및 조건부 액세스 Azure Active Directory 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="5d754-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="5d754-106">공통 ID 및 장치 액세스 구성이 적용된 테스트 환경을 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="5d754-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="5d754-107">선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d754-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="5d754-108">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="5d754-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="5d754-109">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="5d754-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="5d754-110">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="5d754-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="5d754-111">일반 [ID](../security/office-365-security/identity-access-policies.md) 및 장치 액세스 정책을 사용하여 테스트 환경에 대해 구성된 선행 구성을 토대한 정책을 구성하고 ID 및 장치에 대한 보호를 탐색하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d754-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d754-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d754-112">See also</span></span>

[<span data-ttu-id="5d754-113">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="5d754-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5d754-114">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="5d754-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5d754-115">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="5d754-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5d754-116">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="5d754-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5d754-117">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="5d754-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
