---
title: 정보 보호 인프라 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 정보 보호 기반 서비스 및 인프라에 대한 조건을 검사하여 구성이 Microsoft 365 Enterprise 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 267a6efaef5a5bcfb0ec9f8e0e9f33d525f5ce74
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071948"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="c3d13-103">정보 보호 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="c3d13-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c3d13-104">정보 보호 인프라를 다음과 같은 필수 조건 및 선택 요소에 확실히 충족하도록 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3d13-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="c3d13-105">필수: 조직의 보안 및 정보 보호 수준 정의</span><span class="sxs-lookup"><span data-stu-id="c3d13-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="c3d13-p101">조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="c3d13-108">최소한 다음 세 가지 보안 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="c3d13-109">기준</span><span class="sxs-lookup"><span data-stu-id="c3d13-109">Baseline</span></span>
- <span data-ttu-id="c3d13-110">중요</span><span class="sxs-lookup"><span data-stu-id="c3d13-110">Sensitive</span></span>
- <span data-ttu-id="c3d13-111">높은 규제</span><span class="sxs-lookup"><span data-stu-id="c3d13-111">Highly regulated</span></span>

<span data-ttu-id="c3d13-112">필요한 경우 [1단계](infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="c3d13-113">필수: Microsoft 365에 대한 강화된 보안이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="c3d13-114">[Office 365 보안 강화](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)를 위해 다음과 같은 설정을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="c3d13-115">Microsoft 365 보안 센터의 위협 관리 정책</span><span class="sxs-lookup"><span data-stu-id="c3d13-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="c3d13-116">추가 Exchange Online 테넌트 수준 설정</span><span class="sxs-lookup"><span data-stu-id="c3d13-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="c3d13-117">SharePoint Online 관리 센터의 테넌트 정체 공유 정책</span><span class="sxs-lookup"><span data-stu-id="c3d13-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="c3d13-118">Azure Active Directory(Azure AD)의 설정</span><span class="sxs-lookup"><span data-stu-id="c3d13-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="c3d13-119">또한 [SharePoint, OneDrive 및 Microsoft Teams를 위해 Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="c3d13-120">필요한 경우 [3단계](infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="c3d13-121">선택: 전체 사용자 환경에서 분류 구성</span><span class="sxs-lookup"><span data-stu-id="c3d13-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="c3d13-122">법률 및 준수 팀과 함께 조직의 데이터 거버넌스 및 보안 정책을 위한 적합한 분류 및 레이블 지정 체계를 개발하기 위해 작업하였습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="c3d13-123">해당 정책은 다음과 같은 구성 및 배포에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="c3d13-124">중요한 데이터 유형</span><span class="sxs-lookup"><span data-stu-id="c3d13-124">Sensitive data types</span></span>
- <span data-ttu-id="c3d13-125">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="c3d13-125">Retention labels</span></span>
- <span data-ttu-id="c3d13-126">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="c3d13-126">Sensitivity labels</span></span>
- <span data-ttu-id="c3d13-127">Azure Information Protection 레이블</span><span class="sxs-lookup"><span data-stu-id="c3d13-127">Azure Information Protection labels</span></span>

<span data-ttu-id="c3d13-128">필요한 경우 [2단계](infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="c3d13-129">선택 사항: Windows Information Protection이 환경 전체에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="c3d13-130">등록된 Windows 10 Enterprise 장치에 다음을 정의하는 Intune 정책이 배포되고 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="c3d13-131">보호할 앱 유형.</span><span class="sxs-lookup"><span data-stu-id="c3d13-131">Which apps to protect.</span></span>
- <span data-ttu-id="c3d13-132">보호 수준.</span><span class="sxs-lookup"><span data-stu-id="c3d13-132">The level of protection.</span></span>
- <span data-ttu-id="c3d13-133">보호를 확장하는 위치.</span><span class="sxs-lookup"><span data-stu-id="c3d13-133">Where the protection extends.</span></span>

<span data-ttu-id="c3d13-134">필요한 경우, [4단계](infoprotect-deploy-windows-information-protection.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="c3d13-135">선택 사항: Office 365 DLP(Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="c3d13-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="c3d13-136">조직이 고객과 기타 개인 데이터 유형을 보호하고 산업 및 지역 규정과 요구 사항을 준수하는 데 필요한 DLP 정책 집합(위치 및 조건과 조치과 포함된 규칙 사용)을 분석하고 테스트하며 공개했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="c3d13-137">데이터 준수 및 보안 교직원이 Office 365 보안 및 준수 대시보드를 사용하여 DLP 인시던트를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="c3d13-138">필요한 경우 [5단계](infoprotect-data-loss-prevention.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="c3d13-139">선택 사항: Office 365의 권한이 부여된 액세스 관리 구성</span><span class="sxs-lookup"><span data-stu-id="c3d13-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="c3d13-140">권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들어내기 위해 [Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)의 정보를 사용하였습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="c3d13-141">이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 적기에 맞는 액세스가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="c3d13-142">필요한 경우 [6단계](infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-142">If needed, [Step 6](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="c3d13-143">결과 및 다음 단계</span><span class="sxs-lookup"><span data-stu-id="c3d13-143">Results and next steps</span></span>

<span data-ttu-id="c3d13-144">Microsoft 365 Enterprise에 대한 정보 보호 인프라에서는 정의된 보안 수준, Office 365를 위한 강화된 보안, 중요한 데이터 형식 및 레이블을 사용하는 분류, WIP(Windows Information Protection), 데이터 손실 방지 및 권한이 부여된 액세스 관리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="c3d13-145">Microsoft 365 Enterprise의 종단 간 배포를 따른다면 [워크 로드 및 시나리오](deploy-workloads.md)가 모든 기능 및 기초 인프라의 구성을 이용하도록 해줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3d13-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
