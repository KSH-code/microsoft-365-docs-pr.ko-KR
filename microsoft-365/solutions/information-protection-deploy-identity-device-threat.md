---
title: 데이터 개인 정보 보호 규정에 ID, 장치 및 위협 방지 사용
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 개인 데이터의 ID, 장치 및 위협 방지 서비스를 사용하여 개인 데이터 침해를 Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199468"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="113ae-103">데이터 개인 정보 보호 규정에 ID, 장치 및 위협 방지 사용</span><span class="sxs-lookup"><span data-stu-id="113ae-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="113ae-104">Microsoft 365 조직이 데이터 개인 정보 관련 규정 준수 규정을 준수하는 데 사용할 수 있는 다양한 ID, 장치 및 위협 방지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="113ae-105">이 문서에서는 이러한 영역에 필요한 데이터 개인 정보 규정에 대해 설명하고 구현 요구 사항을 충족하는 데 도움이 되는 Microsoft 365 관련 Microsoft 365 기능 및 서비스의 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="113ae-106">ID, 장치 및 위협 방지와 데이터 개인 정보 보호 규정의 관계</span><span class="sxs-lookup"><span data-stu-id="113ae-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="113ae-107">데이터 개인 정보 보호 규정은 특정성에 따라 다르지만, 이러한 규정의 본질은 GDPR의 제5조(1)(f)에 구체화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="113ae-108">개인 데이터는 적절한 기술 또는 조직적 조치('무결성 및 기밀성')를 사용하여 무단 또는 불법적인 처리 및 우발적인 손실, 파괴 또는 손상으로부터 보호를 포함하여 개인 데이터의 적절한 보안을 보장하는 방식으로 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="113ae-109">개인 데이터 침해는 종종 관리 또는 최종 사용자 계정 손상 및 악의적인 시스템 액세스로 인해 발생하기 때문에</span><span class="sxs-lookup"><span data-stu-id="113ae-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="113ae-110">예를 들어 관리자 계정 해킹으로 인해 고객 신용 카드 번호 또는 기타 개인 정보가 유출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="113ae-111">사용자와 함께 사용할 수 있는 일반적으로 Microsoft 365, 장치 및 위협 보호를 구현해야 합니다. 이는 준수 관리자에 있는 준수 점수에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="113ae-112">평가 작업 및 준수 관리자의 결과 사용</span><span class="sxs-lookup"><span data-stu-id="113ae-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="113ae-113">준수 관리자에는 다음 범주를 사용하는 ID, 장치 및 위협 방지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="113ae-114">ID는 컨트롤 액세스 **범주에 해당합니다.**</span><span class="sxs-lookup"><span data-stu-id="113ae-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="113ae-115">디바이스 관리 **범주에 해당합니다.**</span><span class="sxs-lookup"><span data-stu-id="113ae-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="113ae-116">위협 방지는 위협으로부터 보호 **범주에** 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="113ae-117">4개의 주요 데이터 개인 정보 보호 규정 샘플 집합에서 이러한 설정을 선택한 경우 준수 관리자는 90개의 개선 작업을 지정합니다. 이 중 대부분은 "27"으로 점수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="113ae-118">이러한 범주에 대해 준수 관리자가 이러한 많은 수를 호출하기 때문에 참조를 위해 더 일반적인 항목 중 일부가 여기에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="113ae-119">ID [Azure Active Directory(Azure AD)를](https://azure.microsoft.com/services/active-directory/) 사용하여  다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="113ae-120">재생 방지 인증 구현("중간에 있는 사람" 공격을 방지)</span><span class="sxs-lookup"><span data-stu-id="113ae-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="113ae-121">레거시 인증을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-121">Block legacy authentication.</span></span>
- <span data-ttu-id="113ae-122">사용자 위험 및 사용자 로그인 위험 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="113ae-123">관리자 및 비 관리자에 대해 조건부 액세스 및 MFA(다단계 인증)를 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="113ae-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="113ae-124">암호 정책을 구성하고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="113ae-125">Azure AD 계정을 사용하여 권한 있는 계정에 대한 액세스를 Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="113ae-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="113ae-126">종료 시 액세스를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="113ae-126">Disable access upon termination.</span></span>
- <span data-ttu-id="113ae-127">사용자 계정 및 상태 변경 감사</span><span class="sxs-lookup"><span data-stu-id="113ae-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="113ae-128">역할 그룹 및 관리 변경 내용을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="113ae-129">다음 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 장치 및 **장치** 관리 범주에 대해 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="113ae-130">끊어지고 루팅된 모바일 장치를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="113ae-131">모바일 장치 관리를 위해 Intune을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="113ae-132">Android, iOS, macOS 및 Windows 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="113ae-133">Android, iOS, macOS 및 장치용 장치 구성 프로필을 Windows.</span><span class="sxs-lookup"><span data-stu-id="113ae-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="113ae-134">iOS 및 앱에 대한 앱 보호 정책을 Windows.</span><span class="sxs-lookup"><span data-stu-id="113ae-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="113ae-135">잠금 화면으로 정보를 은신합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="113ae-136">모바일 장치에 대한 암호 정책을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="113ae-137">모바일 장치가 비활성에 잠겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="113ae-138">모바일 장치에서 여러 로그인 실패 시 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="113ae-139">위협 Exchange Online Protection 범주에 대해 Office 365 및 Microsoft  [Defender를](../security/office-365-security/defender-for-office-365.md) 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="113ae-140">보낸 사람 인증(SPF, DMARC 및 DKIM)을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="113ae-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="113ae-141">피싱 방지 정책에 Office 365 Microsoft Defender를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="113ae-142">안전한 첨부 파일을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="113ae-143">안전한 링크를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-143">Implement Safe Links.</span></span>
- <span data-ttu-id="113ae-144">맬웨어 검색 및 응답 정책을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="113ae-145">아웃바운드 및 인바운드 스팸 정책을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="113ae-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="113ae-146">참조:</span><span class="sxs-lookup"><span data-stu-id="113ae-146">References:</span></span>

- [<span data-ttu-id="113ae-147">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="113ae-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="113ae-148">보안 위협으로부터 Office 365</span><span class="sxs-lookup"><span data-stu-id="113ae-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="113ae-149">안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="113ae-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="113ae-150">안전한 링크</span><span class="sxs-lookup"><span data-stu-id="113ae-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="113ae-151">안전한 문서</span><span class="sxs-lookup"><span data-stu-id="113ae-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
