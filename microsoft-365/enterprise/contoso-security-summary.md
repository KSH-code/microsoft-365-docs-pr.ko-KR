---
title: Contoso Corporation의 Microsoft 365 Enterprise 보안 요약
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 Microsoft 365 Enterprise에서 보안 기능을 사용하는 방법
ms.openlocfilehash: f8a16b07c6d4cb9a62e0131a1f667b675d5eaf66
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636489"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="279dc-103">Contoso Corporation의 Microsoft 365 Enterprise 보안 요약</span><span class="sxs-lookup"><span data-stu-id="279dc-103">Summary of Microsoft 365 Enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="279dc-p101">IT 보안 부서에서 Microsoft 365 Enterprise 배포 작업의 승인을 얻기 위해 철저한 보안 검토가 수행되었습니다. 다음은 클라우드에 대한 Contoso의 보안 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p101">To obtain the sign-off of the deployment of Microsoft 365 Enterprise by the IT security department, a thorough security review was conducted. Here are Contoso's security requirements for the cloud:</span></span>

- <span data-ttu-id="279dc-106">클라우드 리소스에 대한 직원 액세스에 가장 강력한 인증 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-106">Use the strongest methods of authentication for employee access to cloud resources</span></span>
- <span data-ttu-id="279dc-107">PC 및 모바일 장치가 안전한 방법으로 응용 프로그램을 연결하고 액세스하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-107">Ensure that PCs and mobile devices connect and access applications in secure ways</span></span>
- <span data-ttu-id="279dc-108">PC 및 전자 메일이 악의적인 소프트웨어로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-108">PCs and email are protected from malware</span></span>
- <span data-ttu-id="279dc-109">클라우드 기반 디지털 자산에 대한 권한은 누가 어떤 기능에 액세스할 수 있는지와 수행할 수 있는 작업 및 최소 권한 액세스로 디자인된 대상을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-109">Permissions on cloud-based digital assets define who can access what and what they can do and are designed for least privilege access</span></span>
- <span data-ttu-id="279dc-110">중요 및 높은 규제 대상 디지털 자산은 레이블이 지정되고 암호화된 후 안전한 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-110">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations</span></span>
- <span data-ttu-id="279dc-111">높은 규제 대상 디지털 자산은 추가적인 암호화와 사용 권한으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-111">Highly regulated digital assets are protected with additional encryption and permissions</span></span>
- <span data-ttu-id="279dc-112">IT 보안 직원은 중앙 대시보드에서 현재의 보안 태세를 모니터링하고, 빠른 대응 및 완화를 위해 보안 이벤트 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-112">IT security staff can monitor the current security posture from central dashboards and get notified of security events for quick response and mitigation</span></span>

## <a name="contosos-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="279dc-113">Contoso의 Microsoft 365 보안 준비 과정</span><span class="sxs-lookup"><span data-stu-id="279dc-113">Contoso's path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="279dc-114">Contoso는 다음 단계에 따라 Microsoft 365 Enterprise 배포에 대한 보안을 준비했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-114">Contoso used the following steps to ready their security for their deployment of Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="279dc-115">클라우드용 관리자 계정 제한</span><span class="sxs-lookup"><span data-stu-id="279dc-115">Limited administrator accounts for the cloud</span></span>

   <span data-ttu-id="279dc-116">Contoso는 기존 Active Directory Domain Services (AD DS) 관리자 계정을 포괄적으로 검토하여 일련의 전용 클라우드 관리자 계정 및 그룹을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-116">Contoso did an extensive review of the existing Active Directory Domain Services (AD DS) administrator accounts and set up a series of dedicated cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="279dc-117">3개 수준으로 데이터 분류 분석 수행</span><span class="sxs-lookup"><span data-stu-id="279dc-117">Performed data classification analysis into three levels</span></span>

   <span data-ttu-id="279dc-118">Contoso는 철저한 검토를 수행한 후 3개 수준을 결정했으며, 이러한 수준을 사용하여 Contoso의 가장 중요한 데이터를 보호하기 위한 Microsoft 365 Enterprise 기능을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-118">Contoso performed a careful review and determined the three levels, which was used to determine the Microsoft 365 Enterprise features to protect Contoso's most valuable data.</span></span>

3. <span data-ttu-id="279dc-119">데이터 수준에 대한 액세스, 보존 및 정보 보호 정책 결정</span><span class="sxs-lookup"><span data-stu-id="279dc-119">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="279dc-120">Contoso는 데이터 수준에 따라 상세 요구 사항을 결정했으며, 이러한 요구 사항을 사용하여 향후 클라우드로 이동하는 IT 작업을 선별할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-120">Based on the data levels, Contoso determined detailed requirements, which will be used to qualify future IT workloads being moved to the cloud.</span></span>

<span data-ttu-id="279dc-121">Contoso의 보안 관리자 및 IT 부서는 보안 모범 사례 및 Microsoft 365 Enterprise 배포 요구 사항에 따라, 다음 섹션에 설명된 것과 같은 많은 보안 기능을 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-121">In accordance with security best practices and Microsoft 365 Enterprise deployment requirements, Contoso's security administrators and IT department have deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity--access-management"></a><span data-ttu-id="279dc-122">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="279dc-122">Identity & access management</span></span> 

- <span data-ttu-id="279dc-123">MFA 및 PIM이 있는 전용 전역 관리자 계정</span><span class="sxs-lookup"><span data-stu-id="279dc-123">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="279dc-124">일상적인 사용자 계정에 전역 관리자 역할을 할당하지 않고, Contoso는 강력한 암호를 가지는 3개의 전용 전역 관리자 계정을 만든 후, Azure 다단계 인증 (MFA )및 Azure 활성 디렉터리 (Azure AD), 특권 계정 관리 (PIM)로 보호했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-124">Rather than assign the global admin role to everyday user accounts, Contoso created three, dedicated global administrator accounts with strong passwords and protected them with Azure Multi-Factor Authentication (MFA) and Azure Active Directory (Azure AD) Privileged Identity Management (PIM).</span></span> <span data-ttu-id="279dc-125">PIM은 Microsoft 365 E5에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-125">PIM is only available with Microsoft 365 E5.</span></span>

  <span data-ttu-id="279dc-126">전역 관리자 계정을 사용한 로그인은 특정 관리 작업에 대해서만 수행되고, 암호는 지정된 직원만 알고 있으며, Azure AD PIM을 사용하여 구성된 시간 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-126">Signing in with a global administrator account is only done for specific administrative tasks, the passwords are only known to designated staff and can only be used within the time configured with Azure AD PIM.</span></span> 

  <span data-ttu-id="279dc-127">Contoso의 보안 관리자는 해당 IT 사용자의 직무와 책임에 적합한 더 적은 관리자 역할을 계정에 할당했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-127">Contoso's security administrators have assigned lesser admin roles to accounts that are appropriate to that IT person's job function and responsibility.</span></span>

  <span data-ttu-id="279dc-128">자세한 내용은 [Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="279dc-128">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="279dc-129">모든 사용자 계정에 대한 MFA</span><span class="sxs-lookup"><span data-stu-id="279dc-129">MFA for all user accounts</span></span>

  <span data-ttu-id="279dc-p103">MFA는 사용자에게 암호를 올바르게 입력한 후에 스마트폰에서 전화 통화, 문자 메시지 또는 앱 알림을 승인하도록 요구함으로써 추가적인 로그인 프로세스 보호 계층을 제공합니다. MFA를 사용할 경우 Azure AD 사용자 계정은 계정 암호가 손상된 경우에도 무단 로그인으로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p103">MFA adds an additional layer of protection to the sign-in process by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA, Azure AD user accounts are protected against unauthorized sign-in even if an account password is compromised.</span></span>

   - <span data-ttu-id="279dc-132">Contoso는 Microsoft 365 구독이 손상되지 않도록 보호하기 위해 모든 전역 관리자 계정에서 MFA를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-132">To protect against a compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="279dc-133">Contoso는 공격자가 조직에서 신뢰할 수 있는 사용자의 자격 증명을 손상하고 악의적인 전자 메일을 보내는 피싱 공격으로부터 보호하기 위해 관리자 및 임원을 비롯한 모든 사용자 계정에서 MFA를 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-133">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including managers and executives.</span></span> 

- <span data-ttu-id="279dc-134">조건부 액세스 정책을 사용한 보다 안전한 장치 및 응용 프로그램 액세스</span><span class="sxs-lookup"><span data-stu-id="279dc-134">Safer device and application access with Conditional Access policies</span></span>

  <span data-ttu-id="279dc-p104">Contoso는 ID, 장치, Exchange Online 및 SharePoint에 대해 [조건부 액세스 정책](microsoft-365-policies-configurations.md)을 사용하고 있습니다. ID 조건부 액세스 정책에는 높은 위험에 처한 사용자에게 암호 변경 요구, 클라이언트가 최신 인증을 지원하지 않는 앱을 사용하지 못하도록 지정 등이 포함됩니다. 장치 정책에는 승인된 앱의 정의와 규격 PC 및 모바일 장치 요구가 포함됩니다. Exchange Online 조건부 액세스 정책에는 ActiveSync 클라이언트 차단 및 Office 365 메시지 암호화 설정이 포함됩니다. SharePoint 조건부 액세스 정책에는 중요 및 높은 규제 대상 사이트에 대한 추가적인 보호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p104">Contoso is using [Conditional Access policies](microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint. Identity Conditional Access policies include requiring password changes for high-risk users and blocking clients from using apps that don't support modern authentication. Device policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online Conditional Access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Conditional Access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="279dc-140">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="279dc-140">Windows Hello for Business</span></span>

  <span data-ttu-id="279dc-141">Contoso는 [비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)를 배포했으며, Windows 10 Enterprise를 실행하는 PC 및 모바일 장치에서 강력한 2단계 인증을 사용하여 암호가 필요하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-141">Contoso has deployed and requires [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords with strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="279dc-142">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="279dc-142">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="279dc-143">관리 권한을 사용하여 운영 체제에서 실행되는 표적 공격 및 악성 소프트웨어를 차단하기 위해 Contoso는 AD DS 그룹 정책을 통해 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)를 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-143">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso has enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through AD DS group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="279dc-144">위협 방지</span><span class="sxs-lookup"><span data-stu-id="279dc-144">Threat protection</span></span>

- <span data-ttu-id="279dc-145">Windows Defender 바이러스 백신으로 맬웨어로부터 보호</span><span class="sxs-lookup"><span data-stu-id="279dc-145">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="279dc-146">Contoso는 Windows 10 Enterprise가 실행되는 PC 및 장치에 대해 맬웨어 보호 및 맬웨어 방지 관리를 제공하기 위해 [Windows Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-146">Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="279dc-147">Office 365 고급 위협 방지 기능으로 전자 메일 흐름 및 사서함 감사 로깅 보호</span><span class="sxs-lookup"><span data-stu-id="279dc-147">Secure email flow and mailbox audit logging with Office 365 Advanced Threat Protection</span></span> 

  <span data-ttu-id="279dc-148">Contoso는 Exchange Online Protection 및 [Office 365 Threat Protection ATP(Advanced)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)를 사용하여 알 수 없는 맬웨어, 바이러스 및 전자 메일을 통해 전송되는 악성 URL로부터 보호하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-148">Contoso is using Exchange Online Protection and [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span> 

  <span data-ttu-id="279dc-149">Contoso는 또한 사용자 사서함에 로그인한 사람, 보낸 메시지 및 사서함 소유자, 위임된 사용자 또는 관리자가 수행한 기타 활동을 확인하기 위해 사서함 감사 로깅을 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-149">Contoso has also enabled mailbox audit logging to determine who has logged into user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="279dc-150">Office 365 위협 조사와 응답으로 공격 모니터링 및 방지</span><span class="sxs-lookup"><span data-stu-id="279dc-150">Attack monitoring and prevention with Office 365 threat investigation and response</span></span>

  <span data-ttu-id="279dc-151">Contoso는 [Office 365 위협 조사 및 응답](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)을 사용하여 공격을 더욱 쉽게 식별 및 해결하고, 후속 공격을 방지함으로써 사용자를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-151">Contoso uses [Office 365 threat investigation and response](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect their users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="279dc-152">Advanced Threat Analytics를 사용하여 정교한 공격으로부터 보호</span><span class="sxs-lookup"><span data-stu-id="279dc-152">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="279dc-p105">Contoso는 [ATA(Advanced Threat Analytics)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata)를 사용하여 타기팅된 고급 공격으로부터 자체적으로 보호합니다. ATA는 정상 및 비정상 엔터티(사용자, 장치, 리소스) 동작을 자동으로 분석, 학습 및 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p105">Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span> 

## <a name="information-protection"></a><span data-ttu-id="279dc-155">정보 보호</span><span class="sxs-lookup"><span data-stu-id="279dc-155">Information protection</span></span>

- <span data-ttu-id="279dc-156">Azure Information Protection 레이블을 사용하여 중요 및 높은 규제 대상 디지털 자산 보호</span><span class="sxs-lookup"><span data-stu-id="279dc-156">Protect sensitive and highly regulated digital assets with Azure Information Protection labels</span></span>

  <span data-ttu-id="279dc-p106">Contoso는 세 가지 수준의 데이터 보호를 결정하고, 사용자가 디지털 자산에 적용하는 [Microsoft 365 민감성 레이블](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)을 배포했습니다. 또한 영업 비밀 및 기타 지적 재산권의 경우 콘텐츠를 암호화하고 특정 사용자 계정 및 그룹으로의 액세스를 제한하는 높은 규제 대상 데이터에 대해서는 민감성 하위 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p106">Contoso determined three levels of data protection and deployed [Microsoft 365 sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) that users apply to digital assets. For its trade secrets and other intellectual property, Contoso uses sensitivity sublabels highly regulated data that encrypts content and restricts access to specific user accounts and groups.</span></span>

- <span data-ttu-id="279dc-159">데이터 손실 방지로 인트라넷 데이터 유출 방지하기</span><span class="sxs-lookup"><span data-stu-id="279dc-159">Prevent intranet data leaks with Data Loss Prevention</span></span>

  <span data-ttu-id="279dc-160">Contoso는 Exchange Online, SharePoint 및 비즈니스용 OneDrive에 대해 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 정책을 구성하여 사용자들이 실수로 또는 의도적으로 중요한 데이터를 공유하지 못하도록 하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-160">Contoso has configured [Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="279dc-161">Windows Information Protection로 장치 데이터 누수 방지</span><span class="sxs-lookup"><span data-stu-id="279dc-161">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="279dc-162">Contoso는 [WIP(Windows Information Protection)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)를 사용하여 인터넷 기반 앱 및 서비스, 엔터프라이즈 소유의 장치 및 직원이 회사에 가져오는 개인 장치에 있는 엔터프라이즈 앱과 서비스를 통해 데이터가 누수되지 않도록 보호하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-162">Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through Internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="279dc-163">Microsoft Cloud App Security를 사용하는 클라우드 모니터링</span><span class="sxs-lookup"><span data-stu-id="279dc-163">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="279dc-164">Contoso는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 사용하여 클라우드 환경을 매핑하고, 사용 현황을 모니터링하고, 보안 이벤트 및 인시던트를 감지하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-164">Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> <span data-ttu-id="279dc-165">Microsoft Cloud App Security는 Microsoft 365 E5에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-165">Microsoft Cloud App Security is only available with Microsoft 365 E5.</span></span>

- <span data-ttu-id="279dc-166">Microsoft Intune을 사용한 장치 관리</span><span class="sxs-lookup"><span data-stu-id="279dc-166">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="279dc-p108">Contoso는 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune)을 사용하여 모바일 장치 및 해당 장치에서 실행되는 앱을 등록, 관리 및 구성합니다. 또한 장치 기반 조건부 액세스 정책은 승인된 앱과 규격 PC 및 모바일 장치를 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-p108">Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based Conditional Access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="279dc-169">보안 관리</span><span class="sxs-lookup"><span data-stu-id="279dc-169">Security management</span></span>

- <span data-ttu-id="279dc-170">Azure Security Center의 IT 부서를 위한 중앙 보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="279dc-170">Central security dashboard for IT with Azure Security Center</span></span>

  <span data-ttu-id="279dc-171">Contoso는 보안 및 위협 보호에 대한 통합 보기로 [Azure Security Center](https://azure.microsoft.com/services/security-center/)를 사용하여 워크로드 간에 보안 정책을 관리하고 사이버 공격에 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-171">Contoso uses the [Azure Security Center](https://azure.microsoft.com/services/security-center/) for a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="279dc-172">Windows Defender 보안 센터의 사용자를 위한 중앙 보안 대시보드</span><span class="sxs-lookup"><span data-stu-id="279dc-172">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="279dc-173">Contoso는 Windows 10 Enterprise가 실행되는 PC 및 장치에 [Windows 보안 앱](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)을 배포하여 사용자가 보안 태세를 한 눈에 확인하고 조치를 취할 수 있도록 하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279dc-173">Contoso has deployed the [Windows Security app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>


## <a name="next-step"></a><span data-ttu-id="279dc-174">다음 단계</span><span class="sxs-lookup"><span data-stu-id="279dc-174">Next step</span></span>

<span data-ttu-id="279dc-175">Contoso에서 연구팀 간에 공동 작업을 수행할 수 있도록 규제가 엄격한 데이터를 위해 SharePoint 사이트를 만든 방법을 [알아보세요](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="279dc-175">[Learn](contoso-sharepoint-online-site-for-highly-confidential-assets.md) how Contoso created a SharePoint site for highly regulated data to enable collaboration among its research teams.</span></span>

