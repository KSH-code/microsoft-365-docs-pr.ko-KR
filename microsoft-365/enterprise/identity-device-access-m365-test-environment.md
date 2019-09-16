---
title: Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ID 및 장치 액세스를 테스트하는 Microsoft 365 환경을 만듭니다.
ms.openlocfilehash: c8d7aed1422f9d0c5891157e6fb7d3d30d976c4a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981899"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3faac-103">Microsoft 365 테스트 환경에 대한 ID 및 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="3faac-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3faac-104">[ID 및 장치 액세스 구성](microsoft-365-policies-configurations.md)은 Microsoft 365 Enterprise의 Office 365 및 Microsoft Intune 등 Azure Directory(Azure AD)와 통합된 모든 서비스에 대한 액세스를 보호하기 위한 일련의 기능 및 조건부 액세스 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3faac-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3faac-105">다음 정책을 적용한 테스트 환경을 만들기 위해서는 아래 내용을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3faac-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="3faac-106">선택한 ID 모델 및 인증 방법에 따라 필수 구성 요소 ID 및 보안 기능을 사용하여 테스트 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3faac-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="3faac-107">클라우드 전용</span><span class="sxs-lookup"><span data-stu-id="3faac-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="3faac-108">암호 해시 동기화(PHS)</span><span class="sxs-lookup"><span data-stu-id="3faac-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="3faac-109">통과 인증(PTA)</span><span class="sxs-lookup"><span data-stu-id="3faac-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="3faac-110">[일반 ID 및 장치 액세스 정책](identity-access-policies.md)을 사용하여 필수 구성 요소를 기반으로 구축되고 ID 및 장치 보호 기능을 테스트하는 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3faac-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="3faac-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3faac-111">See also</span></span>

[<span data-ttu-id="3faac-112">추가 ID 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="3faac-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="3faac-113">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="3faac-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="3faac-114">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="3faac-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3faac-115">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="3faac-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3faac-116">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="3faac-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
