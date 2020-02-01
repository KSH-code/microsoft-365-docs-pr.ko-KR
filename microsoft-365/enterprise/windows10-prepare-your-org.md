---
title: Windows 10 Enterprise에 대 한 조직 준비
description: Microsoft 365 Enterprise의 일부로 Pc에 Windows 10 Enterprise를 배포 하는 데 필요한 단계에 대 한 간략 한 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, Windows 10 Enterprise, 배포
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 69ff4846e3daeef39310aa63961e0b3f5ccb9875
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596595"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>1 단계: Windows 10 Enterprise에 대 한 조직 준비

*이 문서는 Microsoft 365 Enterprise E3 및 E5 버전에 모두 적용 됩니다.*

![3단계: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

장치를 Windows 10 Enterprise로 업그레이드 하기 전에 다음 사항을 고려 하세요.

- **도메인을 추가 및 확인 해야 함** <br>
  Microsoft 365 구독을 사용 하는 경우 onmicrosoft.com (예: contoso.onmicrosoft.com)에서 끝나는 기본 도메인 이름을 가져옵니다. 대부분의 조직에서는 자신이 소유한 도메인을 하나 이상 사용 하 여 자신의 전자 메일 주소가 자체 도메인 이름 (username@contoso.com)으로 끝나는 것을 선호 합니다. 자체 도메인을 사용 하려면 Microsoft 365에 추가 하 고 사용자가 소유 하 고 있는지 확인 해야 합니다. 전자 메일 및 비즈니스용 Skype와 같은 Microsoft 365 서비스를 설정할 때마다 해당 도메인을 사용할 수 있도록 지금 추가 하 고 확인 하는 것이 좋습니다.
- **지금은 사용자를 추가할 필요가 없습니다.** <br>
  Microsoft 365 서비스를 사용 하거나 Microsoft 365 제품을 설치 하려면 사용자에 게 Microsoft 365의 계정이 필요 하며 제품 라이선스가 필요 합니다. 사용자를 Microsoft 365에 추가 하는 방법은 사용자 수와 현재 온-프레미스 Active Directory가 있는지 여부에 따라 달라 집니다. Active Directory가 없거나 Active Directory를 Microsoft 365와 동기화 하지 않으려는 경우에는 Microsoft 365에 직접 사용자를 추가 하 고 개별적으로 또는 대량으로 라이선스를 할당할 수 있습니다. <br>
  온-프레미스에 Active Directory를 365 사용 하는 경우 microsoft [365](identity-add-user-accounts.md#identity-sync) 에서 사용한 클라우드 디렉터리인 Azure AD의 사용자 계정을 만들 수 있습니다. 이 방법을 사용 하면 리소스 (예를 들어 SharePoint Online 사이트 모음 또는 문서)에 대 한 사용 권한을 관리 하는 데 사용 되는 사용자 및 보안 그룹에 대 한 계정을 만들 수 있습니다. Active Directory와 Microsoft 365을 동기화 하면 사용자에 게 라이선스가 할당 되지 않습니다.
- **사용자에 게 사용 권한을 부여할 필요가 없습니다.** <br>
  사용자가 microsoft 365 서비스를 사용 하거나 Microsoft 365 포털에서 소프트웨어를 설치할 수 있으려면 먼저 제품 라이선스가 필요 합니다. 전역 또는 사용자 관리 관리자는 Microsoft 365에서 제품 라이선스를 개별적으로 또는 대량으로 직접 할당할 수 있습니다. 또한 사용자가 특정 그룹에 추가 될 때 [그룹 기반 라이선싱](identity-use-group-management.md#identity-group-license) 을 사용 하 여 라이선스를 자동으로 할당할 수 있습니다. 
- **Office 365 ProPlus를 별도로 설치 하는 경우** <br>
  Microsoft 365 라이선스를 취득 해도 클라이언트 컴퓨터에 Office 365 ProPlus가 자동으로 설치 되지 않습니다. 자세한 내용은 [4 단계: Office 365 ProPlus](office365proplus-infrastructure.md) 를 참조 하세요. 

## <a name="set-windows-diagnostics-data-level"></a>Windows 진단 데이터 수준 설정

Microsoft는 진단 데이터를 사용 하 여 맬웨어 추세 및 기타 위협을 식별 하 고 Windows 및 Microsoft 서비스 품질을 개선 하는 데 도움이 되도록 Windows 장치를 안전 하 게 유지 합니다. 조직의 모든 끝점에서 최소 기본 수준으로 진단 서비스가 사용 하도록 설정 되어 있는지 확인 해야 합니다. *기본적으로이 서비스는 사용 하도록 설정 되며 향상 된 수준으로 설정 됩니다.* 그러나 센서 데이터를 수신 하 고 있는지 확인 하는 것이 좋습니다. 정책을 통해 수준을 설정 하면 장치 수준 설정이 재정의 됩니다. 

**Windows 10 운영 체제 진단 데이터 수준**

이미 사용 중인 관리 도구 (예: 그룹 정책, MDM 또는 Windows 프로 비전)를 사용 하 여 운영 체제 진단 데이터 설정을 구성할 수 있습니다. 레지스트리 편집기를 사용 하 여 설정을 수동으로 변경할 수도 있습니다. 관리 정책을 통해 진단 데이터 수준을 설정 하면 모든 장치 수준 설정이 재정의 됩니다.

관리 정책을 구성할 때는 아래 표에 나와 있는 적절 한 값을 사용 합니다.

| 수준 | 수집 된 데이터 | 값 |
|:--- |:--- |:--- |
| 보안 | 보안 데이터만 | 개 |
| 기본 | 보안 데이터 및 기본 시스템 및 품질 데이터 | 개 |
| 방식 | 보안 데이터, 기본 시스템 및 품질 데이터, 향상 된 insights 및 고급 안정성 데이터 | 2 |
| Full | 보안 데이터, 기본 시스템 및 품질 데이터, 향상 된 insights 및 고급 안정성 데이터 및 전체 진단 데이터 | 3(sp3) |

다음 방법 중 하나를 통해 진단 데이터를 사용 하도록 설정할 수 있습니다.

* **Microsoft intune** -Intune을 사용 하 여 장치를 관리 하려는 경우 <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">systemallowtelemetry 분석</a> 시스템 정책을 구성 하 여 진단 데이터를 사용 하도록 구성 정책을 만들 수 있습니다. 구성 정책 설정에 대 한 자세한 내용은 [Microsoft Intune 정책을 사용 하 여 장치에서 설정 및 기능 관리](https://aka.ms/intuneconfigpolicies)를 참조 하세요.
* **레지스트리 편집기** -레지스트리 편집기를 사용 하 여 조직의 각 장치에서 진단 데이터를 수동으로 사용 하도록 설정할 수 있습니다. 또는 레지스트리를 편집 하기 위한 스크립트를 작성할 수 있습니다. 관리 정책이 이미 있는 경우 (예: 그룹 정책 또는 MDM)이 레지스트리 설정이 재정의 됩니다.
* **그룹 정책** -Intune에서 장치를 등록 하지 않을 경우 그룹 정책 개체를 사용 하 여 조직의 진단 데이터 수준을 설정할 수 있습니다.
* **명령 프롬프트** -명령 프롬프트를 사용 하 여 Windows 10 진단 데이터 및 서비스를 자동으로 시작 하도록 설정할 수 있습니다. 이 방법은 소수의 장치 에서만 서비스를 테스트 하는 경우에 가장 적합 합니다. 이 명령을 사용 하 여 서비스를 자동으로 시작 하도록 설정 하면 진단 데이터 수준이 구성 되지 않습니다. 관리 도구를 사용 하 여 진단 데이터 수준을 구성 하지 않은 경우 서비스는 기본 고급 수준으로 작동 합니다.

Windows 진단 데이터에 대 한 자세한 내용을 확인 하 고 선택한 방법에 따라이를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [조직에서 windows 진단 데이터 구성을](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) 참조 하세요.

중간 검사점으로 이 단계에 해당하는 [종료 조건](windows10-exit-criteria.md#crit-windows10-step1)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![2단계](./media/stepnumbers/Step2.png)| [현재 위치 업그레이드로 기존 장치에 대 한 Windows 10 Enterprise 배포](windows10-deploy-inplaceupgrade.md) |






