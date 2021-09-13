---
title: Microsoft 365 BDM(비즈니스 의사 결정자)에 대한 보안
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 조직이 현재 해당 Microsoft 365 가장 일반적인 위협 및 공격 시나리오와 이러한 위험을 완화하기 위한 권장 조치를 제공합니다.
ms.openlocfilehash: 8f5c6e75097814841f8478cd8240c80b4eebc51a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220684"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 BDM(비즈니스 의사 결정자)에 대한 보안

이 문서에서는 조직이 현재 해당 Microsoft 365 가장 일반적인 위협 및 공격 시나리오 중 일부를 설명하고 이러한 위험을 완화하기 위한 권장 조치에 대해 설명합니다. Microsoft 365 다양한 보안 기능이 함께 제공되면 고객도 클라우드 서비스에 액세스하는 데 사용되는 ID, 데이터 및 장치를 보호할 책임이 있습니다. 이 지침은 Kozeta 강선(Microsoft 클라우드 보안 설계자) 및 Thiagaraj Sundararajan(Microsoft 선임 컨설턴트)에서 개발했습니다.

이 문서는 테넌트, 전자 메일 및 자산과 같은 가장 중요한 서비스 및 자산을 관리하는 데 사용되는 계정 보호부터 시작하여 작업의 우선 순위에 따라 SharePoint. 조직 전체의 이해 관계자 및 팀과 진행 상황을 추적할 수 있도록 다음과 같은 스프레드시트와 함께 작업할 수 있는 조직 내 조직의 이해 관계자 및 팀과의 진행 상황을 추적할 [수](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)있도록 Microsoft 365 방법을 제공합니다. 

[![BDM Microsoft 365 권장 스프레드시트의 축소판 이미지입니다.](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft는 테넌트 내에서 보안 점수 도구를 사용하여 정기적인 활동에 따라 보안 자세를 자동으로 분석하고, 점수를 할당하고, 보안 개선 권장 사항을 제공합니다. 이 문서에서 권장하는 작업을 수행하기 전에 현재 점수와 권장 사항을 기록해 넣습니다. 이 문서에서 권장하는 작업을 수행하면 점수가 향상됩니다. 목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 방식으로 환경을 보호할 기회를 인식하는 것입니다. [Microsoft 보안 점수를 참조합니다.](defender/microsoft-secure-score.md)

![다음 단계에 따라 비즈니스에 대한 위험을 완화합니다.](../media/security/security-for-bdms-overview.png)

시작하기 전에 한 가지 더 많은 것이 있습니다. . . 감사 [로그를 켜야 합니다.](../compliance/search-the-audit-log-in-security-and-compliance.md) 나중에 인시던트 또는 위반을 조사해야 하는 경우 이 데이터가 필요합니다. 

## <a name="protect-privileged-accounts"></a>권한 있는 계정 보호

첫 번째 단계로, 이러한 계정에 중요한 서비스 및 리소스를 관리하고 변경할 수 있는 액세스 및 권한이 있으며, 손상된 경우 전체 조직에 부정적인 영향을 줄 수 있는 액세스 및 권한을 가지기 때문에 환경의 중요한 계정에 추가 보호 계층을 부여하는 것이 좋습니다. 권한 있는 계정을 보호하는 것은 손상된 계정의 사용 권한을 관리 계정으로 승격하는 공격자로부터 보호하는 가장 효과적인 방법 중 하나입니다. 

|권장 사항  |E3 |E5  |
|---------|---------|---------|
|모든 관리 계정에 대해 MFA(다단계 인증)를 적용합니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)| 
|PIM(Azure AD) Azure Active Directory(Privileged Identity Management)를 구현하여 Azure AD 및 Azure 리소스에 대한 just-in-time 권한 있는 액세스를 적용합니다. 액세스 권한이 있는 사용자를 검색하고 권한 있는 액세스를 검토할 수 있습니다.|         | ![녹색 확인 표시](../media/green-check-mark.png)|
|권한 있는 액세스 관리를 구현하여 권한 있는 관리 작업에 대한 세부적인 액세스 제어를 Office 365. |         | ![녹색 확인 표시](../media/green-check-mark.png)|
|PAW(Privileged Access Workstation)를 구성하고 사용하여 서비스를 관리합니다. 인터넷을 탐색하고 관리 계정과 관련이 없는 전자 메일을 확인하려면 동일한 workstation을 사용하지 않습니다.|  ![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png) | 

다음 다이어그램에는 이러한 기능이 설명되어 있습니다.
![권한 있는 계정을 보호하기 위한 권장 기능](../media/m365-security-bdm-illustrations-privileged-accounts.png)

추가 권장 사항:
- 사내에서 동기화된 계정에 클라우드 서비스에 대한 관리자 역할이 할당되지 않은지 확인 이렇게 하면 공격자가 클라우드 서비스에 대한 관리 액세스 권한을 얻기 위해 사내 계정을 적용하지 못하게 할 수 있습니다. 
- 서비스 계정에 관리자 역할이 할당되지 않은지 확인 이러한 계정은 종종 모니터링되지 않습니다. 만료되지 않는 암호로 설정됩니다. 기본적으로 AADConnect 및 ADFS 서비스 계정이 전역 관리자가 아닌지 먼저 하세요.
- 관리자 계정에서 라이선스를 제거합니다. 특정 관리자 계정에 라이선스를 할당하는 특정 사용 사례가 없는 경우 이러한 계정에서 라이선스를 제거합니다. 

## <a name="reduce-the-surface-of-attack"></a>공격 표면 감소

다음 포커스 영역은 공격 표면을 줄이는 것입니다. 사용자 및 서비스에 대한 최소한의 노력과 영향으로 이 작업을 수행할 수 있습니다. 공격자는 공격의 표면 영역을 줄이면 조직에 대한 공격을 시작하는 방법이 더 적습니다.

다음은 몇 가지 예입니다.
- POP3, IMAP 및 SMTP 프로토콜을 사용하지 않도록 설정 대부분의 최신 조직에서는 더 이상 이러한 이전 프로토콜을 사용하지 않습니다. 이러한 기능을 안전하게 사용하지 않도록 설정하고 필요한 경우 예외를 허용할 수 있습니다. 
- 테넌트의 전역 관리자 수를 줄이고 필요한 절대 최소값으로 유지하세요. 이렇게 하면 모든 클라우드 응용 프로그램에 대한 공격의 표면 영역을 직접 줄일 수 있습니다. 
- 해당 환경에서 더 이상 사용되지 않습니다. 
- 더 이상 사용되지 않습니다. 계정을 사용 안 하게 및 삭제하는 프로세스를 구현합니다. 

## <a name="protect-against-known-threats"></a>알려진 위협으로부터 보호

알려진 위협에는 맬웨어, 손상된 계정 및 피싱이 포함됩니다. 이러한 위협에 대한 일부 보호는 사용자에게 직접적인 영향을 끼치지 않습니다. 반면에 다른 보호 기능을 사용하려면 추가 계획 및 사용자 교육이 필요할 수 있습니다. 

|권장 사항  |E3  |E5  |
|---------|---------|---------|
|**로그인 위험 정책을** 포함하여 다단계 인증을 설정하고 권장되는 조건부 액세스 정책을 사용 Microsoft는 모든 클라우드 앱(서비스 및 클라우드 서비스 포함)을 보호하기 위해 함께 작동할 Office 365 Microsoft 365 테스트했습니다. ID [및 장치 액세스 구성을 참조하세요.](./office-365-security/microsoft-365-policies-configurations.md) | |![녹색 확인 표시](../media/green-check-mark.png)|
|**모든 사용자에 대해 다단계 인증을 요구합니다.** 권장되는 조건부 액세스 정책을 구현하는 데 라이선스가 필요하지 않은 경우 최소한 모든 사용자에 대해 다단계 인증이 필요합니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**메일의 맬웨어에 대한 보호 수준을 높입니다.** 사용자 Office 365 Microsoft 365 환경에는 맬웨어에 대한 보호가 포함되어 있지만 맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**대상 피싱 공격으로부터** 전자 메일을 보호합니다. Office 365 또는 Microsoft 365 사용자 지정 도메인을 하나 이상 구성한 경우 대상 피싱 방지 보호를 구성할 수 있습니다. Office 365 Defender의 일부인 피싱 방지 보호는 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.| |![녹색 확인 표시](../media/green-check-mark.png)|
|**전자 메일의 랜섬웨어 공격으로부터 보호합니다.** 랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 액세스하지 않습니다. 그런 다음 데이터에 대한 액세스를 반환하는 대가로 일반적으로 '금전'과 같은 암호화 형식의 금전을 요청하여 피해자로부터 돈을 유출하려고 시도합니다. 랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단하거나 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고하는 메일 흐름 규칙을 하나 이상 만들어 랜섬웨어를 방지할 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|를 사용하여 비즈니스하지 않는 **국가에서의 연결을 차단합니다.** Azure AD 조건부 액세스 정책을 만들어 이러한 국가에서 오는 연결을 차단하고 테넌트 주변에 지리적 방화벽을 효과적으로 만들 수 있습니다.| |![녹색 확인 표시](../media/green-check-mark.png)|

다음 다이어그램에는 이러한 기능이 설명되어 있습니다.
![알려진 위협으로부터 보호하기 위한 권장 기능](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>알 수 없는 위협으로부터 보호

권한 있는 계정에 추가 보호를 추가하고 알려진 공격으로부터 보호한 후 알 수 없는 위협으로부터 보호하기 위해 주의를 기울입니다. 더 결정적이고 고급 공격자는 혁신적이고 새로운 알 수 없는 방법을 사용하여 조직을 공격합니다. Microsoft는 수 10억 개가 넘는 장치, 응용 프로그램 및 서비스를 수집한 데이터를 방대한 원격 분석으로 Office 365, Windows Office 365 및 Azure에서 Defender를 수행하여 콘텐츠에 대한 액세스를 허용하기 전에 Zero-Day 공격, 샌드박스 환경 사용 및 유효성 검사에 대해 방지할 수 있습니다. 


|권장 사항  |E3  |E5  |
|---------|---------|---------|
|**다음을 위해 Microsoft Defender를 Office 365.**<br>* 금고 첨부 파일<br>* 금고 링크<br>* Microsoft Defender for Endpoint for SharePoint, OneDrive, and Microsoft Teams<br>* Defender의 피싱 방지 Office 365 보호|         |![녹색 확인 표시](../media/green-check-mark.png) |
|**끝점 기능용 Microsoft Defender 구성**:<br>* Windows Defender 바이러스 백신 <br>* Exploit Protection <br> * 공격 표면 감소 <br> * 하드웨어 기반의 고리 <br>* 제어된 폴더 액세스     |         |![녹색 확인 표시](../media/green-check-mark.png) |
|**이 Microsoft Cloud App Security** 사용하여 SaaS 앱을 검색하고 동작 분석 및 이상 검색 사용을 시작하세요. |         |![녹색 확인 표시](../media/green-check-mark.png) |

다음 다이어그램에는 이러한 기능이 설명되어 있습니다.
![알 수 없는 위협으로부터 보호하기 위한 권장 기능입니다.](../media/m365-security-bdm-illustrations-unknown-threats.png)

추가 권장 사항:
- TLS를 사용하는 전자 메일과 같은 파트너 채널 통신을 보호합니다.
- 통신하는 Teams 페더ation을 열기만 합니다.
- 스팸 및 맬웨어 검사를 무시할 수 있도록 허용 목록에 보낸 사람 도메인, 개별 보낸 사람 또는 원본 IPS를 추가하지 않습니다. 일반적인 방법은 허용 목록에 전자 메일 흐름 문제가 보고될 수 있는 자체 허용 도메인 또는 기타 여러 도메인을 추가하는 것입니다. 스팸 및 연결 필터링 목록에서 도메인을 추가하면 모든 스팸 검사가 무시될 수 있습니다. 
- 아웃바운드 스팸 알림 사용 - 지원팀 또는 IT 관리자 팀에 내부적으로 메일 그룹으로의 아웃바운드 스팸 알림을 사용하도록 설정하여 내부 사용자가 외부에서 스팸 전자 메일을 보내는 경우 보고합니다. 이는 계정이 손상된 표시기일 수 있습니다.
- 모든 사용자에 대해 원격 PowerShell을 사용하지 않도록 설정 - 원격 PowerShell은 관리자가 관리 목적으로 또는 프로그래밍 API 액세스를 위해 서비스에 액세스하는 데 주로 사용됩니다. 관리자가 아닌 사용자가 정경에 액세스해야 하는 업무상 요구 사항이 있는 경우를 위해 이 옵션을 사용 하지 않도록 설정하는 것이 좋습니다. 
- 관리자가 아닌 모든 Microsoft Azure 관리 포털에 대한 액세스를 차단합니다. 관리자를 제외한 모든 사용자를 차단하는 조건부 액세스 규칙을 만들어 이 작업을 수행할 수 있습니다. 


## <a name="assume-breach"></a>위반 가정

Microsoft는 위협과 공격을 방지하기 위해 가능한 모든 조치에 나서지만 항상 "위반 가정" 생각 아래 작업하는 것이 좋습니다. 공격자가 환경으로 침입하는 경우에도 해당 환경에서 데이터 또는 ID 정보를 유출할 수 없는지 확인해야 합니다. 이러한 이유로 사회 보장 번호, 신용 카드 번호, 추가 개인 정보 및 기타 조직 수준의 기밀 정보와 같은 중요한 데이터 누출에 대한 보호를 설정하는 것이 좋습니다. 

"위반 가정" 생각에는 사용자가 네트워크 내부에 있기 때문에 완전히 신뢰할 수 없는 제로 트러스트 네트워크 전략을 구현해야 합니다. 대신 사용자가 할 수 있는 권한 부여의 일부로 조건 집합이 지정됩니다. 이러한 조건이 충족되는 경우 특정 컨트롤이 적용됩니다. 조건에는 장치 상태, 액세스되는 응용 프로그램, 수행되는 작업 및 사용자 위험이 포함됩니다. 예를 들어 장치 등록 작업은 항상 MFA 인증을 트리거하여 라우팅 장치가 환경에 추가되지 않도록 해야 합니다. 

또한 신뢰 네트워크 전략을 사용하려면 정보가 저장되는 위치를 알고 분류, 보호 및 보존에 적절한 컨트롤을 적용해야 합니다. 가장 중요하고 중요한 자산을 효과적으로 보호하려면 먼저 이러한 자산의 위치를 식별하고 인벤토리를 파악해야 합니다. 이 경우 까다로워질 수 있습니다. 다음으로, 조직과 함께 거버넌스 전략을 정의합니다. 조직에 대한 분류표를 정의하고 정책, 레이블 및 조건을 구성하려면 신중한 계획과 준비가 필요합니다. 이 프로세스는 IT 기반 프로세스가 아니라는 점에 유의해야 합니다. 법률 및 규정 준수 팀과 협의하여 조직의 데이터에 적합한 분류 및 레이블 지정스마를 개발해야 합니다.

Microsoft 365 보호 기능을 사용하면 저장되는 정보, 추가 보호가 필요한 정보를 검색하는 데 도움이 될 수 있습니다. 정보 보호는 지속적인 프로세스로 Microsoft 365 기능으로, 사용자가 중요한 정보를 사용하고 배포하는 방법, 정보가 현재 저장되는 위치 및 정보가 흐르는 위치에 대한 가시성을 제공합니다. 또한 사용자가 적절한 레이블 및 보호가 적용될 수 있도록 규제된 정보를 처리하는 방법을 볼 수 있습니다.


|권장 사항 |E3|E5 |
|---------|---------|---------|
|조건부 액세스 및 관련 정책을 검토하고 최적화하여 제로 트러스트 네트워크에 대한 목표에 **맞게 조정합니다.** 알려진 위협으로부터 보호하는 데는 권장 정책 집합 [구현이 포함됩니다.](./office-365-security/microsoft-365-policies-configurations.md) 이러한 정책의 구현을 검토하여 네트워크에 대한 액세스 권한을 얻은 해커로부터 앱과 데이터를 보호할 수 있도록 합니다. WIP(정보 보호)에 대한 권장 intune Windows 10 사용하여 Windows 수 있습니다. WIP는 전자 메일, 소셜 미디어 및 공용 클라우드와 같은 앱 및 서비스를 통해 실수로 조직 데이터가 누출되지 않도록 보호합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**외부 전자 메일 전달을 사용하지 않도록 설정** 사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다. 이는 사용자의 인식 없이도 발생될 수 있습니다. 메일 흐름 규칙을 구성하여 이러한 문제를 방지할 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png) |![녹색 확인 표시](../media/green-check-mark.png)|
|**익명 외부 일정 공유를 사용하지 않도록 설정** 기본적으로 외부 익명 일정 공유는 허용됩니다. [일정 공유를 사용하지](/exchange/sharing/sharing-policies/modify-a-sharing-policy) 않도록 설정하여 중요한 정보의 잠재적 누출을 줄입니다.|![녹색 확인 표시](../media/green-check-mark.png) |![녹색 확인 표시](../media/green-check-mark.png)|
|**중요한 데이터에 대한 데이터 손실 방지 정책을 구성합니다.** 보안 및 준수 센터에서 데이터 손실 방지 정책을 만들어 신용 카드 번호, 주민등증 번호 및 은행 계좌 번호와 같은 중요한 데이터를 검색하고 &amp; 보호합니다. Microsoft 365 데이터 손실 방지 정책에 사용할 수 있는 많은 미리 정의한 중요한 정보 유형이 포함되어 있습니다. 사용자 환경에 사용자 지정되는 중요한 데이터에 대한 중요한 정보 유형을 직접 만들 수도 있습니다. |![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**데이터 분류 및 정보 보호 정책을 구현합니다.** 민감도 레이블을 구현하고 이러한 레이블을 사용하여 중요한 데이터를 분류하고 보호를 적용합니다. 데이터 손실 방지 정책에서 이러한 레이블을 사용할 수 있습니다. Azure Information Protection 레이블을 사용하는 경우 다른 관리 센터에서 새 레이블을 만들지 않는 것이 좋습니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|
|**를 사용하여** 타사 앱 및 서비스의 데이터를 Cloud App Security. Salesforce Cloud App Security Box 또는 앱과 같은 타사 클라우드 앱의 중요한 정보를 보호하기 위한 정책 Dropbox. 정책에서 만든 중요한 정보 유형 및 민감도 레이블을 Cloud App Security SaaS 앱에 적용할 수 있습니다. <br><br>Microsoft Cloud App Security 자동화된 프로세스를 적용할 수 있습니다. 지속적인 준수 검사, 법적 eDiscovery 작업, 공개적으로 공유되는 중요한 콘텐츠에 대한 DLP를 제공하기 위해 정책을 설정할 수 있습니다. Cloud App Security 20개 이상의 메타데이터 필터(예: 액세스 수준, 파일 형식)를 기반으로 모든 파일 형식을 모니터링할 수 있습니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**[끝점용 Microsoft Defender를](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview)** 사용하여 사용자가 해당 장치에서 중요한 정보를 Windows 식별합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**[AIP 스캐너를](/azure/information-protection/deploy-aip-scanner) 사용하여 서버** 및 파일 공유에서 정보를 식별하고 분류합니다. AIP 보고 도구를 사용하여 결과를 보고 적절한 작업을 수행할 수 있습니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|

다음 다이어그램에는 이러한 기능이 설명되어 있습니다.
![위반으로부터 보호하기 위한 권장 기능입니다.](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>지속적인 모니터링 및 감사

마지막으로, Microsoft 365 및 장치와 함께 Microsoft 365 환경에 대한 지속적인 모니터링 및 감사는 Windows 침입을 빠르게 감지하고 재구성할 수 있도록 하는 데 중요합니다. 보안 점수, 보안 센터 및 Microsoft Intelligent Graph 고급 분석과 같은 도구는 테넌트에 막대한 정보를 제공하고 대량의 위협 인텔리전스 및 보안 데이터를 연결하여 타의 다른 위협 방지 및 감지 기능을 제공합니다.


|권장 사항 |E3 |E5 |
|---------|---------|---------|
|감사 **로그가 켜져** 있는지 확인|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**매주 보안 점수 검토** - 보안 점수는 회사의 보안 상태에 액세스하고 보안 점수 권장 사항에 따라 작업을 수행할 수 있는 중앙 위치입니다. 매주 이 검사를 수행하는 것이 좋습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|다음 **도구에 Microsoft Defender를 Office 365** 사용합니다.<br>* 위협 조사 및 대응 기능<br> * 자동화된 조사 및 대응 |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**끝점에 Microsoft Defender 사용:**<br> *    [끝점 검색 및 응답](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * 자동화된 조사 및 수정 보안 점수 <br>*    [고급 헌팅](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![녹색 확인 표시](../media/green-check-mark.png)|
|클라우드  Microsoft Cloud App Security 이상한 동작을 감지하여 랜섬웨어, 손상된 사용자 또는 악성 응용 프로그램을 식별하고, 고위험 사용을 분석하고, 자동으로 수정하여 조직에 대한 위험을 제한합니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|
|**Sentinel** Microsoft Azure 현재 SIEM 도구를 사용하여 환경 전체에서 위협을 모니터링합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**ID에 [대한 Microsoft Defender를](/azure-advanced-threat-protection/what-is-atp)** 배포하여 프레미스 Active Directory 환경을 대상으로 하는 위협을 모니터링하고 보호합니다.   |         |![녹색 확인 표시](../media/green-check-mark.png) |
|Azure **Defender_를** 사용하여 하이브리드 및 클라우드 워크로드에서 위협을 모니터링합니다. Azure Defender_ 리소스 시간 또는 트랜잭션에 따라 지급되는 기능의 무료 계층과 표준 기능 계층이 포함되어 있습니다.|         |         |

다음 다이어그램에는 이러한 기능이 설명되어 있습니다.
![지속적인 모니터링 및 감사를 위한 권장 기능](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

권장되는 상위 모니터링 작업:
- **매주 Microsoft 보안** 점수 검토 - 보안 점수는 테넌트의 보안 상태에 액세스하고 주요 권장 사항에 따라 작업을 수행할 수 있는 중앙 위치입니다. 매주 이 검사를 수행하는 것이 좋습니다. 보안 점수에는 Azure AD, Intune, Cloud App Security 및 끝점용 Microsoft Defender의 권장 사항뿐만 아니라 Office 365. 
- **위험한 로그인을 매주** 검토 - Azure AD 관리 센터를 사용하여 매주 위험한 로그인을 검토합니다. 권장되는 ID 및 장치 액세스 규칙에는 위험한 로그인 시 암호 변경을 적용하는 정책이 포함되어 있습니다.  
- **매주** 상위 맬웨어 및 피싱 사용자 검토 - Office 365 위협 탐색기용 Microsoft Defender를 사용하여 맬웨어 및 피싱으로 대상이 지정되는 상위 사용자를 검토하고 이러한 사용자가 영향을 받는 근본 원인을 찾을 수 있습니다.