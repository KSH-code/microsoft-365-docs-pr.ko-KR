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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487711"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3cd2c-103">엔터프라이즈 테스트 환경용 Microsoft 365 Azure AD Id 보호</span><span class="sxs-lookup"><span data-stu-id="3cd2c-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3cd2c-104">*이 테스트 랩 가이드는 엔터프라이즈 테스트 환경용 Microsoft 365에만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="3cd2c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3cd2c-105">Azure Active Directory (Azure AD) Id 보호를 사용 하 여 조직의 id에 영향을 주는 잠재적 취약성을 검색 하 고 자동화 된 응답을 구성 하 고 인시던트를 조사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="3cd2c-106">이 문서에서는 Azure AD Id 보호를 사용 하 여 테스트 환경 계정의 분석을 보는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="3cd2c-107">엔터프라이즈 테스트 환경용 Microsoft 365에서 Azure AD Id 보호를 설정 하는 작업은 다음 두 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="3cd2c-108">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="3cd2c-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3cd2c-109">2 단계: Azure AD Id 보호 사용</span><span class="sxs-lookup"><span data-stu-id="3cd2c-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3cd2c-111">엔터프라이즈 테스트 랩 가이드 스택의 Microsoft 365에 있는 모든 문서에 대 한 시각적 지도를 보려면 [microsoft 365 for 엔터프라이즈 테스트 랩 가이드 스택을](../downloads/Microsoft365EnterpriseTLGStack.pdf)방문 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3cd2c-112">1 단계: 엔터프라이즈 테스트 환경용 Microsoft 365 구축</span><span class="sxs-lookup"><span data-stu-id="3cd2c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3cd2c-113">최소 요구 사항에 따라 간단한 방법으로 Azure AD Id 보호를 테스트 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3cd2c-114">시뮬레이트된 엔터프라이즈에서 Azure AD Id 보호를 테스트 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cd2c-115">Azure AD Id 보호를 테스트 하려면 AD DS (Active Directory 도메인 서비스) 포리스트의 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3cd2c-116">Azure AD Id 보호를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에 제공 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="3cd2c-117">2 단계: Azure AD Id 보호 사용</span><span class="sxs-lookup"><span data-stu-id="3cd2c-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="3cd2c-118">브라우저의 개인 인스턴스를 열고 [https://portal.azure.com](https://portal.azure.com) 엔터프라이즈 테스트 환경에 대 한 Microsoft 365의 전역 관리자 계정을 사용 하 여 Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="3cd2c-119">Azure portal에서 검색 상자에 **id 보호** 를 입력 한 다음 **Azure AD id 보호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="3cd2c-120">**Id 보호-개요** 블레이드에서 각 보고서를 선택 하 여 보고 되는 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="3cd2c-121">**알림에서 감지 된 위험에서 사용자** **를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3cd2c-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="3cd2c-122">**위험 감지 됨 경고** 창에서 **보통**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="3cd2c-123">**다음 사용자에 게 전자 메일을 보내는**경우 **포함** 을 선택 하 고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="3cd2c-124">**저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-124">Select **Save**.</span></span>

<span data-ttu-id="3cd2c-125">**보호**에서 다양 한 정책을 선택 하 여 구성 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="3cd2c-126">정책을 만들고 활성화 하는 경우에는 모든 사용자에 대 한 액세스를 차단 하지 않는지 또는 로그인 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="3cd2c-127">이를 방지 하려면 전역 관리자와 같은 특정 사용자 계정을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="3cd2c-128">추가 테스트 및 실험을 위해 [위험 이벤트 시뮬레이트](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="3cd2c-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3cd2c-129">Next step</span></span>

<span data-ttu-id="3cd2c-130">테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3cd2c-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cd2c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cd2c-131">See also</span></span>

[<span data-ttu-id="3cd2c-132">Id 로드맵</span><span class="sxs-lookup"><span data-stu-id="3cd2c-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3cd2c-133">엔터프라이증용 Microsoft 365 테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="3cd2c-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3cd2c-134">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="3cd2c-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3cd2c-135">엔터프라이즈 설명서에 대 한 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cd2c-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
