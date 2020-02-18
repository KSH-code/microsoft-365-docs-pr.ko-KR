---
title: Contoso의 모바일 장치 관리
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso에서 Microsoft 365 Enterprise의 Microsoft Intune을 사용하여 장치와 장치에서 실행 중인 앱을 관리하는 방법을 이해합니다.
ms.openlocfilehash: 7232c89cc105525cc57facd5a1b9de06426adbca
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068372"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="1a92b-103">Contoso의 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="1a92b-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="1a92b-104">Microsoft 365 Enterprise에는 모바일 장치 및 응용 프로그램의 관리와 보안을 지원하기 위한 Azure 서비스 집합과 Intune이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-104">Microsoft 365 Enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="1a92b-p101">Contoso에는 많은 모바일 사용 직원이 있으며, 일부는 Contoso 위치에 사무실을 보유하고, 일부는 사무실이 없습니다. Contoso는 직원 생산성을 유지하면서 장치, 해당 장치에 저장된 Contoso 데이터 및 응용 프로그램 동작을 안전하게 유지하는 방법이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="1a92b-107">계획</span><span class="sxs-lookup"><span data-stu-id="1a92b-107">Plan</span></span>

<span data-ttu-id="1a92b-108">Microsoft 365 Enterprise의 모바일 장치 관리를 초기에 분석하면서 Contoso는 다음과 같은 Intune 사용 사례를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-108">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="1a92b-109">모바일 장치에서 안전하게 액세스할 수 있도록 Exchange Online 전자 메일 및 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="1a92b-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="1a92b-110">Contoso 직원들을 위해 BYOD(Bring Your Own Device) 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="1a92b-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="1a92b-111">Contoso 직원에게 조직 소유의 휴대폰 및 사용이 제한된 공유 태블릿 발급</span><span class="sxs-lookup"><span data-stu-id="1a92b-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="1a92b-112">Contoso는 다음 작업에는 Intune을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="1a92b-113">직원들이 관리되지 않는 공용 키오스크에서 Office 365에 안전하게 액세스하도록 허용</span><span class="sxs-lookup"><span data-stu-id="1a92b-113">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="1a92b-114">모바일 장치에서 안전하게 액세스할 수 있도록 온-프레미스 전자 메일 및 데이터 보호(온-프레미스 Microsoft Exchange 서버는 더 이상 제공되지 않기 때문)</span><span class="sxs-lookup"><span data-stu-id="1a92b-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="1a92b-115">배포</span><span class="sxs-lookup"><span data-stu-id="1a92b-115">Deploy</span></span>

<span data-ttu-id="1a92b-116">Contoso가 모바일 장치 관리 인프라를 설정하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="1a92b-117">Intune을 MDM(모바일 장치 관리) 기관으로 설정하고 Azure에서 Intune을 사용하여 콘텐츠 및 장치 관리</span><span class="sxs-lookup"><span data-stu-id="1a92b-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="1a92b-118">등록과 Intune 설정 및 디바이스 기반 조건부 액세스 정책에 대한 디바이스의 Azure AD 그룹 생성</span><span class="sxs-lookup"><span data-stu-id="1a92b-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="1a92b-119">자세한 내용은 [Contoso의 조건부 액세스 정책](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a92b-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="1a92b-120">iPad, iMac, iPhone 및 iPhone 기반 회사 소유 휴대폰이 있는 직원을 지원하기 위한 Apple 장치 플랫폼을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1a92b-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="1a92b-121">모바일 장치에 Contoso의 회사 포털을 설치하는 동안 표시되는 Contoso 고유의 사용 약관 정책 생성</span><span class="sxs-lookup"><span data-stu-id="1a92b-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="1a92b-122">등록된 장치의 경우, Office 365 서비스에 액세스하기 위해 인증을 요구하는 MAM(모바일 응용 프로그램 관리) 정책 집합</span><span class="sxs-lookup"><span data-stu-id="1a92b-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="1a92b-123">다음을 적용하는 Intune 정책 생성:</span><span class="sxs-lookup"><span data-stu-id="1a92b-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="1a92b-124">허용되는 앱</span><span class="sxs-lookup"><span data-stu-id="1a92b-124">Allowed apps</span></span>
  - <span data-ttu-id="1a92b-125">무단된 액세스를 방지하기 위한 장치 암호화</span><span class="sxs-lookup"><span data-stu-id="1a92b-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="1a92b-126">6자리 PIN 또는 암호</span><span class="sxs-lookup"><span data-stu-id="1a92b-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="1a92b-127">비활성화 시간 초과 기간</span><span class="sxs-lookup"><span data-stu-id="1a92b-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="1a92b-128">Windows 10 장치의 Windows Defender를 사용한 바이러스 백신 및 맬웨어 보호, 서명 업데이트</span><span class="sxs-lookup"><span data-stu-id="1a92b-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="1a92b-129">최신 보안 업데이트를 포함하는 Windows 10 장치의 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="1a92b-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="1a92b-130">관리되는 장치로 인증서 푸시</span><span class="sxs-lookup"><span data-stu-id="1a92b-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="1a92b-p102">기업 및 개인 데이터의 명확한 분리. 사용자 또는 관리자는 그림, 개인 전자 메일 계정 및 개인 파일과 같은 개인 데이터는 그대로 두면서 장치에서 회사 데이터를 선택적으로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="1a92b-p103">배포가 끝난 후에 Contoso는 PC 및 회사 소유의 스마트폰과 태블릿을 해당 Intune 장치 그룹에 추가하여 등록한 후, 직원이 개인 장치를 등록할 수 있는 BYOD 프로그램을 롤아웃했습니다. 등록된 장치에는 Intune 정책이 수신되므로 장치 및 해당 응용 프로그램을 관리하고 보안을 유지할 수 있습니다. 등록되지 않은 장치에는 허용되는 응용 프로그램을 지정하는 MAM(모바일 응용 프로그램 관리) 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="1a92b-136">여기 Contoso의 모바일 장치 관리 배포 구조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a92b-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contoso의 모바일 장치 관리 배포 인프라](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="1a92b-138">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1a92b-138">Next step</span></span>

<span data-ttu-id="1a92b-139">Contoso에서 Microsoft 365 Enterprise의 정보 보호 기능을 사용하여 조직에서 중요한 디지털 자산을 분류하고, 식별하고, 보호하는 방법을 [알아봅니다](contoso-info-protect.md).</span><span class="sxs-lookup"><span data-stu-id="1a92b-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a92b-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a92b-140">See also</span></span>

[<span data-ttu-id="1a92b-141">Microsoft 365 Enterprise의 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="1a92b-141">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="1a92b-142">배포 가이드</span><span class="sxs-lookup"><span data-stu-id="1a92b-142">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1a92b-143">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="1a92b-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

