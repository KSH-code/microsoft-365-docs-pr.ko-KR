---
title: Microsoft 365 Enterprise services 개요 | Microsoft Docs
description: 이 콘텐츠는 Microsoft 365 엔터프라이즈 및 엔터프라이즈 사용 권장 사항에 대 한 개요를 제공 합니다.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290163"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 엔터프라이즈 서비스 및 개념

Microsoft 365 Enterprise는 대규모 조직을 위해 설계되었으며 Office 365 Enterprise, Window s 10 Enterprise 및 EMS(Enterprise Mobility + Security)와 통합하여 모든 사용자가 독창적이고 안전하게 함께 작업할 수 있도록 합니다. Microsoft 365 Enterprise에는 Windows 10 엔터프라이즈 버전 및 Office 365 ProPlus를 통한 Office 응용 프로그램이 포함됩니다.

Windows 10 및 Office 365 ProPlus 모두 3월과 9월에 새 기능 릴리스를 반기 채널을 통해 엔터프라이즈에 제공합니다. 반기 채널의 기능 릴리스는 18개월 동안 지원됩니다. Microsoft Intune 및 System Center Configuration Manager 모두 Windows 10과 Office 365 ProPlus를 배포하고 업데이트하는 기능을 제공합니다.

다음은 Windows 10, Office 365 ProPlus, Microsoft Intune 및 System Center Configuration Manager의 최신 버전입니다.

|     |**반기별 채널(지정됨)**|**반기 채널**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update(출시 예정)|버전 1703|
|**Office 365 ProPlus**|버전 1803|버전 1708|
|**Intune**|해당 없음|버전 1708|
|**System Center Configuration Manager**|기술 미리 보기 버전 1708|버전 1706<sup>*</sup>|

<sup>*</sup> System Center Configuration Manager 현재 분기의 업데이트 1706은 버전 1606, 1610 또는 1702를 실행하는 이전에 설치된 사이트에 대한 콘솔 내 업데이트로 제공됩니다.

> [!NOTE]
> Microsoft Azure 서비스도 정기적으로 업데이트되지만 버전 번호에서 참조되지 않습니다. Azure 서비스의 최신 업데이트와 향후 예정 사항을 검토하려면 [클라우드 플랫폼 로드맵](https://www.microsoft.com/cloud-platform/roadmap)을 참조하세요.

이러한 버전에서 사용할 수 있는 기능에 대한 자세한 내용은 다음 문서를 참조하세요.
- [Windows 10의 새로운 기능](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10 릴리스 정보](https://technet.microsoft.com/windows/release-info)
- [Windows 10 업데이트 기록](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365 클라이언트 업데이트 채널 릴리스](https://technet.microsoft.com/office/mt465751)
- [Microsoft Intune의 새로운 기능](https://docs.microsoft.com/intune/whats-new)
- [System Center Configuration Manager의 새로운 기능](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [System Center Configuration Manager용 기술 미리 보기 1708의 기능](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>서비스 개요

이 단원에서는 Microsoft 365 Enterprise에 포함된 EMS 및 Office 365 서비스에 대한 개요를 제공하고 조직의 필요에 따라 가장 잘 활용하는 방법을 이해하는 데 필요한 핵심 개념도 소개합니다. 이러한 서비스는 Microsoft 클라우드 엔터프라이즈 관리자가 회사 직원의 ID와 장치를 보호할 뿐만 아니라 회사 데이터(전송 중인 데이터 및 미사용 데이터 둘 다) 자체에 대한 액세스도 제어할 수 있는 기능을 제공합니다.

|서비스|설명|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD는 다단계 인증, 장치 등록, 셀프 서비스 암호 관리, 셀프 서비스 그룹 관리, 역할 기반 액세스 제어, 응용 프로그램 사용 모니터링, 다양한 감사, 보안 모니터링 및 경고 등 전체 ID 관리 기능을 제공합니다.|
|[Azure AD ID 보호](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|이 서비스를 사용하면 조직의 ID에 영향을 미치는 잠재적인 취약점을 검색하고 낮음, 보통 및 높음 로그인 위험 및 사용자 위험에 대해 조건부 액세스 정책을 통해 자동화된 응답을 구성할 수 있습니다.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|이 서비스를 사용하면 조직은 권한 있는 작업에 영구 액세스 권한이 있는 사용자 수를 최소화할 수 있습니다. Azure AD Privileged Identity Management는 적격 관리자 개념을 소개합니다. 적격 관리자는 매일이 아니라 가끔 권한 있는 액세스가 필요한 사용자여야 합니다. 역할은 사용자가 액세스를 필요로 할 때까지 비활성화 상태이다가 활성화 프로세스를 완료하면 미리 결정된 시간 동안 활성 관리자가 됩니다.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection은 EMS E5 제품의 일환으로 제공되는 클라우드 기반 솔루션으로 조직에서 문서와 메일을 분류하고 레이블을 지정하며 보호하는 데 도움이 됩니다. 이 기능은 규칙 및 조건을 정의하는 관리자는 자동으로, 사용자는 수동으로 수행할 수 있으며, 사용자가 권장 사항을 제공받은 경우에는 자동 또는 수동으로 수행할 수 있습니다. Azure Information Protection 레이블을 사용하여 문서와 전자 메일을 분류할 수 있습니다. 이 작업을 수행하면 데이터가 저장된 위치나 데이터를 공유한 사용자가 누구인지와 관계없이 항상 분류를 식별할 수 있게 됩니다.<br><br>Azure Information Protection 정책 설정은 [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)로 보호됩니다. 레이블이 적용되는 방법과 마찬가지로 Rights Management를 사용하여 적용된 보호 기능은 조직, 네트워크, 파일 서버, 응용 프로그램 내/외의 위치와 관계없이 문서와 메일에 계속 적용됩니다.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune은 직원이 회사 데이터를 보호하면서 생산성을 높일 수 있도록 하는 클라우드 기반 엔터프라이즈 이동성 관리(EMM) 서비스입니다. Intune은 ID 및 액세스 제어에 대해 Azure AD와 긴밀하게 통합되며 장치 및 응용 프로그램 관리에 사용됩니다. [Intune의 장치 관리](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) 기능은 Windows PC를 비롯하여 사용자의 장치를 구성하고 보호하는 데 사용됩니다.<br><br>Intune 장치 관리 기능은 사용자가 개인 휴대폰, 태블릿 또는 PC를 등록할 수 있는 [BYOD(Bring Your Own Device)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 등록과 자동 등록, 공유 장치 또는 사전 승인된 등록 요구 사항 구성 같은 관리 시나리오를 사용할 수 있는 [COD(회사 소유 장치)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 등록을 모두 지원합니다. 추가 보안을 위해 장치를 등록하려면 MFA가 필요할 수 있습니다. 관리로 등록되면 Intune은 장치 기능 및 설정을 구성하여 회사 리소스에 대해 보안 액세스를 사용할 수 있습니다.|

## <a name="important-concepts-to-understand"></a>이해 해야 할 중요 한 개념
아래 표에는 사용자가 익숙해지는 핵심 개념 및 EMS 기능이 설명 되어 있습니다.

|핵심 개념|설명|
|------------|-----------|
|[Azure MFA (multi-factor Authentication)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Microsoft의 2 단계 인증 솔루션으로 Azure MFA는 간단한 로그인 프로세스에 대 한 사용자 요구를 충족 하는 동안 데이터 및 응용 프로그램에 대 한 액세스를 보호 하는 데 도움이 됩니다. 전화 통화, 문자 메시지 또는 모바일 앱 확인을 비롯 한 다양 한 확인 방법을 통해 강력한 인증을 제공 합니다.|
|[Azure AD 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD의이 기능을 사용 하면 특정 조건에 따라 환경의 클라우드 앱에 대 한 액세스에 컨트롤을 적용할 수 있습니다. 컨트롤을 사용 하 여 추가 요구 사항을 액세스에 연결 하거나 차단할 수 있습니다. 조건부 액세스 구현은 정책을 기반으로 합니다.|
|[Exchange Online DLP (데이터 손실 방지)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|exchange online 계획 2 및 office 365 구독의 프리미엄 기능으로 사용할 수 있는 exchange online DLP (데이터 손실 방지) 정책을 사용 하 여 조직에서 Office 365의 중요 한 정보를 식별, 모니터링 및 자동으로 보호할 수 있습니다.<br><br>exchange online DLP 정책을 사용 하 여 exchange online, SharePoint online 및 비즈니스용 OneDrive와 같은 다양 한 위치에서 중요 한 정보를 확인할 수 있습니다. 예를 들어 이러한 정책을 사용 하면 중요 한 정보가 포함 된 문서를 식별 하거나 조직 외부의 사용자와 실수로 중요 한 정보가 공유 되지 않도록 할 수 있습니다.|
|[Exchange 메일 흐름/전송 규칙](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)은 조직을 통과 하 고 작업 하는 메시지에서 특정 조건을 찾습니다. 메일 흐름 규칙은 여러 전자 메일 클라이언트에서 사용할 수 있는 받은 편지함 규칙과 같습니다. Outlook과 같이 클라이언트 응용 프로그램에서 설정 하는 메일 흐름 규칙과 규칙의 주요 차이점은 메시지가 배달 된 후와 반대로 메시지가 전송 중일 때 메일 흐름 규칙이 메시지에 작용 한다는 점입니다. 또한 메일 흐름 규칙에는 여러 유형의 메시징 정책을 구현 하는 유연성을 제공 하는 다양 한 조건, 예외 및 작업 집합이 포함 되어 있습니다.|
|[Intune 모바일 장치 관리](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune에서는 모바일 운영 체제에서 사용할 수 있는 프로토콜 또는 api를 사용 하 여 MDM (모바일 장치 관리)을 제공 합니다. 여기에는 장치를 관리로 등록 하 여 회사 서비스에 액세스 하는 장치에 대 한 인벤토리를 포함 하 고, 장치를 구성 하 여 회사의 보안 및 상태 표준을 충족 하 고 인증서 및 wi-fi/VPN 프로필을 제공 하는 등의 작업을 수행 합니다. 회사 서비스 액세스, 보고 설정 및 회사 표준에 대 한 장치 준수 측정 및 관리 되는 장치에서 회사 데이터 제거|
|[Intune 앱 보호 정책](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Intune 앱 보호 정책을 사용 하 여 관리에 장치를 등록 하거나 포함 하지 않고 모바일 앱에서 회사의 데이터를 보호할 수 있습니다. 실제로 [Intune이 Office 365 정보를 보호](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)하는 동안 타사 MDM 솔루션을 사용 하 여 사용자의 모바일 장치를 관리할 수도 있습니다. 직원 들이 계속 생산적으로 작업할 수 있도록 하면서 의도적이 고 의도 하지 않은 데이터 손실을 방지할 수도 있습니다. 응용 프로그램 수준 정책을 구현 하 여 회사 리소스에 대 한 액세스를 제한 하 고 IT 부서의 통제 내에서 데이터를 유지할 수 있습니다.|
|[Azure AD 토큰 수명](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|azure Active Directory (azure AD)에서 발급 한 토큰의 수명을 지정할 수 있습니다. 조직의 모든 앱, 다중 테 넌 트 (다중 조직) 응용 프로그램 또는 조직의 특정 서비스 사용자에 대해 토큰 수명을 설정할 수 있습니다.|
|Microsoft id 브로커|Microsoft는 다양 한 공급 업체의 응용 프로그램 간 자격 증명 브리징을 허용 하 고 자격 증명의 유효성을 검사 하는 데 사용할 수 있는 단일 안전한 위치를 필요로 하는 특수 한 향상 된 기능을 제공 하는 모든 모바일 플랫폼용 응용 프로그램 이 브로커를 호출 합니다. iOS 및 Android에서 이러한 브로커는 Microsoft 인증자 및 Intune 회사 포털 앱을 통해 제공 됩니다. Windows 10에서이 기능은 기술적으로 웹 인증 브로커 라고 알려진 운영 체제에 기본적으로 제공 되는 계정 선택에 의해 제공 됩니다.|

## <a name="security-best-practices-and-recommendations"></a>보안 모범 사례 및 권장 사항
모든 고객 환경에 꼭 맞는 단일 권장 사항은 없지만 [권장 보안 정책 및 구성](microsoft-365-policies-configurations.md) 문서에서는 이해가 필요한 중요 보안 모범 사례 개념을 소개합니다. 또한 직원들의 보안과 생산성을 모두 유지하기 위해 Microsoft 클라우드 내에서 정책 및 구성을 적용하는 방법에 대한 일반적인 Microsoft 권장 사항에 대해서도 다룹니다.

### <a name="baseline-recommended-security-policies-and-configurations"></a>권장 되는 초기 보안 정책 및 구성
[일반 id 및 장치 액세스 정책 권장 사항은](identity-access-policies.md) Microsoft 365 엔터프라이즈 보안을 유지 하는 데 도움이 되는 일반적인 권장 정책을 설명 합니다. 조건부 액세스에 대한 기술적인 필수 구성 요소뿐만 아니라 사용자에게 최상의 SSO 환경을 제공하기 위해 Microsoft에서 권장하는 기본 플랫폼 클라이언트 구성에 대해서도 설명합니다.

### <a name="exchange-online-access-policies"></a>Exchange Online 액세스 정책
[전자 메일 보안에 도움이 되는 정책 권장 사항은](secure-email-recommended-policies.md) 최신 인증 및 조건부 액세스를 지 원하는 전자 메일 클라이언트와 조직의 전자 메일을 보호 하는 데 도움이 되는 Microsoft 권장 사항을 제공 합니다. [일반 ID 및 액세스 권장 사항](identity-access-policies.md)에 추가되는 내용입니다.

### <a name="sharepoint-online-access-policies"></a>SharePoint Online 액세스 정책
[일반 id 및 액세스 정책](identity-access-policies.md) 권장 사항 외에도 [SharePoint Online 파일 액세스를 보호](sharepoint-file-access-policies.md) 하기 위한 권장 사항과 [전자 메일 보안에 도움이 되는 정책 권장](secure-email-recommended-policies.md)사항을 제공 합니다. 이 문서에서는 Exchange online 전자 메일과 SharePoint online 파일 액세스를 모두 보호 하기 위해 만들어야 하는 새 정책과 기존 정책을 수정 하는 방법에 대해 설명 합니다.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Windows 10 및 Office 365 ProPlus 배포
Windows 10 및 Office 365 ProPlus를 배포하고 Microsoft Azure AD(Azure Active Directory) 또는 온-프레미스 AD DS(Active Directory Domain Services)에 통합하는 방법을 알아보세요. Windows 10, Office 365 ProPlus 및 다른 기간 업무 앱을 새 장치에 배포하거나 Intune, System Center Configuration Manager 및 그룹 정책을 사용하여 기존 장치를 Windows 10으로 업그레이드하고 장치를 관리하세요.

자세한 내용은 다음 문서를 참조하십시오.
- [Windows 10 배포 고려 사항](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Office 365 ProPlus의 배포 가이드](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [엔터프라이즈에서 Office 365 ProPlus를 배포하는 모범 사례 가이드](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [Intune을 사용하여 Office 365 ProPlus 앱을 Windows 10 장치에 배포](https://docs.microsoft.com/intune/apps-add-office365)

Microsoft 365를 통한 배포 지원은 [FastTrack에 문의하세요](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Windows 10 및 Office 365 ProPlus로의 업데이트 관리
다음 링크에서는 Windows 10 및 Office 365 ProPlus의 품질과 기능 업데이트를 최대한 제어할 수 있는 방법을 소개합니다. 대역폭 사용량을 효율적으로 제어하고 최신 기능, 기능 및 보안 업데이트를 통해 Windows 및 Office를 최신 상태로 유지하는 방법을 알아보세요.

자세한 내용은 다음 문서를 참조하십시오.
- [Windows as a service 개요](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Office 365 ProPlus의 업데이트 채널 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Intune을 통한 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [System Center Configuration Manager를 사용하여 Windows 10 업데이트 배포](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Configuration Manager를 사용하여 Office 365 ProPlus 관리](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft는 Windows 업데이트 관리를 위해 현재 Configuration Manager를 사용하는 조직이 Windows 10 클라이언트 컴퓨터에 대해서도 계속 동일한 작업을 수행하도록 권장합니다.

## <a name="next-steps"></a>다음 단계
[Microsoft 365 Enterprise 제품 페이지](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[클라우드 플랫폼 로드맵](https://www.microsoft.com/cloud-platform/roadmap)
