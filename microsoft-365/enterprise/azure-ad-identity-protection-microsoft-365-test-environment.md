---
title: 엔터프라이즈 테스트 환경용 Microsoft 365 Azure AD Id 보호
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
description: Azure AD Id 보호를 구성 하 고 Microsoft 365에서 엔터프라이즈 테스트 환경에 대 한 현재 계정을 분석 합니다.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694993"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eb921-103">엔터프라이즈 테스트 환경용 Microsoft 365 Azure AD Id 보호</span><span class="sxs-lookup"><span data-stu-id="eb921-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eb921-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="eb921-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="eb921-105">Azure Active Directory (Azure AD) Id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="eb921-106">이 문서에서는 Azure AD Id 보호를 사용 하 여 테스트 환경 계정의 분석을 보는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="eb921-107">엔터프라이즈 테스트 환경용 Microsoft 365에서 Azure AD Id 보호를 설정 하는 단계는 다음 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="eb921-108">엔터프라이즈 테스트 환경용 Microsoft 365을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="eb921-109">Azure AD Id 보호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-109">Use Azure AD Identity Protection.</span></span>

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="eb921-111">[여기](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eb921-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="eb921-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eb921-113">최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="eb921-114">시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="eb921-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb921-115">Azure AD Id 보호를 테스트 하는 경우 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="eb921-116">Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="eb921-117">2 단계: Azure AD Id 보호 사용</span><span class="sxs-lookup"><span data-stu-id="eb921-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="eb921-118">브라우저의 개인 인스턴스를 열고 [https://portal.azure.com](https://portal.azure.com) 엔터프라이즈 테스트 환경에 대 한 Microsoft 365의 전역 관리자 계정을 사용 하 여 Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="eb921-119">Azure portal에서 검색 상자에 **id 보호** 를 입력 하 고 **Azure AD id 보호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="eb921-120">**Id 보호-개요** 블레이드에서 각 보고서를 클릭 하 여 보고 되는 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="eb921-121">**알림에서 감지 된 위험에 사용자** **를 클릭**합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="eb921-122">**위험 감지 됨 경고** 창에서 **보통**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="eb921-123">**다음 사용자에 게 전자 메일을 보내는**경우 **포함** 을 클릭 하 고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="eb921-124">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-124">Click **Save**.</span></span>

<span data-ttu-id="eb921-125">**보호** 에서 각 정책을 클릭 하 여 구성 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="eb921-126">정책을 만들고 활성화 하는 경우에는 조건의 범위가 너무 광범위 하 게 액세스를 차단 하지 않도록 하거나 전역 관리자 인 로그인을 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="eb921-127">추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb921-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="eb921-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="eb921-128">Next step</span></span>

<span data-ttu-id="eb921-129">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="eb921-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb921-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb921-130">See also</span></span>

[<span data-ttu-id="eb921-131">Id 로드맵</span><span class="sxs-lookup"><span data-stu-id="eb921-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="eb921-132">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="eb921-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eb921-133">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="eb921-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="eb921-134">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb921-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
