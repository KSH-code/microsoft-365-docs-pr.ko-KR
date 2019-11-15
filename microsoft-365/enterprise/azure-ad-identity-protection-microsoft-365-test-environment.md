---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 Enterprise 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: a21b20f4ca774ad38990e44abc18d666426e74d5
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640407"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4bbf1-103">Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호</span><span class="sxs-lookup"><span data-stu-id="4bbf1-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4bbf1-104">Azure AD Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="4bbf1-105">이 문서에서는 Azure AD Id 보호를 사용 하도록 설정 하 고 테스트 환경 계정에 대 한 분석을 보는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="4bbf1-106">Microsoft 365 Enterprise 테스트 환경에서 Azure AD Id 보호를 설정 하는 데는 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="4bbf1-107">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4bbf1-108">Azure AD Id 보호를 사용 하도록 설정 하 고 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4bbf1-110">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4bbf1-111">1 단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="4bbf1-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4bbf1-112">최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4bbf1-113">시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4bbf1-114">Azure AD Id 보호를 테스트 하는 경우에는 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4bbf1-115">Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="4bbf1-116">2 단계: Azure AD Id 보호 사용 및 사용</span><span class="sxs-lookup"><span data-stu-id="4bbf1-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="4bbf1-117">브라우저의 개인 인스턴스를 열고 Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4bbf1-118">Azure portal에서 **모든 서비스 >** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="4bbf1-119">**AZURE AD Id 보호** 를 입력 한 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="4bbf1-120">**시작** 블레이드에서 **설정**아래의 **온보드** 를 클릭 하 고 **대시보드에 고정**을 클릭 한 다음 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="4bbf1-121">Azure portal에서 대시보드의 **AZURE AD Id 보호** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="4bbf1-122">대시보드의 **AZURE AD Id 보호-개요** 블레이드에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="4bbf1-123">**취약성**에 따라 다단계 인증 등록이 없는 사용자 계정 수를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="4bbf1-124">이 숫자는 이전에 수행한 Microsoft 365 Enterprise 테스트 랩 가이드에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="4bbf1-125">**조사** 를 위해 범주를 클릭 하 여 검색 된 사용자 또는 이벤트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="4bbf1-126">추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="4bbf1-127">프로덕션 환경에서 Azure AD Id 보호를 배포 하는 방법에 대 한 자세한 내용은 Id 단계의 [자격 증명 손상 보호](identity-secure-user-sign-ins.md#identity-ident-prot) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-127">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="4bbf1-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4bbf1-128">Next step</span></span>

<span data-ttu-id="4bbf1-129">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf1-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bbf1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4bbf1-130">See also</span></span>

[<span data-ttu-id="4bbf1-131">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="4bbf1-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4bbf1-132">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="4bbf1-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4bbf1-133">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="4bbf1-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4bbf1-134">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="4bbf1-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
