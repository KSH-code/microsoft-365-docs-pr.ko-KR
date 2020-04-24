---
title: '6단계: 정보 보호'
f1.keywords:
- NOCSH
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
description: Microsoft 365 Enterprise에 대한 정보 보호 인프라를 배포하는 단계입니다.
ms.openlocfilehash: 0e6fdf1a9c63200bfb57fc9f833515553c1609f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631624"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="715d0-103">6단계: 정보 보호</span><span class="sxs-lookup"><span data-stu-id="715d0-103">Phase 6: Information protection</span></span>

![6단계: 정보 보호](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="715d0-p101">정보 보호는 중요한 정보를 전송, 저장 및 처리하는 방법을 정의하는 정책 및 기술 집합입니다. 6단계에서는 클라우드 기반 워크로드 및 시나리오의 데이터를 보호하는 데 유용한 Microsoft 365 Enterprise의 정보 보호 설정 및 기능을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="715d0-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="715d0-107">정보 보호를 이미 배포한 경우 이 단계에 대한 [종료 조건](infoprotect-exit-criteria.md)을 검토하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="715d0-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="715d0-108">Microsoft 365 Enterprise 정보 보호 인프라 계획 및 배포</span><span class="sxs-lookup"><span data-stu-id="715d0-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="715d0-p102">법률 및 준수 팀과 협력하여 조직에서 HIPPA, CJIS 또는 GDPR과 같은 준수 표준을 충족해야 하는지 확인해야 합니다. 또한 보안 그룹과 협력하여 조직과 추가 보안이 필요한 부서나 그룹의 정보 보호 목표를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="715d0-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="715d0-111">이제 다음 단계를 사용하여 Microsoft 365 Enterprise에 대한 정보 보호를 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="715d0-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![1단계](../media/stepnumbers/Step1.png)|[<span data-ttu-id="715d0-113">보안 및 정보 보호 수준 정의</span><span class="sxs-lookup"><span data-stu-id="715d0-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![2단계](../media/stepnumbers/Step2.png)|[<span data-ttu-id="715d0-115">사용자 환경에 대한 분류 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![3단계](../media/stepnumbers/Step3.png)|[<span data-ttu-id="715d0-117">Microsoft 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![4단계](../media/stepnumbers/Step4.png)|[<span data-ttu-id="715d0-119">WIP(Windows Information Protection) 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![5단계](../media/stepnumbers/Step5.png)|[<span data-ttu-id="715d0-121">데이터 손실 방지 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![6단계](../media/stepnumbers/Step6.png)|[<span data-ttu-id="715d0-123">전자 메일 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![7단계](../media/stepnumbers/Step7.png)|[<span data-ttu-id="715d0-125">Office 365에 대한 권한이 부여된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="715d0-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="715d0-126">이러한 단계를 완료했으면 이 단계에 대한 [종료 조건](infoprotect-exit-criteria.md)으로 이동하여 Microsoft 365 Enterprise에 대한 필수 및 선택적 조건을 충족하는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="715d0-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="715d0-127">Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="715d0-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="715d0-128">Microsoft의 IT 전문가가 [Azure Information Protection을 사용하고 데이터를 보호](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="715d0-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="715d0-129">Contoso의 Microsoft 365 Enterprise 사용 방식</span><span class="sxs-lookup"><span data-stu-id="715d0-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="715d0-130">가상의 대표적 다국적 기업인 Contoso Corporation이 Microsoft 365 클라우드 서비스에 맞게 [정보 보호를 구현](contoso-info-protect.md)한 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="715d0-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="715d0-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="715d0-132">Next step</span></span>

|||
|:-------|:-----|
|![1단계](../media/stepnumbers/Step1.png)|[<span data-ttu-id="715d0-134">보안 및 정보 보호 수준 정의</span><span class="sxs-lookup"><span data-stu-id="715d0-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

