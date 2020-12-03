---
title: Contoso Corporation의 엔터프라이즈 보안용 Microsoft 365 요약
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso에서 기업에 대 한 Microsoft 365의 보안 기능을 사용 하는 방법
ms.openlocfilehash: 5c951a973fbebeff92040f9411ad2c81788f920a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558397"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation의 엔터프라이즈 보안용 Microsoft 365 요약

Microsoft 365 for enterprise를 배포할 수 있는 승인을 받기 위해 Contoso IT 보안 부서는 철저 한 보안 검토를 수행 했습니다. 클라우드에 대해 다음과 같은 보안 요구 사항을 확인 했습니다.

- 클라우드 리소스에 대 한 직원 액세스에 가장 강력한 인증 방법을 사용 합니다.
- Pc 및 모바일 장치가 안전한 방법으로 응용 프로그램에 연결 하 고 액세스 하는지 확인 합니다.
- Pc 및 맬웨어 로부터 전자 메일을 보호 합니다.
- 클라우드 기반 디지털 자산에 대 한 사용 권한은 사용자가 수행할 수 있는 작업과 작업에 액세스할 수 있는 사람을 정의 하며 최소 권한 액세스용으로 설계 되었습니다.
- 중요 및 높은 규제 대상 디지털 자산은 레이블이 지정 되 고 암호화 되며 안전한 위치에 저장 됩니다.
- 높은 규제 대상 디지털 자산은 추가 암호화 및 사용 권한으로 보호 됩니다.
- IT 보안 담당자는 중앙 대시보드에서 현재 보안 상태를 모니터링 하 고, 빠른 대응 및 완화를 위해 보안 이벤트에 대 한 알림을 받을 수 있습니다.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 보안 준비를 위한 Contoso 경로

Contoso는 다음 단계를 수행 하 여 기업에 대 한 Microsoft 365 배포에 대 한 보안을 준비 합니다.

1. 클라우드의 관리자 계정 제한

   Contoso는 기존 AD DS (Active Directory 도메인 서비스) 관리자 계정을 광범위 하 게 검토 하 고 전용 클라우드 관리자 계정 및 그룹을 설정 했습니다.

2. 데이터를 세 가지 보안 수준으로 분류

   Contoso는 신중 하 게 검토 하 고 가장 중요 한 데이터를 보호 하기 위해 Microsoft 365 for enterprise 기능을 식별 하는 데 사용 된 세 가지 수준을 확인 했습니다.

3. 데이터 수준에 대 한 액세스, 보존 및 정보 보호 정책 결정

   Contoso는 데이터 수준에 따라 클라우드로 이동 되는 미래의 IT 워크 로드를 정규화 하기 위한 자세한 요구 사항을 확인 했습니다.

기업 배포 요구 사항에 대 한 보안 모범 사례와 Microsoft 365을 따르기 위해 Contoso 보안 관리자 및 IT 부서가 다음 섹션에서 설명 하는 것 처럼 다양 한 보안 기능을 배포 했습니다.

## <a name="identity-and-access-management"></a>ID 및 액세스 관리 

- MFA 및 PIM이 있는 전용 전역 관리자 계정

  Contoso는 매일 사용자 계정에 전역 관리자 역할을 할당 하는 대신 강력한 암호를 사용 하 여 세 개의 전용 전역 관리자 계정을 만들었습니다. 계정이 Azure MFA (Multi-factor Authentication) 및 azure AD (특권 Id 관리)에 의해 보호 됩니다. *PIM은 Microsoft 365 E5에서만 사용할 수 있습니다.*

  전역 관리자 계정으로 로그인 하는 것은 특정 관리 작업에 대해서만 수행 됩니다. 암호는 지정 된 직원 에게만 알려진 것 이며 Azure AD PIM에서 구성 되는 기간 내 에서만 사용 될 수 있습니다.

  Contoso 보안 관리자는 해당 IT 직원의 작업 기능에 적합 한 계정에 대해 낮은 관리자 역할을 할당 받아야 합니다.

  자세한 내용은 [Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)를 참조하세요.

- 모든 사용자 계정에 대한 MFA

  MFA는 로그인 프로세스에 추가 보호 계층을 추가 합니다. 사용자가 암호를 올바르게 입력 한 후 전화 통화, 문자 메시지 또는 앱 알림을 스마트 전화에서 승인 해야 합니다. MFA를 사용 하는 경우 Azure AD 사용자 계정은 계정 암호가 노출 되더라도 무단 로그인 으로부터 보호 됩니다.

   - Contoso는 Microsoft 365 구독의 손상을 방지 하기 위해 모든 전역 관리자 계정에서 MFA를 요구 합니다.
   - Contoso는 공격자가 조직에서 신뢰할 수 있는 사용자의 자격 증명을 손상하고 악의적인 전자 메일을 보내는 피싱 공격으로부터 보호하기 위해 관리자 및 임원을 비롯한 모든 사용자 계정에서 MFA를 사용하도록 설정했습니다.

- 조건부 액세스 정책을 사용한 보다 안전한 장치 및 응용 프로그램 액세스

  Contoso는 ID, 장치, Exchange Online 및 SharePoint에 대해 [조건부 액세스 정책](../security/office-365-security/microsoft-365-policies-configurations.md)을 사용하고 있습니다. ID 조건부 액세스 정책에는 높은 위험에 처한 사용자에게 암호 변경 요구, 클라이언트가 최신 인증을 지원하지 않는 앱을 사용하지 못하도록 지정 등이 포함됩니다. 장치 정책에는 승인된 앱의 정의와 규격 PC 및 모바일 장치 요구가 포함됩니다. Exchange Online 조건부 액세스 정책에는 ActiveSync 클라이언트 차단 및 Office 365 메시지 암호화 설정이 포함됩니다. SharePoint 조건부 액세스 정책에는 중요 및 높은 규제 대상 사이트에 대한 추가적인 보호가 포함됩니다.

- 비즈니스용 Windows Hello

  Contoso는 [비즈니스용 Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 를 배포 했기 때문에 Windows 10 Enterprise를 실행 하는 pc 및 모바일 장치에서 강력한 2 단계 인증을 통해 암호를 사용할 필요가 없습니다.

- Windows Defender Credential Guard

  관리 권한을 사용 하 여 운영 체제에서 실행 되는 대상 지정 된 공격과 맬웨어를 차단 하기 위해 Contoso는 AD DS 그룹 정책을 통해 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) 를 사용 하도록 설정 합니다.

## <a name="threat-protection"></a>위협 방지

- Windows Defender 바이러스 백신으로 맬웨어로부터 보호

  Contoso는 Windows 10 Enterprise가 실행되는 PC 및 장치에 대해 맬웨어 보호 및 맬웨어 방지 관리를 제공하기 위해 [Windows Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)을 사용하고 있습니다.

- Office 용 Microsoft Defender 365의 보안 전자 메일 흐름 및 사서함 감사 로깅 

  Contoso는 Exchange Online Protection 및 [Defender For Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 를 사용 하 여 알 수 없는 맬웨어, 바이러스 및 전자 메일을 통해 전송 되는 악성 url 로부터 보호 합니다.

  또한 Contoso는 사서함 감사 로깅을 사용 하도록 설정 하 여 사용자 사서함에 로그인 하 고 메시지를 보내며 사서함 소유자, 위임 된 사용자 또는 관리자가 수행 하는 다른 작업을 식별 합니다.

- Office 365 위협 조사와 응답으로 공격 모니터링 및 방지

  Contoso는 공격을 쉽게 식별 하 고 해결할 수 있도록 하 고, 향후의 공격을 방지 하기 위해 [Office 365 위협 조사 및 응답](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) 을 사용 하 여 사용자를 보호 합니다.

- Advanced Threat Analytics를 사용하여 정교한 공격으로부터 보호

  Contoso는 [ATA(Advanced Threat Analytics)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata)를 사용하여 타기팅된 고급 공격으로부터 자체적으로 보호합니다. ATA는 정상 및 비정상 엔터티(사용자, 장치, 리소스) 동작을 자동으로 분석, 학습 및 식별합니다.

## <a name="information-protection"></a>정보 보호

- Azure Information Protection 레이블을 사용하여 중요 및 높은 규제 대상 디지털 자산 보호

  Contoso는 세 가지 수준의 데이터 보호를 확인 하 고 사용자가 디지털 자산에 적용 하는 [Microsoft 365 민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 배포 했습니다. Contoso는 해당 영업 비밀 및 기타 지적 재산권에 대해 민감도 리본의을 사용 하 여 높은 규제 대상 데이터를 사용할 것입니다. 이 프로세스에서는 콘텐츠를 암호화 하 고 특정 사용자 계정 및 그룹에 대 한 액세스를 제한 합니다.

- 데이터 손실 방지로 인트라넷 데이터 유출 방지하기

  Contoso는 Exchange Online, SharePoint 및 비즈니스용 OneDrive에 대해 [데이터 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) 정책을 구성 하 여 사용자가 실수로 또는 의도적으로 중요 한 데이터를 공유 하지 못하도록 차단 합니다.

- Windows Information Protection로 장치 데이터 누수 방지

  Contoso는 [MICROSOFT WIP (Windows Information Protection)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) 를 사용 하 여 인터넷 기반 앱, 서비스 및 엔터프라이즈 앱을 통해 데이터 누출을 보호 하 고 직원 들이 작동 하기 위해 사용 하는 개인 장치에 대 한 정보를 보호할 수 있습니다.

- Microsoft Cloud App Security를 사용하는 클라우드 모니터링

  Contoso는 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 사용하여 클라우드 환경을 매핑하고, 사용 현황을 모니터링하고, 보안 이벤트 및 인시던트를 감지하고 있습니다. *Microsoft Cloud App Security는 Microsoft 365 E5에서만 사용할 수 있습니다.*

- Microsoft Intune을 사용한 장치 관리

  Contoso는 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune)을 사용하여 모바일 장치 및 해당 장치에서 실행되는 앱을 등록, 관리 및 구성합니다. 또한 장치 기반 조건부 액세스 정책은 승인된 앱과 규격 PC 및 모바일 장치를 요구합니다.

## <a name="security-management"></a>보안 관리

- Azure Defender를 사용 하는 IT 용 중앙 보안 대시보드

  Contoso는 [Azure Defender](https://azure.microsoft.com/services/security-center/) 를 사용 하 여 보안 및 위협 보호에 대 한 통합 된 보기를 제공 하 고, 워크 로드에 대 한 보안 정책을 관리 하 고, 고 사이버 공격에 응답할 수 있습니다.

- Windows Defender 보안 센터의 사용자를 위한 중앙 보안 대시보드

  Contoso는 사용자가 자신의 보안 환경을 한눈에 확인 하 고 조치를 취할 수 있도록 Windows 10 Enterprise를 실행 하는 Pc 및 장치에 [Windows 보안 앱](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 을 배포 했습니다.
