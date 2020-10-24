---
title: Contoso의 모바일 장치 관리
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 365에서 microsoft Intune을 사용 하 여 기업에 대해 실행 되는 앱과 장치를 관리 하는 방법을 이해 합니다.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754000"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="cf492-103">Contoso의 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="cf492-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="cf492-104">엔터프라이즈에 대 한 Microsoft 365에는 Intune과 모바일 장치 및 응용 프로그램 관리 및 보안을 지 원하는 Azure 서비스 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="cf492-p101">Contoso에는 모바일 사용 가능 직원이 많이 있습니다. 일부는 Contoso 위치에 있고 일부는 사무실을 갖고 있지 않습니다. Contoso는 직원 생산성을 사용 하도록 설정 하는 방법을 필요로 하지만, 장치, 해당 장치에 저장 된 Contoso 데이터 및 응용 프로그램 동작 보안을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="cf492-108">계획</span><span class="sxs-lookup"><span data-stu-id="cf492-108">Plan</span></span>

<span data-ttu-id="cf492-109">Contoso에서 엔터프라이즈에 대 한 Microsoft 365의 모바일 장치 관리에 대 한 다음과 같은 Intune 사용 사례를 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="cf492-110">모바일 장치에서 안전 하 게 액세스할 수 있도록 Exchange Online 전자 메일 및 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="cf492-111">Contoso 직원을 위한 BYOD (직접 장치 만들기) 프로그램을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="cf492-112">Contoso 직원에 게 조직 소유의 휴대폰 및 사용이 제한 된 공유 태블릿 문제를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="cf492-113">Contoso는 Intune을 사용 하 여 다음을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="cf492-114">직원 들이 관리 되지 않는 공개 키오스크에서 Microsoft 365에 안전 하 게 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="cf492-115">온-프레미스 Microsoft Exchange 서버가 없기 때문에 모바일 장치에서 안전 하 게 액세스할 수 있도록 온-프레미스 전자 메일 및 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="cf492-116">배포</span><span class="sxs-lookup"><span data-stu-id="cf492-116">Deploy</span></span>

<span data-ttu-id="cf492-117">Contoso가 모바일 장치 관리 인프라를 설정하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="cf492-118">Intune을 MDM (모바일 장치 관리) 기관으로 설정 하 고 Azure에서 Intune을 사용 하 여 콘텐츠를 관리 하 고 장치를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="cf492-119">등록 및 Intune 설정 및 장치 기반 조건부 액세스 정책에 대 한 Azure Active Directory (Azure AD) 그룹을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="cf492-120">자세한 내용은 [Contoso 조건부 액세스 정책을](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf492-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="cf492-121">Ipad, iMacs 및 Iphone 및 회사 소유 Iphone가 있는 직원을 지원 하기 위해 Apple 장치 플랫폼을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="cf492-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="cf492-122">모바일 장치에 Contoso의 회사 포털을 설치하는 동안 표시되는 Contoso 고유의 사용 약관 정책 생성</span><span class="sxs-lookup"><span data-stu-id="cf492-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="cf492-123">등록 되지 않은 장치의 경우 Microsoft 365 서비스에 액세스 하기 위해 인증을 요구 하는 MAM (모바일 응용 프로그램 관리) 정책 집합을 구현 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="cf492-124">다음을 적용하는 Intune 정책 생성:</span><span class="sxs-lookup"><span data-stu-id="cf492-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="cf492-125">허용 되는 앱</span><span class="sxs-lookup"><span data-stu-id="cf492-125">Allowed apps.</span></span>
  - <span data-ttu-id="cf492-126">무단 액세스를 방지 하는 데 도움이 되는 장치 암호화</span><span class="sxs-lookup"><span data-stu-id="cf492-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="cf492-127">6 자리 PIN 또는 암호</span><span class="sxs-lookup"><span data-stu-id="cf492-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="cf492-128">비활동 제한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="cf492-129">Windows 10 장치의 Windows Defender를 사용한 바이러스 백신 및 맬웨어 보호 및 서명 업데이트</span><span class="sxs-lookup"><span data-stu-id="cf492-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="cf492-130">최신 보안 업데이트를 포함 하는 Windows 10 장치의 자동 업데이트</span><span class="sxs-lookup"><span data-stu-id="cf492-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="cf492-131">관리 되는 장치에 인증서를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="cf492-p102">기업 및 개인 데이터의 명확한 분리. 사용자 또는 관리자는 그림, 개인 전자 메일 계정 및 개인 파일과 같은 개인 데이터는 그대로 두면서 장치에서 회사 데이터를 선택적으로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="cf492-134">Contoso는 해당 하는 Intune 장치 그룹에 Pc 및 회사 소유의 스마트폰 및 태블릿을 추가 하 여이를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="cf492-135">또한 직원 들이 개인 장치를 등록 하는 BYOD 프로그램을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="cf492-136">등록 된 장치는 Intune 정책을 수신 하 여 관리 및 보안 장치와 해당 응용 프로그램을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="cf492-137">등록 되지 않은 장치에는 허용 되는 응용 프로그램을 지정 하는 MAM (모바일 응용 프로그램 관리) 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="cf492-138">다음은 Contoso 모바일 장치 관리 배포 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Contoso 모바일 장치 관리 배포 인프라](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="cf492-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cf492-140">Next step</span></span>

<span data-ttu-id="cf492-141">Contoso에서 기업에 대 한 Microsoft 365의 [정보 보호 기능](contoso-info-protect.md) 을 사용 하 여 조직에서 중요 한 디지털 자산을 분류, 식별 및 보호 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cf492-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf492-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf492-142">See also</span></span>

[<span data-ttu-id="cf492-143">Microsoft 365에 대 한 장치 관리</span><span class="sxs-lookup"><span data-stu-id="cf492-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="cf492-144">엔터프라이즈용 Microsoft 365 개요</span><span class="sxs-lookup"><span data-stu-id="cf492-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="cf492-145">테스트 랩 가이드</span><span class="sxs-lookup"><span data-stu-id="cf492-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

