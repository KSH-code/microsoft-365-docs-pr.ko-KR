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
# <a name="step-5-security-and-compliance-considerations"></a>5단계: 보안 및 준수 고려 사항

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><strong>5단계: 보안 및 준수 고려 사항</strong></p>
<p>Windows 10 및 Office 365 ProPlus는 데이터, 장치 및 사용자를 보호하고 위협을 빠르게 감지하고 대응하는 새로운 방법을 제공합니다. 또한 디스크 암호화, 맬웨어 방지 앱 및 Windows 10으로 전환할 때의 정책과 관련된 일반적인 문제를 처리하는 방법도 알아봅니다.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>보안 및 규정 준수는 Windows 10/Office 365 ProPlus 보안 및 준수 고려 사항을 포함하는 권장 배포 프로세스 사이클의 5번째 단계입니다. 전체 데스크톱 배포 프로세스를 보려면 [데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.
>

이제 이전 버전의 Windows 및 Office에서 전환하는 경우의 고려 사항 및 일반적인 방해 요인과 함께, Windows 10 및 Office 365 ProPlus 배포의 일부로서 새로운 보안 및 준수 기능을 목표로 구현하기 위한 옵션을 검토할 차례입니다. 많은 보안 관련 기능 때문에 최신 플랫폼인 Windows 10으로의 전환이 추진되고 있습니다. 또한 Office 365의 클라우드 서비스와의 통합과 Azure Active Directory를 사용하는 ID 옵션을 통해 데이터, 장치 및 사용자를 위한 새롭거나 지속적으로 업데이트되는 보호 기능을 활용할 수 있습니다.

## <a name="overcoming-potential-security-related-deployment-blockers"></a>잠재적인 보안 관련 배포 방해 요인 극복

Windows 10 및 Office 365 ProPlus로 전환하고 이러한 환경을 클라우드에 연결할 때 추가할 수 있는 새로운 기능을 설명하기 전에, 배포 진행을 중단시킬 수 있는 몇 가지 추세부터 살펴보겠습니다.

### <a name="disk-encryption"></a>디스크 암호화

초기에 겪게 되는 난제 중 하나가 하드 디스크 암호화입니다. 하드 디스크 암호화용 솔루션 대부분은 이전 버전의 Windows에서 최신 버전의 Windows로 업그레이드할 수 없습니다.

일부 디스크 암호화 솔루션에서는 특정 버전의 플랫폼에서 Windows 설치 프로그램과 함께 ‘/reflectdrivers’ 옵션을 사용하여 업그레이드를 수행할 수 있지만, 일부 솔루션에서는 배포 전에 드라이브의 암호를 해독했다가 Windows 10을 설치한 후 다시 암호화해야 할 수 있습니다. 또한 일부 플랫폼에서는 레거시 BIOS를 사용하여 MBR(마스터 부트 레코드)에서 UEFI에 필요한 GPT(GUID 파티션 테이블)로 전환할 수 없습니다. 이러한 문제는 UEFI가 있는 Windows 10 64비트가 아래에 설명된 Windows 10의 새로운 가상화 기반 보안 기능에 필요하기 때문에 중요합니다.

이러한 문제를 해결하기 위한 한 가지 옵션은 Windows 10 Pro 이상 버전에 포함된 Windows 10의 BitLocker를 사용하는 것입니다. BitLocker를 사용하면 프로세스의 일부로 OS 업그레이드 및 기능 업데이트에 대한 보호를 일시 중단할 수 있습니다.

[Bitlocker 기본 배포](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)

### <a name="antivirus-and-antimalware-application-compatibility"></a>바이러스 백신 및 맬웨어 방지 응용 프로그램 호환성

둘째, Windows 7과 Windows 10 사이에서 [99% 이상의 Windows 응용 프로그램이 호환된다고](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) 확인되었으나, 종종 AV(바이러스 백신) 앱 또는 VPN(가상 사설망) 클라이언트에서 예외가 나타납니다. 이러한 응용 프로그램은 종종 비표준 개발 사례와 API를 구현하며, 문서화되지 않은 방식을 사용해서 시스템을 보호하거나 네트워크 리소스에 연결하려고 합니다.

결과적으로 이러한 앱은 본질적으로 새 버전의 Windows로 전환할 때 변화에 취약할 수 있습니다. AV 또는 VPN 소프트웨어가 Windows 10에서 또는 업그레이드 이후에 작동하지 않을 경우 사용 중인 앱을 Windows 10에서 지원되는 테스트를 거친 앱으로 바꿀 수 있습니다.

### <a name="security-policies"></a>보안 정책

이전 버전의 Windows 및 Office에 사용되는 Active Directory 그룹 정책 설정은 Windows 10 및 Office 365 ProPlus로 직접 변환되지 않을 수 있으며, 최신 보안 및 준수 기능에 따라 고려 사항도 달라집니다. Microsoft 보안 규정 준수 도구 키트를 사용하여 현재 버전의 Windows 및 Office에 대한 보안 정책 기준을 확인하는 것이 좋습니다. 또한 Microsoft Intune의 일부로 모바일 장치 관리 정책을 살펴보는 것도 유용할 수 있습니다.

![](../media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a>Microsoft 365의 새로운 보안 및 규정 준수 기능

지금까지 최신 보호를 적용하기 위한 고려 사항과 전환 전에 알아야할 사항에 대해 살펴보았습니다. 이제, Windows 10, Office 365 ProPlus 및 EMS의 클라우드 기반 옵션 이상으로 전환할 때 이용할 수 있는 새로운 기능을 살펴보겠습니다.

### <a name="identity-and-access-management"></a>ID 및 액세스 관리

ID 및 액세스 관리를 먼저 살펴보겠습니다. Azure Active Directory는 앱, 장치 및 클라우드 서비스에 대한 ID 제어 평면으로, Office 365 및 기타 클라우드 서비스에 연결하는 최신 방법입니다. 조건부 액세스를 사용하면 로그인한 위치, 사용 중인 장치, 비정상적인 동작 등을 토대로 다양한 인증 요구 사항을 정의할 수 있습니다.

장치 수준에서 생체 인식은 암호를 없애는 목표를 달성하면서 좀 더 간편하고 안전하게 장치 및 앱에 액세스하기 위한 고유한 식별자를 제공할 수 있습니다. Windows Hello는 장치 기반, 다단계 인증을 제공합니다. 이 기능은 정책을 통해 장치 자체, 사용자의 PIN 또는 고유한 생체 인식 식별자(예: 얼굴 또는 지문)를 활용합니다.

[Azure ID 관리의 기본 사항](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-fundamentals)

[Azure ID 솔루션 이해](https://docs.microsoft.com/azure/active-directory/fundamentals/understand-azure-identity-solutions)

[Azure Active Directory 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

[비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)

### <a name="virtualization-based-security"></a>가상화 기반 보안

이제 ID를 사용하는 것 외에도, 알려진 위협과 알려지지 않은 위협에 대해 지속적인 보호를 설정할 수 있습니다. 이를 위해 Windows 10에서는 핵심 영역에서 가상화 기반 보안을 사용하여 보안 부트를 통해 부팅 무결성 및 코드 무결성을 보장합니다. Microsoft는 Credential Guard를 통해 사용자 비밀을 Windows와 따로 유지 관리함으로써 자격 증명을 도난당하는 문제를 피하도록도와드릴 수 있습니다. 또한 Application Guard는 브라우저를 격리된 컨테이너에서 실행하여 브라우저 기반 위협을 격리하고 완화할 수 있습니다. 이러한 모든 기술은 Windows 10의 가상화 기반 보안을 사용하며, Windows 7에서는 복제할 수 없는 기본적인 변경 기능입니다. 또한 이러한 기능을 사용하려면 UEFI, 64비트 Windows 및 SLAT를 통한 가상화 확장 지원이 하드웨어 수준에서 구현되어야 합니다.

[가상화 기반 보안에 대한 추가 정보](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-vbs)

### <a name="security-enhancements-from-cloud-services"></a>클라우드 서비스를 통한 보안 향상

클라우드 서비스는 또 다른 선택적 보호 계층을 제공하여 Windows 및 Office 보안을 강화합니다. 이를 통해 대응 및 업데이트 배포 시간이 기본적으로 더 느린 전형적인 소프트웨어 업데이트 및 AV 서명 파일과 비교할 때 새로운 공격 및 공격 유형을 즉시 감지하고, 저항하고, 대응할 수 있는 새로운 수준의 실시간(대체적으로 지원) 제어 기능이 확보될 수 있습니다.

Microsoft Intelligent Security Graph를 사용하여 이러한 두 가지 정보에 빠르게 액세스하고 새로운 위협으로부터 보호할 수 있습니다. 다음은 활용할 수 있는 몇 가지 예제로, Office 관련 내용부터 제공됩니다.

Office 365 ProPlus에 기본 제공되어 있는 **[데이터 손실 방지](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)** 는 신용 카드 또는 주민 등록 번호와 같은 고위험 콘텐츠가 감지될 때 사용장게 보안 정책을 알리는 데 도움을 줍니다. 정책은 관련 정보를 제공하거나, 알림을 제공한 후에 전송 및 공유를 차단할 수 있습니다.

**[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)** 은 Office에서 사용할 수 있는 보충 서비스로, 사용자들이 Office 파일을 쉽게 분류하고 레이블을 지정할 수 있도록 합니다. 또한 레이블이 지정된 파일에 대해 암호화 또는 공유 잠금과 같은 자동 작업을 트리거할 수 있습니다.

Microsoft는 또한 Office 앱에 대해 **[안전한 링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)** 보호 기능도 제공합니다. 이 기능을 사용하면 알려진 악성 웹 사이트의 동적 목록의 사이트로부터 보호할 수 있습니다.

또한 Outlook 및 Exchange Online의 일부로 제공되는 **[안전한 첨부 파일](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)** 은 전자 메일 필터링 이상의 기능을 제공하여 첨부 파일을 검사합니다. 위험도가 높은 첨부 파일을 식별되면 안전한 첨부 파일 기능은 알려진 악성 첨부 파일을 사용자에게 알리고 전자 메일에서 제거합니다.

**[OEM(Office 365 메시지 암호화)](https://docs.microsoft.com/office365/securitycompliance/encryption)** 또한 전송된 전자 메일 및 첨부 파일을 보호하고, 의도한 받는 사람만 전자 메일 콘텐츠를 보도록 하는 데 사용될 수 있습니다. OME은 Google, Yahoo 및 Microsoft 소비자 계정 인증에서 원활하게 작동하며, 일회성 암호는 다른 전자 메일 서비스 사용자도 전자 메일을 안전하게 수신하도록 할 수 있습니다.

#### <a name="additional-windows-10-protections"></a>추가 Windows 10 보호

Windows 10의 **[Windows Defender 응용 프로그램 컨트롤](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** 은 Microsoft가 안전을 확인한 승인된 허용 및 거부 응용 프로그램 목록과 Microsoft Intune을 사용하여 끝점 보호 정책이 관리하는 모든 응용 프로그램 목록을 운영합니다.

**[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview)** 은 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합 플랫폼입니다. 이 플랫폼은 사이버 위협으로부터 끝점을 보호하고, 고급 공격 및 데이터 위반을 감지하고, 보안 인시던트를 자동화하고, 보안 태세를 개선합니다.

**[Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** 는 맬웨어가 Windows에 유입되지 않도록 하고, 신뢰할 수 없는 프로세스가 보호된 폴더에 액세스하지 못하도록 하여 실행 중인 응용 프로그램에 대한 공격 표면을 줄이는 데 도움을 줍니다.

#### <a name="microsoft-intune"></a>Microsoft Intune

[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune)은 IOS, Android 및 Windows 장치를 포함하는 모바일 시나리오에 대한 클라우드 기반 관리 서비스로 사용되며, 이제 공동 관리 부서에서 Configuration Manager에서 관리되는 특정 워크로드에 대한 컨트롤을 보완하고 확장하도록 구성할 수 있습니다. 한 가지 장점은 보호된 리소스에 액세스하는 장치 중에서 관리되지 않거나 도메인에 가입되지 않았거나 Azure AD에 가입되지 않은 모든 장치의 경우 장치 관리 부서에 등록하도록 요구할 수 있다는 것입니다. 또한 운영 체제 및 응용 프로그램 수준에서 세분화된 구성 및 준수 정책 적용을 활용할 수도 있습니다. 응용 프로그램 정책 및 설정을 중앙에서 구성하고, Microsoft Intune을 사용하여 Office 365 ProPlus 및 Windows 10의 스토어 앱에 적용할 수 있습니다.

## <a name="next-step"></a>다음 단계

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[6단계: 운영 체제 배포 및 기능 업데이트](https://aka.ms/mdd6)

## <a name="previous-step"></a>이전 단계 

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[4단계: 사용자 파일 및 설정](https://aka.ms/mdd4)
