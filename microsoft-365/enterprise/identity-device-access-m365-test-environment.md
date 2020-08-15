---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685857"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="937d1-103">Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="937d1-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="937d1-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="937d1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="937d1-105">[Id 및 장치 액세스 구성은](microsoft-365-policies-configurations.md) Azure Active Directory (azure AD)와 통합 된 모든 서비스에 대 한 액세스를 보호 하기 위한 기능 및 조건부 액세스 정책의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="937d1-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="937d1-106">다음 정책을 적용한 테스트 환경을 만들기 위해서는 아래 내용을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="937d1-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="937d1-107">선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="937d1-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="937d1-108">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="937d1-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="937d1-109">암호 해시 동기화(PHS)</span><span class="sxs-lookup"><span data-stu-id="937d1-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="937d1-110">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="937d1-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="937d1-111">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치 보호 기능을 테스트하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="937d1-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="937d1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="937d1-112">See also</span></span>

[<span data-ttu-id="937d1-113">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="937d1-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="937d1-114">Id 로드맵</span><span class="sxs-lookup"><span data-stu-id="937d1-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="937d1-115">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="937d1-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="937d1-116">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="937d1-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="937d1-117">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="937d1-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
