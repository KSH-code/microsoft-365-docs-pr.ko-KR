---
title: 정보 보호 인프라 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 정보 보호 기반 서비스 및 인프라에 대한 조건을 검사하여 구성이 Microsoft 365 Enterprise 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870247"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="cb38d-103">정보 보호 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="cb38d-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="cb38d-104">기본 인프라를 완료하기 전에 정보 보호 인프라가 이러한 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="cb38d-105">필수: 조직의 보안 및 정보 보호 수준 정의</span><span class="sxs-lookup"><span data-stu-id="cb38d-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="cb38d-p101">조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="cb38d-108">최소한 다음 세 가지 보안 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="cb38d-109">기준</span><span class="sxs-lookup"><span data-stu-id="cb38d-109">Baseline</span></span>
- <span data-ttu-id="cb38d-110">중요</span><span class="sxs-lookup"><span data-stu-id="cb38d-110">Sensitive</span></span>
- <span data-ttu-id="cb38d-111">높은 규제</span><span class="sxs-lookup"><span data-stu-id="cb38d-111">Highly regulated</span></span>

<span data-ttu-id="cb38d-112">필요한 경우 [1단계](infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="cb38d-113">필수: Office 365에 대한 향상된 보안 구성</span><span class="sxs-lookup"><span data-stu-id="cb38d-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="cb38d-114">[향상된 보안을 위한 Office 365 테넌트 구성](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)의 정보를 바탕으로 향상된 보안을 위해 다음 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="cb38d-115">Office 365 보안 및 준수 센터의 위협 관리 정책</span><span class="sxs-lookup"><span data-stu-id="cb38d-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="cb38d-116">추가 Exchange Online 테넌트 수준 설정</span><span class="sxs-lookup"><span data-stu-id="cb38d-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="cb38d-117">SharePoint 관리 센터의 테넌트 수준 공유 정책</span><span class="sxs-lookup"><span data-stu-id="cb38d-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="cb38d-118">Azure Active Directory의 설정</span><span class="sxs-lookup"><span data-stu-id="cb38d-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="cb38d-119">또한 [Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="cb38d-120">필요한 경우 [3단계](infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="cb38d-121">선택: 전체 사용자 환경에서 분류 구성</span><span class="sxs-lookup"><span data-stu-id="cb38d-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="cb38d-122">법률 및 준수 팀과 함께 조직의 데이터에 대한 적절한 분류 및 레이블 지정 체계를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="cb38d-123">중요한 데이터 유형</span><span class="sxs-lookup"><span data-stu-id="cb38d-123">Sensitive data types</span></span>
- <span data-ttu-id="cb38d-124">Office 365 레이블</span><span class="sxs-lookup"><span data-stu-id="cb38d-124">Office 365 labels</span></span>
- <span data-ttu-id="cb38d-125">Azure Information Protection 레이블</span><span class="sxs-lookup"><span data-stu-id="cb38d-125">Azure Information Protection labels</span></span>

<span data-ttu-id="cb38d-126">필요한 경우 [2단계](infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="cb38d-127">선택 사항: Office 365의 권한이 부여된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="cb38d-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="cb38d-p102">[Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목의 정보를 사용하여 권한이 부여된 액세스를 사용하도록 설정하고 Office 365 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만듭니다. 이러한 정책을 구성했으며 중요한 데이터 액세스 또는 중요한 구성 설정 액세스를 위해 JIT(Just-In-Time) 액세스가 사용되도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="cb38d-130">필요한 경우 [4단계](infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="cb38d-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cb38d-131">Next Step</span></span>

<span data-ttu-id="cb38d-132">이제 Microsoft 365 Enterprise 기본 인프라에서 실행되는 [워크로드 및 시나리오](deploy-workloads.md)(예: Microsoft Teams 및 Exchange Online)를 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb38d-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
