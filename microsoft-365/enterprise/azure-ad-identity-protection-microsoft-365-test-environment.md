---
title: Azure AD Id 보호 Microsoft 365 기업에 대 한 테스트 환경
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 기업 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869803"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="285ca-103">Azure AD Id 보호 Microsoft 365 기업에 대 한 테스트 환경</span><span class="sxs-lookup"><span data-stu-id="285ca-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="285ca-p101">Azure AD Id 보호를 사용 하면 조직의 id가 영향을 줄 수 있는 잠재적인 취약점 검색, 자동된 응답을 구성 하 고, 문제를 조사할 수 있습니다. 이 문서에서는 Azure AD Id 보호를 설정 하 고 테스트 환경 계정의 분석을 볼 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="285ca-106">Microsoft 365 기업 테스트 환경에서 Azure AD Id 보호를 설정 하는 두 단계로 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="285ca-107">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="285ca-108">사용 하도록 설정 하 고 Azure AD Id 보호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="285ca-110">[여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="285ca-111">1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다</span><span class="sxs-lookup"><span data-stu-id="285ca-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="285ca-112">최소 요구 사항을 경량 방식으로 Azure AD Id 보호를 테스트 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="285ca-113">시뮬레이션 된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="285ca-p102">Azure AD Id 보호를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 제공 되 Azure AD Id 보호를 테스트 하 고 일반적인 조직을 대표 하는 환경에서 사용해 수 있도록 하는 옵션으로 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="285ca-116">2 단계:을 설정 하 고 Azure AD Id 보호를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="285ca-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="285ca-117">브라우저의 개인 인스턴스를 열고에서 Azure 포털에 로그인 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="285ca-118">Azure 포털에서 클릭 **모든 서비스 > 마켓플레이스**합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="285ca-119">**Azure AD Id 보호** 를 입력 하 고을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="285ca-120">**시작** 블레이드에서 **설정**아래에서 **온보드** 를 클릭 하 **대시보드에 고정을**클릭 한 다음 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="285ca-121">Azure 포털에서 대시보드에서 **Azure AD Id 보호** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="285ca-p103">대시보드로 **Azure AD Id 보호 개요** 블레이드가 표시 됩니다. **취약점**다단계 인증 등록 하지 않고 사용자 계정 수를 결정 되도록를 확인 합니다. 이 번호는 이전 Microsoft 365 Enterprise 테스트 랩 가이드를 수행한 상태 여야에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="285ca-125">**조사** 를 모든 사용자 또는 검색 된 이벤트 참조에 대 한 범주를 통해이 옵션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="285ca-126">추가 테스트 및 실험 [Simulating 위험 이벤트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="285ca-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="285ca-127">정보 및 프로덕션 환경에서 Azure AD Id 보호를 배포에 대 한 링크에 대 한 Identity 단계에서 [손상 암호로 보호 자격 증명에 대 한](identity-azure-ad-identity-protection.md) 단계를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="285ca-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="285ca-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="285ca-128">Next step</span></span>

<span data-ttu-id="285ca-129">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="285ca-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="285ca-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="285ca-130">See also</span></span>

[<span data-ttu-id="285ca-131">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="285ca-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="285ca-132">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="285ca-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="285ca-133">Microsoft 365 엔터프라이즈 배포</span><span class="sxs-lookup"><span data-stu-id="285ca-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="285ca-134">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="285ca-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
