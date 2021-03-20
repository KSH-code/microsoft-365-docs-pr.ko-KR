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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907471"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f36d0-103">Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="f36d0-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f36d0-104">*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="f36d0-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f36d0-105">[ID 및 장치 액세스 구성은](../security/office-365-security/microsoft-365-policies-configurations.md) Azure AD(Azure Active Directory)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 권장 구성 및 조건부 액세스 정책 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f36d0-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="f36d0-106">공통 ID 및 장치 액세스 구성이 적용된 테스트 환경을 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="f36d0-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="f36d0-107">선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f36d0-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="f36d0-108">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="f36d0-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="f36d0-109">PHS(암호 해시 동기화)</span><span class="sxs-lookup"><span data-stu-id="f36d0-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="f36d0-110">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="f36d0-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="f36d0-111">일반 [ID](../security/office-365-security/identity-access-policies.md) 및 장치 액세스 정책을 사용하여 테스트 환경에 대해 구성된 선행 구성을 토대한 정책을 구성하고 ID 및 장치에 대한 보호를 탐색하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f36d0-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f36d0-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f36d0-112">See also</span></span>

[<span data-ttu-id="f36d0-113">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f36d0-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="f36d0-114">ID 로드맵</span><span class="sxs-lookup"><span data-stu-id="f36d0-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f36d0-115">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="f36d0-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f36d0-116">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="f36d0-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f36d0-117">기업용 Microsoft 365 설명서</span><span class="sxs-lookup"><span data-stu-id="f36d0-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)