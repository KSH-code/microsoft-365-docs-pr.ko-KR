---
title: 데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용
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
description: Microsoft 365의 id, 장치 및 위협 보호 서비스를 통해 개인 데이터 위반을 방지 합니다.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377060"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="57d50-103">데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용</span><span class="sxs-lookup"><span data-stu-id="57d50-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="57d50-104">Microsoft 365에서는 조직에서 데이터 개인 정보 관련 규정 준수 규정을 준수 하는 데 사용할 수 있는 다양 한 id, 장치 및 위협 보호 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="57d50-105">이 문서에서는 이러한 분야에 필요한 데이터 개인 정보 규정에 대해 설명 하 고, 구현 요구 사항을 해결 하는 데 도움이 되는 자세한 정보에 대 한 링크와 함께 관련 Microsoft 365 기능 및 서비스의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="57d50-106">Id, 장치 및 위협 보호와 데이터 개인 정보 규정의 관계</span><span class="sxs-lookup"><span data-stu-id="57d50-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="57d50-107">데이터 개인 정보 규정은 해당 복구 단위에 따라 달라 지는 하지만, 다음을 나타내는 GDPR의 문서 5 (1) (f)에서 해당 사용자의 통화에 대 한 에센스를 embodied 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="57d50-108">개인 데이터는 무단 또는 불법적 처리, 우발적 손실, 파괴 또는 손상에 대 한 보호, 적절 한 기술 또는 조직적 조치 (' 무결성 및 기밀성 ')를 포함 하 여 개인 데이터에 대 한 적절 한 보안을 보장 하는 방식으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="57d50-109">개인 데이터 침해는 종종 관리 또는 최종 사용자 계정 손상 및 악의적인 시스템 액세스로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="57d50-110">예를 들어 관리자 계정 해킹으로 인해 고객 신용 카드 번호나 기타 개인 정보를 exfiltration 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="57d50-111">준수 관리자에 게 제공 되는 Microsoft 365에서 사용할 수 있는 일반적으로 권장 되는 모든 id, 장치 및 위협 방지는 준수 점수에 반영 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="57d50-112">평가 작업 및 준수 관리자의 결과 사용</span><span class="sxs-lookup"><span data-stu-id="57d50-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="57d50-113">준수 관리자는 다음 범주를 사용 하는 id, 장치 및 위협 보호를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="57d50-114">**제어 액세스** 범주에 해당 하는 id입니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="57d50-115">장치가 **장치 관리** 범주에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="57d50-116">위협 방지는 **위협 으로부터 보호** 범주에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="57d50-117">4 가지 주요 데이터 개인 정보 규정을 준수 하는 샘플 집합에서 이러한 기능을 선택 하는 경우 적합성 관리자는 90 개선 작업을 지정 하며, 대부분의 경우 "27"로 점수가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="57d50-118">이러한 대규모 번호는 이러한 범주에 대 한 준수 관리자에 의해 호출 되기 때문에 참조를 위해 여기에 나열 되는 몇 가지 일반적인 항목이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="57d50-119">다음과 같은 작업을 수행할 수 있는 id 및 **제어 액세스** 범주에 [azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="57d50-120">Replay 방지 인증 구현 ("중간자" 공격을 막기 위해)</span><span class="sxs-lookup"><span data-stu-id="57d50-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="57d50-121">레거시 인증을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-121">Block legacy authentication.</span></span>
- <span data-ttu-id="57d50-122">사용자 위험 및 사용자 로그인 위험 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="57d50-123">관리자 및 비관리자를 위해 조건부 액세스 및 MFA (multi-factor authentication)를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="57d50-124">암호 정책을 구성 하 고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="57d50-125">Azure AD 권한 Id 관리를 사용 하 여 권한 있는 계정에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="57d50-126">종료 시 액세스를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="57d50-126">Disable access upon termination.</span></span>
- <span data-ttu-id="57d50-127">감사 사용자 계정 및 상태 변경</span><span class="sxs-lookup"><span data-stu-id="57d50-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="57d50-128">역할 그룹 및 관리 변경 내용을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="57d50-129">장치 및 **장치 관리** 범주에 대해 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="57d50-130">깨진 및 루트 모바일 장치를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="57d50-131">모바일 장치 관리를 위해 Intune을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="57d50-132">Android, iOS, macOS 및 Windows 장치에 대 한 준수 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="57d50-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="57d50-133">Android, iOS, macOS 및 Windows 장치에 대 한 장치 구성 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="57d50-134">IOS 및 Windows에 대 한 앱 보호 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="57d50-135">잠금 화면을 사용 하 여 정보 숨기기</span><span class="sxs-lookup"><span data-stu-id="57d50-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="57d50-136">모바일 장치에 대 한 암호 정책 구현</span><span class="sxs-lookup"><span data-stu-id="57d50-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="57d50-137">비활성 상태가 되 면 모바일 장치가 잠길 수 있도록 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="57d50-138">여러 로그인 오류가 발생 하면 모바일 장치에서 데이터를 정리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="57d50-139">다음을 수행할 수 있는 **위협 으로부터 보호** 범주에 대해 [Exchange Online Protection 및 Office 365 ATP (Advanced Threat Protection)](../security/office-365-security/office-365-atp.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="57d50-140">보낸 사람 인증 (SPF, DMARC 및 DKIM)을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="57d50-141">Office 365 ATP (Advanced Threat Protection) 피싱 방지 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="57d50-142">ATP 안전한 첨부 파일을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="57d50-143">ATP 안전한 링크를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="57d50-144">맬웨어 검색 및 응답 정책을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="57d50-145">아웃 바운드 및 인바운드 스팸 정책을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="57d50-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="57d50-146">참조가</span><span class="sxs-lookup"><span data-stu-id="57d50-146">References:</span></span>

- [<span data-ttu-id="57d50-147">일반 ID 및 장치 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="57d50-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="57d50-148">Office 365에서 위협 으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="57d50-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="57d50-149">ATP 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="57d50-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="57d50-150">ATP 안전한 링크</span><span class="sxs-lookup"><span data-stu-id="57d50-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="57d50-151">ATP 안전한 문서</span><span class="sxs-lookup"><span data-stu-id="57d50-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
