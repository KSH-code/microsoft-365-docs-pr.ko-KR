---
title: Windows 10 Enterprise에 대 한 조직 준비
description: Microsoft 365 Enterprise의 일부로 Pc에서 Windows 10 엔터프라이즈 배포에 필요한 단계에 대 한 고급 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise Microsoft 365 설명서, Windows 10 엔터프라이즈 배포
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870253"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>1 단계: Windows 10 Enterprise에 대 한 조직 준비

*Microsoft 365 Enterprise의 E3와 e 5 버전에 적용 하는이 문서*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 엔터프라이즈에 장치를 업그레이드 하기 전에 다음 사항을 고려 합니다.

- **도메인을 추가 및 확인 해야 합니다.** <br>Microsoft 365 구독을 사용 하는 기본 도메인 이름이 onmicrosoft.com (예: contoso.onmicrosoft.com 형식)에서 끝나는 얻을 수 있습니다. 대부분의 조직에서는 기본 자신의 도메인 이름 (예: username@contoso.com)의 전자 메일 주소를 종료 하도록 자신이 소유한 도메인 중 하나 이상을 사용 하 여 사용 합니다. 사용자의 도메인을 사용 하려면 Microsoft 365에 추가 하 고가지고 있는지 확인 해야 합니다. 추가 하 고 전자 메일 및 비즈니스를 위한 Skype 등과 같은 Microsoft 365 서비스를 설정 하는 때마다 이동 준비가 있도록 이제 도메인을 확인 하는 것이 좋습니다.
- **현재 사용자를 추가 하지 않아도 됩니다.** <br>을 Microsoft 365 서비스를 사용 하거나 Microsoft 365 제품을 설치 하려면 사용자에 게 Microsoft 365에서 계정이 필요 하 고 제품 라이선스를 필요 합니다. Microsoft 365에 추가할 사용자의 사용자 수 및 현재 Active Directory 온-프레미스가 있는지 여부에 따라 달라 집니다. Active Directory 없는 (또는 Active Directory를 되었지만 Microsoft 365로 동기화 하지 않으려고) 하는 경우에 Microsoft 365에 직접 사용자를 추가할 수 있으며 개별적으로 또는 대량에서 라이선스를 할당할 수 있습니다.<br>Active Directory 온-프레미스를 설치한 경우에 Azure AD를 사용 하 여 Microsoft 365 클라우드 디렉터리에서 사용자 계정을 만들려면 [Microsoft 365와 동기화](identity-azure-ad-connect-health.md) 할 수 있습니다. 이 메서드와 함께 계정과 사용자에 대 한 보안 그룹에 대 한 리소스 (예: SharePoint Online 사이트 모음 또는 문서)에 대 한 사용 권한 관리를 사용 하 여 만들 수 있습니다. Microsoft 365와 Active Directory 동기화 (영문) 사용자에 게 라이선스 할당 되지 않습니다.
- **현재 사용자에 게 라이선스를 하지 않아도** <br>사용자 수 Microsoft 365 서비스를 사용 하거나 Microsoft 365 포털에서 소프트웨어를 설치 하기 전에 제품 라이선스 필요한 합니다. 전역 또는 사용자 관리 관리자도 개별적으로 또는 대량에서 Microsoft 365에서 제품 라이선스를 직접 할당할 수 있습니다. 사용자가 특정 그룹에 추가 될 때 라이선스를 자동으로 할당 하려면 [라이선스 그룹 기반](identity-group-based-licensing.md) 을 사용할 수도 있습니다. 
- **개별적으로 Office 365 ProPlus 설치** <br>Microsoft 365 라이선스를 획득 설치 하지는 않습니다 자동으로 Office 365 ProPlus 클라이언트 컴퓨터에 있습니다. 참조 [4 단계: Office 365 ProPlus](office365proplus-infrastructure.md) 에 대 한 자세한 내용은 합니다. 

## <a name="set-windows-diagnostics-data-level"></a>Windows 진단 데이터 수준 설정

Microsoft 진단 데이터를 사용 하 여 Windows 장치 맬웨어 추세 및 기타 위협 요소를 식별 하 여 보안을 유지 하기 위해 Windows 및 Microsoft 서비스의 품질을 개선 하는 데 도움이을 합니다. 진단 서비스의 기본 조직에서 모든 끝점에 대 한 최소 수준에서 사용 하도록 설정 되었는지 확인 해야 합니다. *기본적으로이 서비스를 사용 하도록 설정 하 고 향상 된 수준으로 설정 합니다.* 그러나 것이 좋습니다 확인 하 고 센서 데이터를 받고는 있는지 확인 합니다. 정책을 통해 수준을 설정 장치 수준 설정 보다 우선 합니다. 

**Windows 10 운영 체제 진단 데이터 수준**

예: 그룹 정책, MDM, 또는 Windows 프로 비전 이미 사용 중인 관리 도구를 사용 하 여 운영 체제 진단 데이터 설정을 구성할 수 있습니다. 또한 수동으로 레지스트리 편집기를 사용 하 여 설정을 변경할 수 있습니다. 현재 진단 데이터 수준 정보 관리 정책을 통해 설정 된 장치 수준 설정 보다 우선 합니다.

관리 정책을 구성 하는 경우 아래 표에 적절 한 값을 사용 합니다.

| 수준 | 수집 되는 데이터 | 값 |
|:--- |:--- |:--- |
| 보안 | 보안 데이터에만 해당 합니다. | 0 |
| 기본 | 보안 데이터 및 기본 시스템 및 품질 데이터를 제공 합니다. | 1  |
| 향상 된 | 보안 데이터, 기본 시스템 및 품질 데이터 및 향상 된 정보 및 고급 안정성 데이터입니다. | 2  |
| Full | 보안 데이터, 기본 시스템 품질 데이터, 향상 된 정보 및 고급 안정성 데이터, 데이터 및 전체 진단 데이터입니다. | 3  |

이러한 방법 중 하나를 통해 진단 데이터를 설정할 수 있습니다.

* **Microsoft Intune** -Intune 장치 관리를 사용 하 여 계획 하는 경우, <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> 시스템 정책을 구성 하 여 진단 데이터를 사용 하도록 설정 하는 구성 정책을 만들 수 있습니다. 구성 정책 설정에 자세한 정보 [설정 관리 및 Microsoft Intune 정책 사용 하 여 장치에서 기능을](https://aka.ms/intuneconfigpolicies)참조 하십시오.
* **레지스트리 편집기** -레지스트리 편집기를 사용 하 여 수동으로 조직에서 각 장치에 진단 데이터를 사용 하도록 설정 합니다. 또는 레지스트리를 편집 하는 스크립트를 작성할 수 있습니다. 예: 그룹 정책 또는 MDM, 관리 정책에서 이미 존재 하는 경우이 레지스트리 설정을 재정의 합니다.
* **그룹 정책** -Intune에서 장치를 등록 하지 않으려는 경우, 조직의 진단 데이터 수준을 설정 하려면 그룹 정책 개체를 사용할 수 있습니다.
* **명령 프롬프트** -Windows 10 진단 데이터 및 서비스를 자동으로 명령 프롬프트에서 시작 하도록 설정할 수 있습니다. 이 방법은 몇 장치만에서 서비스를 테스트 하는 경우 가장 적합 합니다. 이 명령을 사용 하 여 자동으로 시작 되도록 서비스를 사용 하도록 설정에서 진단 데이터 수준을 구성 하지 않습니다. 관리 도구를 사용 하 여 진단 데이터 수준 구성 하지 않은 경우에 향상 된 수준으로는 기본으로 서비스 작동 합니다.

대 한 자세한 내용은 Windows 진단 데이터 및 활성화 하는 방법을 선택 하는 방법에 따라 [조직에서 Windows 구성 진단 데이터](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) 참조 하십시오.

중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step1)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [전체 업그레이드로 기존 장치에 대 한 Windows 10 엔터프라이즈 배포](windows10-deploy-inplaceupgrade.md) |






