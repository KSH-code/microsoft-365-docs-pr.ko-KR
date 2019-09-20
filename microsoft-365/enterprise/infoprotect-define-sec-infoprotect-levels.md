---
title: '1단계: 보안 및 정보 보호 수준 정의'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 조직의 보안 및 정보 보호 수준을 이해하고 구성합니다.
ms.openlocfilehash: a216079e38b173a8b35c49317a072975b0c7f36e
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047261"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="becb2-103">1단계: 보안 및 정보 보호 수준 정의</span><span class="sxs-lookup"><span data-stu-id="becb2-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="becb2-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="becb2-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="becb2-105">이 단계에서는 조직의 보안 및 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-105">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="becb2-106">예를 들어 판매 부서는 낮은 보안 수준만 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-106">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="becb2-107">그러나 연구 부서와 연구 부서의 매우 중요한 지적 재산은 파일을 암호화하고 연구원만 액세스할 수 있도록 높은 보안 수준을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-107">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="becb2-108">사용자 고유의 보안 수준을 정의하고 일부는 이미 적용되고 있을 수 있지만 적용 가능한 세 가지 이상의 보안 및 보호 수준을 사용할 계획을 수립하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-108">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="becb2-109">시작하기 위한 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-109">Here is a list to get you started:</span></span> 

- <span data-ttu-id="becb2-p103">**기준:** 데이터 보호 및 데이터에 액세스하는 장치와 ID에 대한 최소 기준입니다. 기준 보안 및 보호 권장 사항에 따라 많은 조직이나 해당 부서의 요구 사항을 충족하는 강력한 기본 보호를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="becb2-p104">**중요:** 기준 수준을 넘어 보호해야 하는 데이터의 하위 집합에 대한 추가 보호입니다. Office 365 환경의 특정 데이터 집합에 이 강화된 보호를 적용할 수 있습니다. 또한 중요한 데이터에 액세스하는 ID 및 장치에도 중요 보안 수준을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="becb2-p105">**높은 규제:** 일반적으로 고도로 분류되고 지적 재산 또는 영업 비밀로 간주되는 극소량의 데이터 또는 엄격한 보안 규정을 준수해야 하는 데이터가 있는 조직에 대한 최고 보안 수준입니다. Microsoft 365 Enterprise에는 조직이 ID 및 장치에 대한 상응하는 보호를 포함하여 이러한 높은 보안 요구 사항을 충족하도록 도와주는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="becb2-117">자세한 내용은 [보호의 3계층](microsoft-365-policies-configurations.md#three-tiers-of-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="becb2-117">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="becb2-118">중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step1)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="becb2-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="becb2-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="becb2-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="becb2-120">사용자 환경에 대한 분류 구성</span><span class="sxs-lookup"><span data-stu-id="becb2-120">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
