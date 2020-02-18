---
title: 5단계 - 보안 및 준수 고려 사항
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 중요한 Windows/Office 보안 및 준수 고려 사항에 대해 알아봅니다.
ms.openlocfilehash: 1d38347ca1bdf152a891cfd147ec3fabf552ff3d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085272"
---
# <a name="step-5-security-and-compliance-considerations"></a><span data-ttu-id="05425-103">5단계: 보안 및 준수 고려 사항</span><span class="sxs-lookup"><span data-stu-id="05425-103">Step 5: Security and Compliance Considerations</span></span>

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><span data-ttu-id="05425-104"><strong>5단계: 보안 및 준수 고려 사항</strong></span><span class="sxs-lookup"><span data-stu-id="05425-104"><strong>Step 5: Security and Compliance Considerations</strong></span></span></p>
<p><span data-ttu-id="05425-p101">Windows 10 및 Office 365 ProPlus는 데이터, 장치 및 사용자를 보호하고 위협을 빠르게 감지하고 대응하는 새로운 방법을 제공합니다. 또한 디스크 암호화, 맬웨어 방지 앱 및 Windows 10으로 전환할 때의 정책과 관련된 일반적인 문제를 처리하는 방법도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p101">Windows 10 and Office 365 ProPlus provide new ways to protect your data, devices and users and quickly detect and respond to threats. Also, learn how to deal with common problems associated with disk encryption, anti-malware apps and policies when moving to Windows 10.</span></span></p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="05425-107">보안 및 규정 준수는 Windows 10/Office 365 ProPlus 보안 및 준수 고려 사항을 포함하는 권장 배포 프로세스 사이클의 5번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="05425-107">Security and Compliance is the fifth step in our recommended deployment process wheel covering Windows 10 and Office 365 ProPlus security and compliance considerations.</span></span> <span data-ttu-id="05425-108">전체 데스크톱 배포 프로세스를 보려면 [데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="05425-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="05425-109">이제 이전 버전의 Windows 및 Office에서 전환하는 경우의 고려 사항 및 일반적인 방해 요인과 함께, Windows 10 및 Office 365 ProPlus 배포의 일부로서 새로운 보안 및 준수 기능을 목표로 구현하기 위한 옵션을 검토할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="05425-109">Now it's time to review options for targeting new security and compliance capabilities as part of your Windows 10 and Office 365 ProPlus deployment, along with the considerations and common blockers when moving from previous versions of Windows and Office.</span></span> <span data-ttu-id="05425-110">많은 보안 관련 기능 때문에 최신 플랫폼인 Windows 10으로의 전환이 추진되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-110">Many of the security-related capabilities in Windows 10 alone are driving the shift to the newer platform.</span></span> <span data-ttu-id="05425-111">또한 Office 365의 클라우드 서비스와의 통합과 Azure Active Directory를 사용하는 ID 옵션을 통해 데이터, 장치 및 사용자를 위한 새롭거나 지속적으로 업데이트되는 보호 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-111">Also, integration with cloud services in Office 365 and identity options using Azure Active Directory brings access to new and continually updated protections for your data, devices and users.</span></span>

## <a name="overcoming-potential-security-related-deployment-blockers"></a><span data-ttu-id="05425-112">잠재적인 보안 관련 배포 방해 요인 극복</span><span class="sxs-lookup"><span data-stu-id="05425-112">Overcoming Potential Security-Related Deployment Blockers</span></span>

<span data-ttu-id="05425-113">Windows 10 및 Office 365 ProPlus로 전환하고 이러한 환경을 클라우드에 연결할 때 추가할 수 있는 새로운 기능을 설명하기 전에, 배포 진행을 중단시킬 수 있는 몇 가지 추세부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-113">Before explaining new capabilities that you can add as you move to Windows 10 and Office 365 ProPlus and connect those experiences to the cloud, let’s start with a few trends we’re seeing that can often interrupt deployment progress.</span></span>

### <a name="disk-encryption"></a><span data-ttu-id="05425-114">디스크 암호화</span><span class="sxs-lookup"><span data-stu-id="05425-114">Disk Encryption</span></span>

<span data-ttu-id="05425-p104">초기에 겪게 되는 난제 중 하나가 하드 디스크 암호화입니다. 하드 디스크 암호화용 솔루션 대부분은 이전 버전의 Windows에서 최신 버전의 Windows로 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p104">First one of the initial challenges you might encounter is hard disk encryption. Many solutions for hard disk encryption cannot easily be upgraded from a previous version of Windows to a newer version of Windows.</span></span>

<span data-ttu-id="05425-p105">일부 디스크 암호화 솔루션에서는 특정 버전의 플랫폼에서 Windows 설치 프로그램과 함께 ‘/reflectdrivers’ 옵션을 사용하여 업그레이드를 수행할 수 있지만, 일부 솔루션에서는 배포 전에 드라이브의 암호를 해독했다가 Windows 10을 설치한 후 다시 암호화해야 할 수 있습니다. 또한 일부 플랫폼에서는 레거시 BIOS를 사용하여 MBR(마스터 부트 레코드)에서 UEFI에 필요한 GPT(GUID 파티션 테이블)로 전환할 수 없습니다. 이러한 문제는 UEFI가 있는 Windows 10 64비트가 아래에 설명된 Windows 10의 새로운 가상화 기반 보안 기능에 필요하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p105">Some disk encryption solutions allow you to perform the upgrades when using the ‘/reflectdrivers’ option with Windows Setup on certain versions of their platforms, but others may require you to unencrypt the drive prior to deployment, then re-encrypt after Windows 10 is installed. Some solutions also do not allow you to move from Master Boot Record (MBR), using legacy BIOS, to GUID Partition Table (GPT), required for UEFI. This is important because a 64-bit version of Windows 10 with UEFI is required for the new virtualization-based security capabilities in Windows 10 and those are explained below.</span></span>

<span data-ttu-id="05425-p106">이러한 문제를 해결하기 위한 한 가지 옵션은 Windows 10 Pro 이상 버전에 포함된 Windows 10의 BitLocker를 사용하는 것입니다. BitLocker를 사용하면 프로세스의 일부로 OS 업그레이드 및 기능 업데이트에 대한 보호를 일시 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p106">One option to resolve these issues is using BitLocker in Windows 10, which is included in Windows 10 Pro and higher editions. BitLocker allows you to suspend protection for OS upgrades and Feature Updates as part of the process.</span></span>

[<span data-ttu-id="05425-122">Bitlocker 기본 배포</span><span class="sxs-lookup"><span data-stu-id="05425-122">Bitlocker basic deployment</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)

### <a name="antivirus-and-antimalware-application-compatibility"></a><span data-ttu-id="05425-123">바이러스 백신 및 맬웨어 방지 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="05425-123">Antivirus and Antimalware Application Compatibility</span></span>

<span data-ttu-id="05425-p107">둘째, Windows 7과 Windows 10 사이에서 [99% 이상의 Windows 응용 프로그램이 호환된다고](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) 확인되었으나, 종종 AV(바이러스 백신) 앱 또는 VPN(가상 사설망) 클라이언트에서 예외가 나타납니다. 이러한 응용 프로그램은 종종 비표준 개발 사례와 API를 구현하며, 문서화되지 않은 방식을 사용해서 시스템을 보호하거나 네트워크 리소스에 연결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p107">Second, while we’ve seen that more than [99% of Windows applications are compatible](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) between Windows 7 and Windows 10, the exceptions are often anti-virus (AV) apps or Virtual Private Network (VPN) clients. These applications often implement non-standard development practices and APIs, using often undocumented ways to protect your system or connect you to network resources.</span></span>

<span data-ttu-id="05425-p108">결과적으로 이러한 앱은 본질적으로 새 버전의 Windows로 전환할 때 변화에 취약할 수 있습니다. AV 또는 VPN 소프트웨어가 Windows 10에서 또는 업그레이드 이후에 작동하지 않을 경우 사용 중인 앱을 Windows 10에서 지원되는 테스트를 거친 앱으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p108">As a result, these apps by nature can be fragile to changes when shifting to a new version of Windows. If your AV or VPN software doesn’t work in Windows 10 or after upgrading, the fix is typically to replace the app you’re using with something supported and tested on Windows 10.</span></span>

### <a name="security-policies"></a><span data-ttu-id="05425-128">보안 정책</span><span class="sxs-lookup"><span data-stu-id="05425-128">Security Policies</span></span>

<span data-ttu-id="05425-p109">이전 버전의 Windows 및 Office에 사용되는 Active Directory 그룹 정책 설정은 Windows 10 및 Office 365 ProPlus로 직접 변환되지 않을 수 있으며, 최신 보안 및 준수 기능에 따라 고려 사항도 달라집니다. Microsoft 보안 규정 준수 도구 키트를 사용하여 현재 버전의 Windows 및 Office에 대한 보안 정책 기준을 확인하는 것이 좋습니다. 또한 Microsoft Intune의 일부로 모바일 장치 관리 정책을 살펴보는 것도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p109">Your Active Directory Group Policy settings used for older versions of Windows and Office may not translate directly to Windows 10 and Office 365 ProPlus, and there are different considerations with newer security and compliance capabilities. It’s a good idea to use the Microsoft Security Compliance Toolkit to get a baseline of the security policies for current versions of Windows and Office. Additionally, it’s worth looking into Mobile Device Management policies as part of Microsoft Intune.</span></span>

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a><span data-ttu-id="05425-132">Microsoft 365의 새로운 보안 및 규정 준수 기능</span><span class="sxs-lookup"><span data-stu-id="05425-132">New Security and Compliance Capabilities in Microsoft 365</span></span>

<span data-ttu-id="05425-p110">지금까지 최신 보호를 적용하기 위한 고려 사항과 전환 전에 알아야할 사항에 대해 살펴보았습니다. 이제, Windows 10, Office 365 ProPlus 및 EMS의 클라우드 기반 옵션 이상으로 전환할 때 이용할 수 있는 새로운 기능을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p110">Now, those were considerations for moving your current protections forward and things to be aware of before your shift. Now let’s take a look at new capabilities that you can take advantage of when moving to Windows 10, Office 365 ProPlus and cloud-based options from EMS and beyond.</span></span>

### <a name="identity-and-access-management"></a><span data-ttu-id="05425-135">ID 및 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="05425-135">Identity and Access Management</span></span>

<span data-ttu-id="05425-p111">ID 및 액세스 관리를 먼저 살펴보겠습니다. Azure Active Directory는 앱, 장치 및 클라우드 서비스에 대한 ID 제어 평면으로, Office 365 및 기타 클라우드 서비스에 연결하는 최신 방법입니다. 조건부 액세스를 사용하면 로그인한 위치, 사용 중인 장치, 비정상적인 동작 등을 토대로 다양한 인증 요구 사항을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p111">Starting with identity and access management. Azure Active Directory is the identity control plane for apps, devices and Cloud services and is the modern way to connect to Office 365 and other Cloud services. Conditional access allows you to define different authentication requirements based on where you are logging in from, which device you're using, as well as things like anomalous behaviors.</span></span>

<span data-ttu-id="05425-p112">장치 수준에서 생체 인식은 암호를 없애는 목표를 달성하면서 좀 더 간편하고 안전하게 장치 및 앱에 액세스하기 위한 고유한 식별자를 제공할 수 있습니다. Windows Hello는 장치 기반, 다단계 인증을 제공합니다. 이 기능은 정책을 통해 장치 자체, 사용자의 PIN 또는 고유한 생체 인식 식별자(예: 얼굴 또는 지문)를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p112">At the device level, biometrics can provide unique identifiers for simpler and more secure access to your devices and apps - as you move toward the goal of eliminating passwords. Windows Hello offers device-based, multi-factor authentication. It relies on the device itself, your PIN, or unique biometric identifier such as your face or fingerprint, which you can enforce via policy.</span></span>

[<span data-ttu-id="05425-142">Azure ID 관리의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="05425-142">Fundamentals of Azure identity management</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-fundamentals)

[<span data-ttu-id="05425-143">Azure ID 솔루션 이해</span><span class="sxs-lookup"><span data-stu-id="05425-143">Understand Azure identity solutions</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/understand-azure-identity-solutions)

[<span data-ttu-id="05425-144">Azure Active Directory 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="05425-144">Azure Active Directory Conditional Access</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

[<span data-ttu-id="05425-145">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="05425-145">Windows Hello for Business</span></span>](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)

### <a name="virtualization-based-security"></a><span data-ttu-id="05425-146">가상화 기반 보안</span><span class="sxs-lookup"><span data-stu-id="05425-146">Virtualization-based security</span></span>

<span data-ttu-id="05425-p113">이제 ID를 사용하는 것 외에도, 알려진 위협과 알려지지 않은 위협에 대해 지속적인 보호를 설정할 수 있습니다. 이를 위해 Windows 10에서는 핵심 영역에서 가상화 기반 보안을 사용하여 보안 부트를 통해 부팅 무결성 및 코드 무결성을 보장합니다. Microsoft는 Credential Guard를 통해 사용자 비밀을 Windows와 따로 유지 관리함으로써 자격 증명을 도난당하는 문제를 피하도록도와드릴 수 있습니다. 또한 Application Guard는 브라우저를 격리된 컨테이너에서 실행하여 브라우저 기반 위협을 격리하고 완화할 수 있습니다. 이러한 모든 기술은 Windows 10의 가상화 기반 보안을 사용하며, Windows 7에서는 복제할 수 없는 기본적인 변경 기능입니다. 또한 이러한 기능을 사용하려면 UEFI, 64비트 Windows 및 SLAT를 통한 가상화 확장 지원이 하드웨어 수준에서 구현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p113">Now beyond identity, you can also enable continuous protection against both known and unknown threats and to do this Windows 10 uses virtualization-based security at the core to ensure boot integrity and code integrity using Secure Boot. We can help also stop credential theft with Credential Guard by maintaining user secrets in isolation from Windows. And, Application Guard can isolate and mitigate browser-based threats by running the browser in an isolated container. All of these technologies use virtualization-based security in Windows 10 and are foundational changes that cannot be replicated on a Windows 7 system – note that these also require UEFI, 64-bit Windows and virtualization extension support with SLAT – at the hardware level.</span></span>

[<span data-ttu-id="05425-151">가상화 기반 보안에 대한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="05425-151">More on Virtualization-based Security</span></span>](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-vbs)

### <a name="security-enhancements-from-cloud-services"></a><span data-ttu-id="05425-152">클라우드 서비스를 통한 보안 향상</span><span class="sxs-lookup"><span data-stu-id="05425-152">Security enhancements from cloud services</span></span>

<span data-ttu-id="05425-p114">클라우드 서비스는 또 다른 선택적 보호 계층을 제공하여 Windows 및 Office 보안을 강화합니다. 이를 통해 대응 및 업데이트 배포 시간이 기본적으로 더 느린 전형적인 소프트웨어 업데이트 및 AV 서명 파일과 비교할 때 새로운 공격 및 공격 유형을 즉시 감지하고, 저항하고, 대응할 수 있는 새로운 수준의 실시간(대체적으로 지원) 제어 기능이 확보될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p114">Cloud services provide another layer of optional protection to improve Windows and Office security. These can give you a new level of often real-time control that can instantly detect, resist and respond to new attacks and attack types – especially compared to traditional software updating and AV signature files – where response and update deployment times are inherently slower.</span></span>

<span data-ttu-id="05425-p115">Microsoft Intelligent Security Graph를 사용하여 이러한 두 가지 정보에 빠르게 액세스하고 새로운 위협으로부터 보호할 수 있습니다. 다음은 활용할 수 있는 몇 가지 예제로, Office 관련 내용부터 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p115">Along with the Microsoft Intelligent Security Graph, you have faster access to both information and protections from emerging threats. Here are a few examples of what you can take advantage of, starting with Office.</span></span>

<span data-ttu-id="05425-p116">Office 365 ProPlus에 기본 제공되어 있는 **[데이터 손실 방지](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** 는 신용 카드 또는 주민 등록 번호와 같은 고위험 콘텐츠가 감지될 때 사용장게 보안 정책을 알리는 데 도움을 줍니다. 정책은 관련 정보를 제공하거나, 알림을 제공한 후에 전송 및 공유를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p116">**[Data Loss Prevention](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** built into Office 365 ProPlus, helps inform users of security policies when high risk content like credit card or identification numbers are detected. Policies can inform or block sending and sharing after notifying users.</span></span>

<span data-ttu-id="05425-p117">**[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** 은 Office에서 사용할 수 있는 보충 서비스로, 사용자들이 Office 파일을 쉽게 분류하고 레이블을 지정할 수 있도록 합니다. 또한 레이블이 지정된 파일에 대해 암호화 또는 공유 잠금과 같은 자동 작업을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p117">**[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** is a complementary service that can be used with Office, allowing users to easily classify and label their Office files. It can trigger automatic action on labeled files, such as encryption or locking down sharing.</span></span>

<span data-ttu-id="05425-161">Microsoft는 또한 Office 앱에 대해 **[안전한 링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)** 보호 기능도 제공합니다. 이 기능을 사용하면 알려진 악성 웹 사이트의 동적 목록의 사이트로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-161">We've also introduced **[Safe Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)** protection across Office apps to protect you against a dynamic list of known malicious websites.</span></span>

<span data-ttu-id="05425-p118">또한 Outlook 및 Exchange Online의 일부로 제공되는 **[안전한 첨부 파일](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)** 은 전자 메일 필터링 이상의 기능을 제공하여 첨부 파일을 검사합니다. 위험도가 높은 첨부 파일을 식별되면 안전한 첨부 파일 기능은 알려진 악성 첨부 파일을 사용자에게 알리고 전자 메일에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p118">Additionally, **[Safe Attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)** in Outlook and as part of Exchange Online goes beyond email filtering to inspect attachments. If a high-risk attachment is identified, Safe Attachments will inform the user of known malicious attachments and remove them from email.</span></span>

<span data-ttu-id="05425-p119">**[OEM(Office 365 메시지 암호화)](https://docs.microsoft.com/office365/securitycompliance/encryption)** 또한 전송된 전자 메일 및 첨부 파일을 보호하고, 의도한 받는 사람만 전자 메일 콘텐츠를 보도록 하는 데 사용될 수 있습니다. OME은 Google, Yahoo 및 Microsoft 소비자 계정 인증에서 원활하게 작동하며, 일회성 암호는 다른 전자 메일 서비스 사용자도 전자 메일을 안전하게 수신하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p119">**[Office 365 Message Encryption](https://docs.microsoft.com/office365/securitycompliance/encryption)** (OME) can also be used to safeguard email and attachments sent, ensuring only intended recipients can view email content. OME works seamlessly with Google, Yahoo, and Microsoft consumer account authentication, and one-time passcodes allow users of other email services to securely receive email as well.</span></span>

#### <a name="additional-windows-10-protections"></a><span data-ttu-id="05425-166">추가 Windows 10 보호</span><span class="sxs-lookup"><span data-stu-id="05425-166">Additional Windows 10 protections</span></span>

<span data-ttu-id="05425-167">Windows 10의 **[Windows Defender 응용 프로그램 컨트롤](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** 은 Microsoft가 안전을 확인한 승인된 허용 및 거부 응용 프로그램 목록과 Microsoft Intune을 사용하여 끝점 보호 정책이 관리하는 모든 응용 프로그램 목록을 운영합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-167">**[Windows Defender Application Control](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** in Windows 10 operates off an approved allow and deny list of applications that Microsoft has checked for safety and all that is managed by endpoint protection policies using Microsoft Intune.</span></span>

<span data-ttu-id="05425-p120">**[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** 은 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 이 플랫폼은 사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하고, 보안 태세를 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p120">**[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** is a unified platform for preventative protection, post-breach detection, automated investigation, and response. It protects endpoints from cyber threats; detects advanced attacks and data breaches, automates security incidents and improves security posture.</span></span>

<span data-ttu-id="05425-170">**[Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** 는 맬웨어가 Windows에 유입되지 않도록 하고, 신뢰할 수 없는 프로세스가 보호된 폴더에 액세스하지 못하도록 하여 실행 중인 응용 프로그램에 대한 공격 표면을 줄이는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05425-170">**[Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** helps reduce the attack surface for running applications by preventing malware from getting into Windows and blocking untrusted processes from accessing protected folders.</span></span>

#### <a name="microsoft-intune"></a><span data-ttu-id="05425-171">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="05425-171">Microsoft Intune</span></span>

<span data-ttu-id="05425-p121">[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune)은 IOS, Android 및 Windows 장치를 포함하는 모바일 시나리오에 대한 클라우드 기반 관리 서비스로 사용되며, 이제 공동 관리 부서에서 Configuration Manager에서 관리되는 특정 워크로드에 대한 컨트롤을 보완하고 확장하도록 구성할 수 있습니다. 한 가지 장점은 보호된 리소스에 액세스하는 장치 중에서 관리되지 않거나 도메인에 가입되지 않았거나 Azure AD에 가입되지 않은 모든 장치의 경우 장치 관리 부서에 등록하도록 요구할 수 있다는 것입니다. 또한 운영 체제 및 응용 프로그램 수준에서 세분화된 구성 및 준수 정책 적용을 활용할 수도 있습니다. 응용 프로그램 정책 및 설정을 중앙에서 구성하고, Microsoft Intune을 사용하여 Office 365 ProPlus 및 Windows 10의 스토어 앱에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05425-p121">[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) serves as a Cloud based management service for mobile scenarios, including IOS, Android and Windows devices, and can now be configured for co-management to complement and extend controls for specific workloads managed by Configuration Manager. One advantage here is that, devices accessing protected resources can be required to enroll into device management – even non-managed, non-domain joined or non-Azure AD joined devices. You can also take advantage of granular configuration and compliance policy enforcement at the operating system and application level. Application policies and settings can be configured centrally and enforced for Office 365 ProPlus and Store apps in Windows 10 using Microsoft Intune.</span></span>

## <a name="next-step"></a><span data-ttu-id="05425-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="05425-176">Next Step</span></span>

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[<span data-ttu-id="05425-177">6단계: 운영 체제 배포 및 기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="05425-177">Step 6: OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)

## <a name="previous-step"></a><span data-ttu-id="05425-178">이전 단계</span><span class="sxs-lookup"><span data-stu-id="05425-178">Previous Step</span></span> 

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="05425-179">4단계: 사용자 파일 및 설정</span><span class="sxs-lookup"><span data-stu-id="05425-179">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)
