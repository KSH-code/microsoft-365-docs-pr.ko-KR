---
title: Contoso Corporation의 Microsoft 365 Enterprise 보안 요약
author: JoeDavies-MSFT
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
ms.openlocfilehash: fd3f73919a113389e9d423dbed11cf0074fb5833
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802063"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation의 Microsoft 365 Enterprise 보안 요약

IT 보안 부서에서 Microsoft 365 Enterprise 배포 작업의 승인을 얻기 위해 철저한 보안 검토가 수행되었습니다. 다음은 클라우드에 대한 Contoso의 보안 요구 사항입니다.

- 클라우드 리소스에 대한 직원 액세스에 가장 강력한 인증 방법을 사용합니다.
- PC 및 모바일 장치가 안전한 방법으로 응용 프로그램을 연결하고 액세스하는지 확인합니다.
- PC 및 전자 메일이 악의적인 소프트웨어로부터 보호됩니다.
- 클라우드 기반 디지털 자산에 대한 권한은 누가 어떤 기능에 액세스할 수 있는지와 수행할 수 있는 작업 및 최소 권한 액세스로 디자인된 대상을 정의합니다.
- 중요 및 높은 규제 대상 디지털 자산은 레이블이 지정되고 암호화된 후 안전한 위치에 저장됩니다.
- 높은 규제 대상 디지털 자산은 추가적인 암호화와 사용 권한으로 보호됩니다.
- IT 보안 직원은 중앙 대시보드에서 현재의 보안 태세를 모니터링하고, 빠른 대응 및 완화를 위해 보안 이벤트 알림을 받을 수 있습니다.

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contoso의 Microsoft 365 보안 준비 과정

Contoso는 다음 단계에 따라 Microsoft 365 Enterprise 배포에 대한 보안을 준비했습니다.

1. 클라우드용 관리자 계정 제한

   Contoso는 기존 Active Directory Domain Services (AD DS) 관리자 계정을 포괄적으로 검토하여 일련의 전용 클라우드 관리자 계정 및 그룹을 설정했습니다.

2. 3개 수준으로 데이터 분류 분석 수행

   Contoso는 철저한 검토를 수행한 후 3개 수준을 결정했으며, 이러한 수준을 사용하여 Contoso의 가장 중요한 데이터를 보호하기 위한 Microsoft 365 Enterprise 기능을 결정했습니다.

3. 데이터 수준에 대한 액세스, 보존 및 정보 보호 정책 결정

   Contoso는 데이터 수준에 따라 상세 요구 사항을 결정했으며, 이러한 요구 사항을 사용하여 향후 클라우드로 이동하는 IT 작업을 선별할 예정입니다.

Contoso의 보안 관리자 및 IT 부서는 보안 모범 사례 및 Microsoft 365 Enterprise 배포 요구 사항에 따라, 다음 섹션에 설명된 것과 같은 많은 보안 기능을 배포했습니다.

## <a name="identity--access-management"></a>ID 및 액세스 관리 

- MFA 및 PIM이 있는 전용 전역 관리자 계정

  일상적인 사용자 계정에 전역 관리자 역할을 할당하지 않고, Contoso는 강력한 암호를 가지는 3개의 전용 전역 관리자 계정을 만든 후, Azure 다단계 인증 (MFA )및 Azure 활성 디렉터리 (Azure AD), 특권 계정 관리 (PIM)로 보호했습니다. PIM은 Microsoft 365 E5에서만 사용할 수 있습니다.

  전역 관리자 계정을 사용한 로그인은 특정 관리 작업에 대해서만 수행되고, 암호는 지정된 직원만 알고 있으며, Azure AD PIM을 사용하여 구성된 시간 내에서만 사용할 수 있습니다. 

  Contoso의 보안 관리자는 해당 IT 사용자의 직무와 책임에 적합한 더 적은 관리자 역할을 계정에 할당했습니다.

  자세한 내용은 [Office 365 관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)를 참조하세요.

- 모든 사용자 계정에 대한 MFA

  MFA는 사용자에게 암호를 올바르게 입력한 후에 스마트폰에서 전화 통화, 문자 메시지 또는 앱 알림을 승인하도록 요구함으로써 추가적인 로그인 프로세스 보호 계층을 제공합니다. MFA를 사용할 경우 Azure AD 사용자 계정은 계정 암호가 손상된 경우에도 무단 로그인으로부터 보호됩니다.

   - Contoso는 Microsoft 365 구독이 손상되지 않도록 보호하기 위해 모든 전역 관리자 계정에서 MFA를 요구합니다.
   - Contoso는 공격자가 조직에서 신뢰할 수 있는 사용자의 자격 증명을 손상하고 악의적인 전자 메일을 보내는 피싱 공격으로부터 보호하기 위해 관리자 및 임원을 비롯한 모든 사용자 계정에서 MFA를 사용하도록 설정했습니다. 

- 조건부 액세스 정책을 사용한 보다 안전한 장치 및 응용 프로그램 액세스

  Contoso는 ID, 장치, Exchange Online 및 SharePoint에 대해 [조건부 액세스 정책](microsoft-365-policies-configurations.md)을 사용하고 있습니다. ID 조건부 액세스 정책에는 높은 위험에 처한 사용자에게 암호 변경 요구, 클라이언트가 최신 인증을 지원하지 않는 앱을 사용하지 못하도록 지정 등이 포함됩니다. 장치 정책에는 승인된 앱의 정의와 규격 PC 및 모바일 장치 요구가 포함됩니다. Exchange Online 조건부 액세스 정책에는 ActiveSync 클라이언트 차단 및 Office 365 메시지 암호화 설정이 포함됩니다. SharePoint 조건부 액세스 정책에는 중요 및 높은 규제 대상 사이트에 대한 추가적인 보호가 포합됩니다.

- 비즈니스용 Windows Hello

  Contoso는 [비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)를 배포했으며, Windows 10 Enterprise를 실행하는 PC 및 모바일 장치에서 강력한 2단계 인증을 사용하여 암호가 필요하지 않도록 합니다.

- Windows Defender Credential Guard

  관리 권한을 사용하여 운영 체제에서 실행되는 표적 공격 및 악성 소프트웨어를 차단하기 위해 Contoso는 AD DS 그룹 정책을 통해 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)를 사용하도록 설정했습니다.

## <a name="threat-protection"></a>위협 방지

- Windows Defender 바이러스 백신으로 맬웨어로부터 보호

  Contoso는 Windows 10 Enterprise가 실행되는 PC 및 장치에 대해 맬웨어 보호 및 맬웨어 방지 관리를 제공하기 위해 [Windows Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)을 사용하고 있습니다.

- Office 365 고급 위협 방지 기능으로 전자 메일 흐름 및 사서함 감사 로깅 보호 

  Contoso는 Exchange Online Protection 및 [Office 365 Threat Protection ATP(Advanced)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)를 사용하여 알 수 없는 맬웨어, 바이러스 및 전자 메일을 통해 전송되는 악성 URL로부터 보호하고 있습니다. 

  Contoso는 또한 사용자 사서함에 로그인한 사람, 보낸 메시지 및 사서함 소유자, 위임된 사용자 또는 관리자가 수행한 기타 활동을 확인하기 위해 사서함 감사 로깅을 사용하도록 설정했습니다.

- Office 365 위협 조사와 응답으로 공격 모니터링 및 방지

  Contoso는 [Office 365 위협 조사 및 응답](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)을 사용하여 공격을 보다 쉽게 식별 및 해결하고 후속 공격을 방지함으로써 Office 365 사용자를 보호합니다.

- Advanced Threat Analytics를 사용하여 정교한 공격으로부터 보호

  Contoso는 [ATA(Advanced Threat Analytics)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata)를 사용하여 타기팅된 고급 공격으로부터 자체적으로 보호합니다. ATA는 정상 및 비정상 엔터티(사용자, 장치, 리소스) 동작을 자동으로 분석, 학습 및 식별합니다. 

## <a name="information-protection"></a>정보 보호

- Azure Information Protection 레이블을 사용하여 중요 및 높은 규제 대상 디지털 자산 보호

  Contoso는 세 가지 수준의 데이터 보호를 결정하고, 사용자가 디지털 자산에 적용하는 [Office 365 민감성 레이블](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)을 배포했습니다. 또한 영업 비밀 및 기타 지적 재산권의 경우 콘텐츠를 암호화하고 특정 사용자 계정 및 그룹으로의 액세스를 제한하는 높은 규제 대상 데이터에 대해서는 민감성 하위 레이블을 사용합니다.

- Office 365 데이터 손실 방지로 인트라넷 데이터 누수 방지

  Contoso는 Exchange Online, SharePoint 및 비즈니스용 OneDrive에 대해 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 정책을 구성하여 사용자들이 실수로 또는 의도적으로 중요한 데이터를 공유하지 못하도록 하고 있습니다.

- Windows Information Protection로 장치 데이터 누수 방지

  Contoso는 [WIP(Windows Information Protection)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)를 사용하여 인터넷 기반 앱 및 서비스, 엔터프라이즈 소유의 장치 및 직원이 회사에 가져오는 개인 장치에 있는 엔터프라이즈 앱과 서비스를 통해 데이터가 누수되지 않도록 보호하고 있습니다.

- Microsoft Cloud App Security를 사용하는 클라우드 모니터링

  Contoso는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 사용하여 클라우드 환경을 매핑하고, 사용 현황을 모니터링하고, 보안 이벤트 및 인시던트를 감지하고 있습니다. Microsoft Cloud App Security는 Microsoft 365 E5에서만 사용할 수 있습니다.

- Microsoft Intune을 사용한 장치 관리

  Contoso는 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune)을 사용하여 모바일 장치 및 해당 장치에서 실행되는 앱을 등록, 관리 및 구성합니다. 또한 장치 기반 조건부 액세스 정책은 승인된 앱과 규격 PC 및 모바일 장치를 요구합니다.

## <a name="security-management"></a>보안 관리

- Azure Security Center의 IT 부서를 위한 중앙 보안 대시보드

  Contoso는 보안 및 위협 보호에 대한 통합 보기로 [Azure Security Center](https://azure.microsoft.com/services/security-center/)를 사용하여 워크로드 간에 보안 정책을 관리하고 사이버 공격에 대응합니다.

- Windows Defender 보안 센터의 사용자를 위한 중앙 보안 대시보드

  Contoso는 Windows 10 Enterprise가 실행되는 PC 및 장치에 [Windows 보안 앱](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)을 배포하여 사용자가 보안 태세를 한 눈에 확인하고 조치를 취할 수 있도록 하고 있습니다.


## <a name="next-step"></a>다음 단계

Contoso에서 연구팀 간에 공동 작업을 수행할 수 있도록 규제가 엄격한 데이터를 위해 SharePoint 사이트를 만든 방법을 [알아보세요](contoso-sharepoint-online-site-for-highly-confidential-assets.md).

