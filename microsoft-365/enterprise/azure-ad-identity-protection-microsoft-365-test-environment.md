---
title: Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Id 보호를 구성 하 고 Microsoft 365 Enterprise 테스트 환경에서 현재 계정을 분석 합니다.
ms.openlocfilehash: 376fc838191314e93ae37accb7fc5066456499fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597165"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9fb19-103">Microsoft 365 Enterprise 테스트 환경에 대 한 Azure AD Id 보호</span><span class="sxs-lookup"><span data-stu-id="9fb19-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9fb19-104">*이 테스트 랩 가이드는 Microsoft 365 Enterprise 테스트 환경에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="9fb19-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9fb19-105">Azure Active Directory (Azure AD) Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="9fb19-106">이 문서에서는 Azure AD Id 보호를 사용 하 여 테스트 환경 계정의 분석을 보는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="9fb19-107">Microsoft 365 Enterprise 테스트 환경에서 Azure AD Id 보호를 설정 하는 데는 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="9fb19-108">Microsoft 365 Enterprise 테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="9fb19-109">Azure AD Id 보호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-109">Use Azure AD Identity Protection.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9fb19-111">[여기](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9fb19-112">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="9fb19-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9fb19-113">최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9fb19-114">시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9fb19-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fb19-115">Azure AD Id 보호를 테스트 하는 경우 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9fb19-116">Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="9fb19-117">2 단계: Azure AD Id 보호 사용</span><span class="sxs-lookup"><span data-stu-id="9fb19-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="9fb19-118">브라우저의 개인 인스턴스를 열고 Microsoft 365 Enterprise 테스트 환경의 전역 관리자 계정을 [https://portal.azure.com](https://portal.azure.com) 사용 하 여 Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="9fb19-119">Azure portal에서 검색 상자에 **id 보호** 를 입력 하 고 **Azure AD id 보호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="9fb19-120">**Id 보호-개요** 블레이드에서 각 보고서를 클릭 하 여 보고 되는 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="9fb19-121">**알림에서 감지 된 위험에 사용자** **를 클릭**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="9fb19-122">**위험 감지 됨 경고** 창에서 **보통**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="9fb19-123">**다음 사용자에 게 전자 메일을 보내는**경우 **포함** 을 클릭 하 고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="9fb19-124">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-124">Click **Save**.</span></span>

<span data-ttu-id="9fb19-125">**보호** 에서 각 정책을 클릭 하 여 구성 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="9fb19-126">정책을 만들고 활성화 하는 경우에는 조건의 범위가 너무 광범위 하 게 액세스를 차단 하지 않도록 하거나 전역 관리자 인 로그인을 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="9fb19-127">추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb19-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="9fb19-128">프로덕션 환경에서 Azure AD Id 보호를 배포 하는 방법에 대 한 자세한 내용은 Id 단계의 [자격 증명 손상 보호](identity-secure-user-sign-ins.md#identity-ident-prot) 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb19-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="9fb19-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9fb19-129">Next step</span></span>

<span data-ttu-id="9fb19-130">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb19-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fb19-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fb19-131">See also</span></span>

[<span data-ttu-id="9fb19-132">2단계: ID</span><span class="sxs-lookup"><span data-stu-id="9fb19-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9fb19-133">Microsoft 365 Enterprise 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="9fb19-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9fb19-134">Microsoft 365 Enterprise 배포</span><span class="sxs-lookup"><span data-stu-id="9fb19-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9fb19-135">Microsoft 365 Enterprise 설명서</span><span class="sxs-lookup"><span data-stu-id="9fb19-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
