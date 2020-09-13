---
title: BDMs (비즈니스 의사 결정권자 용 Microsoft 365 Security)
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
description: 현재 조직이 Microsoft 365 환경에 직면 하 게 되는 가장 일반적인 위협과 공격 시나리오로, 이러한 위험을 완화 하기 위한 권장 작업을 소개 합니다.
ms.openlocfilehash: 2f7de328edbd0220e5627612430fca24641ace11
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47548001"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>BDMs (비즈니스 의사 결정권자 용 Microsoft 365 Security)

이 문서에서는 Microsoft 365 환경에 대해 조직이 현재 직면 한 가장 일반적인 위협 및 공격 시나리오와 이러한 위험을 완화 하기 위한 권장 작업에 대해 설명 합니다. Microsoft 365에는 미리 구성 된 다양 한 보안 기능과 함께 제공 되지만, 고객은 클라우드 서비스에 액세스 하는 데 사용 되는 고유한 id, 데이터 및 장치를 보호 해야 합니다. 이 지침은 Kozeta 빔 (Microsoft Cloud Security 설계자) 및 Thiagaraj Sundararajan (Microsoft 선임 컨설턴트)가 개발 했습니다.

이 문서는 테 넌 트, 전자 메일 및 SharePoint와 같은 가장 중요 한 서비스 및 자산을 관리 하는 데 사용 되는 계정을 보호 하기 시작 하 여 우선 순위에 따라 구성 됩니다. 이 기능은 보안에 대 한 체계적인 방법을 제공 하며, 조직 전체에서 관련자 및 팀의 진행 상황을 추적할 수 있도록 다음 스프레드시트와 함께 작동 합니다. [BDMs 스프레드시트에 대 한 Microsoft 365 security](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![엄지 단추 이미지 Microsoft 365 BDM 보안 권장 사항 스프레드시트](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft는 테 넌 트 내에서 보안 점수 도구를 제공 하 여 정기적인 활동에 따라 보안 환경을 자동으로 분석 하 고, 점수를 할당 하 고, 보안 강화 권장 사항을 제공 합니다. 이 문서에서 권장 하는 작업을 수행 하기 전에 현재 점수 및 권장 사항을 기록해 둡니다. 이 문서에서 권장 하는 작업을 통해 점수가 증가 합니다. 목표는 최대 점수를 얻는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 방식으로 환경을 보호 하기 위한 기회를 확보 하기 위한 것입니다. [Microsoft 보안 점수](mtp/microsoft-secure-score.md)를 참조 하세요.

시작 하기 전에 한 가지 더 많은 일이 있습니다. . . [감사 로그를 설정](../compliance/search-the-audit-log-in-security-and-compliance.md)해야 합니다. 이 데이터는 나중에 문제 또는 위반을 조사 해야 하는 경우에 필요 합니다. 

## <a name="protect-privileged-accounts"></a>권한 있는 계정 보호

첫 번째 단계에서는 이러한 계정에는 전체 조직에 부정적인 영향을 줄 수 있는 중요 한 서비스와 리소스를 관리 하 고 변경 하기 위한 액세스 및 권한이 있다는 것을 고려 하 여 환경의 중요 한 계정에 추가 보호 기능을 제공 하는 것이 좋습니다. 권한 있는 계정 보호는 손상 된 계정의 사용 권한을 관리 1로 승격 하려는 공격자 로부터 보호 하는 가장 효과적인 방법 중 하나입니다. 

|권장 사항  |E3 |E5  |
|---------|---------|---------|
|모든 관리 계정에 대해 MFA (multi-factor authentication)를 적용 합니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)| 
|Azure AD 및 Azure 리소스에 대 한 특권 수준의 권한 있는 액세스를 적용 하는 PIM (관리 권한 Id 관리)을 구현 합니다. 또한 액세스 권한을 가진 사용자 및 권한 있는 액세스를 검토 하는 사람을 검색할 수도 있습니다.|         | ![녹색 확인 표시](../media/green-check-mark.png)|
|권한 있는 액세스 관리를 구현 하 여 Office 365에서 권한이 부여 된 관리 작업에 대 한 세부적인 액세스 제어를 관리 합니다. |         | ![녹색 확인 표시](../media/green-check-mark.png)|
|권한 있는 액세스 워크스테이션 (발 없는)을 구성 하 고 사용 하 여 서비스를 관리 합니다. 동일한 워크스테이션을 사용 하 여 인터넷을 찾아보고 관리 계정과 관련 되지 않은 전자 메일을 확인 하지 마십시오.|  ![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png) | 

다음 다이어그램에서는 이러한 기능을 보여 줍니다.
![권한 있는 계정 보호에 대 한 권장 기능](../media/m365-security-bdm-illustrations-privileged-accounts.png)

추가 권장 사항:
- 온-프레미스에서 동기화 된 계정에 클라우드 서비스에 대 한 관리자 역할이 할당 되어 있지 않은지 확인 합니다. 이를 통해 공격자가 클라우드 서비스에 대 한 관리 액세스 권한을 얻은 후 온-프레미스 계정을 활용할 수 없습니다. 
- 서비스 계정에 관리자 역할이 할당 되지 않았는지 확인 합니다. 이러한 계정은 대개 만료 되지 않는 암호를 사용 하 여 모니터링 및 설정 되지 않습니다. 기본적으로 AADConnect 및 ADFS 서비스 계정이 전역 관리자가 되지 않도록 합니다.
- 관리자 계정에서 라이선스를 제거 합니다. 특정 사용 사례가 특정 관리자 계정에 라이선스를 할당 하는 경우를 제외 하 고 이러한 계정에서 라이선스를 제거 합니다. 

## <a name="reduce-the-surface-of-attack"></a>공격 허점 줄이기

다음 포커스 영역이 공격 표면을 줄입니다. 이 작업은 사용자 및 서비스에 최소한의 노력과 영향을 줄 수 있습니다. 공격에 대 한 노출 영역을 줄임으로써 공격자는 조직에 대해 공격을 시작 하는 방법을 보다 적게 제공 합니다.

그 예는 다음과 같습니다.
- POP3, IMAP 및 SMTP 프로토콜을 사용 하지 않도록 설정 합니다. 대부분의 최신 조직은 더 이상 이러한 오래 된 프로토콜을 사용 하지 않습니다. 이 기능을 사용 하지 않도록 설정 하 고 필요한 경우에만 예외를 허용할 수 있습니다. 
- 테 넌 트의 전역 관리자 수를 최소 필수로 줄이고 유지 합니다. 이렇게 하면 모든 클라우드 응용 프로그램에 대 한 공격 노출 영역이 직접적으로 줄어듭니다. 
- 사용자 환경에서 더 이상 사용 되지 않는 서버 및 응용 프로그램을 폐기 합니다. 
- 더 이상 사용 되지 않는 계정을 사용 하지 않도록 설정 하 고 삭제 하는 프로세스를 구현 합니다. 

## <a name="protect-against-known-threats"></a>알려진 위협 으로부터 보호

알려진 위협에는 맬웨어, 손상 된 계정 및 피싱이 포함 됩니다. 이러한 위협에 대 한 일부 보호는 사용자에 게 직접적인 영향을 주지 않고 신속 하 게 구현 하 고, 다른 사용자에 게는 계획 및 사용자 교육이 더 많이 필요 합니다. 

|권장 사항  |E3  |E5  |
|---------|---------|---------|
|**다단계 인증을 설정 하 고 로그인 위험 정책을 포함 하 여 권장 되는 조건부 액세스 정책을 사용**합니다. Microsoft는 Office 365 및 Microsoft 365 서비스를 비롯 한 모든 클라우드 앱을 보호 하기 위해 함께 작동 하는 일련의 정책 들을 테스트 하는 것이 좋습니다. [Id 및 장치 액세스 구성를](../enterprise/microsoft-365-policies-configurations.md)참조 하세요. | |![녹색 확인 표시](../media/green-check-mark.png)|
|**모든 사용자에 대해 다단계 인증이 필요**합니다. 권장 조건부 액세스 정책을 구현 하는 데 필요한 라이선스가 없는 경우 최소한 모든 사용자에 대해 multi-factor authentication을 사용 해야 합니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**메일에서 맬웨어에 대 한 보호 수준을 높입니다**. Office 365 또는 Microsoft 365 환경에는 맬웨어에 대 한 보호 기능이 포함 되어 있지만 일반적으로 맬웨어에 사용 되는 파일 형식을 사용 하 여 첨부 파일이 차단 되므로이 보호 기능을 높일 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**대상 피싱 공격 으로부터 전자 메일을 보호**합니다. Office 365 또는 Microsoft 365 환경용으로 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호 기능을 구성할 수 있습니다. ATP 피싱 방지 보호, Office 365 Advanced Threat Protection의 일부분은 악의적인 가장 기반 피싱 공격과 기타 피싱 공격 으로부터 조직을 보호 하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성 하지 않은 경우에는이 작업을 수행 하지 않아도 됩니다.| |![녹색 확인 표시](../media/green-check-mark.png)|
|**전자 메일에서 랜 섬 웨어 공격 으로부터 보호**합니다. 랜 섬 웨어는 파일 암호화 또는 컴퓨터 화면 잠금으로 데이터에 대 한 액세스를 사용 합니다. 그런 다음 사용자가 데이터에 대 한 액세스를 반환 하기 위해 exchange에서 Bitcoin과 같은 "ransom"를 사용 하 여 victims에서 ort money를 연결 하려고 시도 합니다. 메일 흐름 규칙을 하나 이상 만들어, 랜 섬 웨어에 일반적으로 사용 되는 파일 확장명을 차단 하거나, 전자 메일로 이러한 첨부 파일을 받는 사용자에 게 경고할 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**비즈니스를 수행 하지 않는 국가의 연결을 차단**합니다. 다음 국가에서 들어오는 연결을 차단 하 여 테 넌 트 주변에 지리적 방화벽을 효과적으로 만드는 Azure AD 조건부 액세스 정책을 만듭니다.| |![녹색 확인 표시](../media/green-check-mark.png)|

다음 다이어그램에서는 이러한 기능을 보여 줍니다.
![알려진 위협 으로부터 보호 하는 데 권장 되는 기능](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>알 수 없는 위협 으로부터 보호

권한 있는 계정에 추가 보호를 추가 하 고 알려진 공격 으로부터 보호 한 후에는 알 수 없는 위협 으로부터 보호 하기 위해 주의를 기울여야 합니다. 더 결정 되 고 고급 악의적 사용자는 조직 공격에 알 수 없는 혁신적이 고 새로운 방법을 사용 합니다. 10억 개의 장치, 응용 프로그램 및 서비스를 통해 수집 된 데이터에 대 한 Microsoft의 방대한 원격 분석을 통해 Windows, Office 365 및 Azure에서 Advanced Threat Protection을 수행 하 여 당일 공격을 방지 하 고, 샌드 박스 환경을 활용 하 고, 콘텐츠에 대 한 액세스를 허용 하기 전에 유효성을 검사 하도록 할 수 있습니다. 


|권장 사항  |E3  |E5  |
|---------|---------|---------|
|**Office 365 ATP (Advanced Threat Protection) 구성**:<br>* ATP 안전한 첨부 파일<br>* ATP 안전한 링크<br>* SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP<br>* ATP 피싱 방지 보호 기능|         |![녹색 확인 표시](../media/green-check-mark.png) |
|**Microsoft Defender Advanced Threat Protection 기능을 구성**합니다.<br>* Windows Defender 바이러스 백신 <br>* Exploit protection <br> * 공격 표면 줄이기 <br> * 하드웨어 기반 격리 <br>* 제어 되는 폴더 액세스     |         |![녹색 확인 표시](../media/green-check-mark.png) |
|**Microsoft Cloud App Security를 사용** 하 여 SaaS 앱을 검색 하 고 동작 분석 및 변칙 검색을 사용 하기 시작 합니다. |         |![녹색 확인 표시](../media/green-check-mark.png) |

다음 다이어그램에서는 이러한 기능을 보여 줍니다.
![알 수 없는 위협 으로부터 보호 하는 데 권장 되는 기능](../media/m365-security-bdm-illustrations-unknown-threats.png)

추가 권장 사항:
- TLS를 사용 하는 전자 메일과 같은 보안 파트너 채널 통신
- 팀 페더레이션은 통신 하는 파트너 에게만 열려 있습니다.
- 보낸 사람 도메인, 개별 보낸 사람 또는 원본 Ip를 허용 목록에 추가 하지 않음이는 스팸 및 맬웨어 검사를 우회 하는 것을 허용 하 고, 고객은 자신의 허용 도메인을 추가 하는 일반적인 방법이 나 전자 메일 흐름 문제가 허용 목록에 보고 되었을 수 있는 기타 여러 도메인을 추가할 수 있습니다. 스팸 및 연결 필터링 목록에 도메인을 추가 하지 않으므로 모든 스팸 검사가 무시 될 수 있습니다. 
- 아웃 바운드 스팸 알림 사용-지원 센터 또는 IT 관리 팀에 내부적으로 메일 그룹에 대 한 아웃 바운드 스팸 알림을 사용 하도록 설정 하 여 내부 사용자가 외부에서 스팸 메일을 보내는 경우 보고 합니다. 이는 계정이 손상 되었음을 나타내는 지표로 표시 될 수 있습니다.
- 모든 사용자에 대해 원격 PowerShell 사용 안 함-원격 PowerShell은 주로 관리자가 관리 목적 또는 프로그래밍 API 액세스용으로 서비스에 액세스 하는 데 사용 됩니다. 관리자가 아닌 사용자에 게는이 옵션을 사용 하지 않는 것이 좋습니다. 
- 관리자가 아닌 모든 사람에 대 한 Microsoft Azure 관리 포털 액세스를 차단 합니다. 관리자를 제외 하 고 모든 사용자를 차단 하는 조건부 액세스 규칙을 만들어이 작업을 수행할 수 있습니다. 


## <a name="assume-breach"></a>위반 가정

Microsoft는 위협 및 공격을 방지 하기 위해 가능한 모든 조치를 취하는 반면, "위반 가정" 이라는 마음가짐에서 항상 작업 하는 것이 좋습니다. 공격자가 환경에 intrude를 관리 하더라도 환경에서 데이터 나 id 정보를 exfiltrate 수 있는지 확인 해야 합니다. 따라서 주민 등록 번호, 신용 카드 번호, 추가 개인 정보 및 기타 조직 수준 기밀 정보와 같은 중요 한 데이터 누수 로부터 보호를 사용 하도록 설정 하는 것이 좋습니다. 

"위반 가정" 마음가짐에서는 사용자가 네트워크 내부에 있기 때문에 완전히 신뢰 되지 않는다는 것을 의미 하는 제로 트러스트 네트워크 전략을 구현 해야 합니다. 대신 사용자가 수행할 수 있는 작업, 조건 집합, 그리고 이러한 조건이 충족 되는 경우 특정 컨트롤이 적용 됩니다. 조건에는 장치 상태, 액세스 중인 응용 프로그램, 수행 중인 작업 및 사용자 위험이 포함 될 수 있습니다. 예를 들어 장치 등록 작업은 항상 MFA 인증을 트리거하여 환경에 rouge 장치가 추가 되지 않도록 해야 합니다. 

또한 제로 트러스트 네트워크 전략을 사용 하려면 정보가 저장 된 위치를 알고 있어야 하며 분류, 보호 및 보존을 위한 적절 한 제어를 적용 해야 합니다. 가장 중요 하 고 중요 한 자산을 효과적으로 보호 하려면 먼저 이러한 자산의 위치를 파악 하 고 인벤터리를 사용 하 여 작업을 수행 하는 것이 어려울 수 있습니다. 다음으로, 조직과 협력 하 여 거 버 넌 스 전략을 정의 합니다. 조직에 대 한 분류 스키마를 정의 하 고 정책, 레이블 및 조건을 구성 하려면 신중한 계획 및 준비를 수행 해야 합니다. 이 프로세스는 IT 구동 프로세스가 아니라는 것을 염두에 두어야 합니다. 법률 및 준수 팀과 협력 하 여 조직의 데이터에 대 한 적절 한 분류 및 레이블 지정 스키마를 개발 해야 합니다.

Microsoft 365 information protection 기능은 보유 한 정보, 저장 위치 및 추가 보호가 필요한 정보를 파악 하는 데 도움이 될 수 있습니다. 정보 보호는 지속적인 프로세스 이며 Microsoft 365 기능은 사용자가 현재 저장 되어 있는 중요 한 정보, 그리고 정보가 흐르는 위치를 표시 하는 방법을 제공 합니다. 또한 사용자가 적절 한 레이블과 보호가 적용 되도록 규정 된 정보를 처리 하는 방법도 볼 수 있습니다.


|권장 사항 |E3|E5 |
|---------|---------|---------|
|**제로 트러스트 네트워크에 대 한 목표에 맞게 조건부 액세스 및 관련 정책을 검토 하 고 최적화**합니다. 알려진 위협 으로부터 보호 하려면 [권장 되는 정책](../enterprise/microsoft-365-policies-configurations.md)집합을 구현 하는 것이 포함 됩니다. 이러한 정책의 구현을 검토 하 여 네트워크에 대 한 액세스 권한을 얻은 해커 로부터 앱 및 데이터를 보호 하 고 있는지 확인 합니다. Windows 10 용 권장 Intune 앱 보호 정책에는 WIP (Windows Information Protection)가 사용 됩니다. WIP는 전자 메일, 소셜 미디어, 공용 클라우드 등의 앱 및 서비스를 통해 조직 데이터를 실수로 누설 하지 않도록 보호 합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**외부 전자 메일 전달을 사용 하지 않도록 설정**합니다. 사용자의 사서함에 대 한 액세스 권한을 획득 하는 해커는 전자 메일을 자동으로 전달 하도록 사서함을 설정 하 여 메일을 도용할 수 있습니다. 사용자의 인식이 없어도이 문제가 발생할 수 있습니다. 메일 흐름 규칙을 구성 하 여 이러한 상황이 발생 하지 않도록 할 수 있습니다.|![녹색 확인 표시](../media/green-check-mark.png) |![녹색 확인 표시](../media/green-check-mark.png)|
|**익명 외부 일정 공유를 사용 하지 않도록 설정**합니다. 기본적으로 외부 익명 일정 공유를 사용할 수 있습니다. [일정 공유를 사용 하지 않도록 설정](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) 하 여 중요 한 정보의 잠재적 누출을 줄입니다.|![녹색 확인 표시](../media/green-check-mark.png) |![녹색 확인 표시](../media/green-check-mark.png)|
|**중요 한 데이터에 대 한 데이터 손실 방지 정책을 구성**합니다. 보안 및 준수 센터에서 데이터 손실 방지 정책을 만들어 &amp; 신용 카드 번호, 주민 등록 번호 및 은행 계좌 번호와 같은 중요 한 데이터를 검색 하 고 보호 합니다. Microsoft 365에는 데이터 손실 방지 정책에서 사용할 수 있는 미리 정의 된 중요 한 정보 유형이 많이 포함 되어 있습니다. 또한 환경에 사용자 지정 된 중요 한 데이터에 대 한 중요 한 정보 유형을 직접 만들 수도 있습니다. |![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**데이터 분류 및 정보 보호 정책을 구현**합니다. 민감도 레이블을 구현 하 고이를 사용 하 여 중요 한 데이터에 보호 기능을 분류 하 고 적용 합니다. 데이터 손실 방지 정책 에서도 이러한 레이블을 사용할 수 있습니다. Azure Information Protection 레이블을 사용 하는 경우에는 다른 관리 센터에서 새 레이블을 만드는 것을 피하는 것이 좋습니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|
|**Cloud App Security를 사용 하 여 타사 앱 및 서비스의 데이터를 보호**합니다. Cloud App Security 정책을 구성 하 여 Salesforce, Box 또는 Dropbox와 같은 타사 클라우드 앱에서 중요 한 정보를 보호 합니다. 클라우드 앱 보안 정책에서 만든 민감도 레이블과 중요 한 정보 유형을 사용 하 고이를 SaaS 앱 전체에 적용할 수 있습니다. <br><br>Microsoft Cloud App Security를 사용 하면 다양 한 범위의 자동화 된 프로세스를 적용할 수 있습니다. 지속적인 준수 검사, 법적 eDiscovery 작업, 중요 한 콘텐츠에 대해 공유 되는 DLP를 제공 하는 정책을 설정할 수 있습니다. Cloud App Security에서는 20 개 이상의 메타 데이터 필터 (예: 액세스 수준, 파일 형식)를 기반으로 모든 파일 형식을 모니터링할 수 있습니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|** [MICROSOFT Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) 를 사용 하 여 사용자가 Windows 장치에 중요 한 정보를 저장 하는지 확인**합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|** [Aip 스캐너](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) 를 사용 하 여 서버 및 파일 공유에서 정보를 식별 하 고 분류**합니다. AIP 보고 도구를 사용 하 여 결과를 확인 하 고 적절 한 작업을 수행 합니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|

다음 다이어그램에서는 이러한 기능을 보여 줍니다.
![위반 으로부터 보호 하기 위한 권장 기능](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>지속적인 모니터링 및 감사

마지막으로, 모든 침입을 신속 하 게 감지 하 고 수정할 수 있도록 Microsoft 365 환경에서 Windows 및 장치와 함께 계속 해 서 모니터링 및 감사를 수행 하는 것은 매우 중요 합니다. 보안 점수, 보안 센터 및 Microsoft 지능형 그래프의 고급 분석 같은 도구를 통해 테 넌 트에 귀중 한 정보를 제공 하 고 매우 강력한 위협 요소 및 보안 데이터를 연결 하 여 위협에 대 한 보호 및 감지를 제공 합니다.


|권장 사항 |E3 |E5 |
|---------|---------|---------|
|**감사 로그** 를 사용 하도록 설정 되어 있는지 확인 합니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**보안 점수 매주 검토** -보안 점수는 회사의 보안 상태에 액세스 하 고 보안 점수 권장 사항을 기반으로 작업을 수행 하는 중앙 위치입니다. 매주이 검사를 수행 하는 것이 좋습니다.|![녹색 확인 표시](../media/green-check-mark.png)|![녹색 확인 표시](../media/green-check-mark.png)|
|**Office 365 ATP** 도구 사용:<br>* 위협 조사 및 응답 기능<br> * 자동화 된 조사 및 대응 |         |![녹색 확인 표시](../media/green-check-mark.png)|
|**Microsoft DEFENDER ATP**사용:<br> *    [끝점 검색 및 응답](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * 자동화 된 조사 및 치료 보안 점수 <br>*    [고급 구하기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![녹색 확인 표시](../media/green-check-mark.png)|
|**Microsoft Cloud App Security** 를 사용 하 여 클라우드 앱 간의 비정상적인 동작을 검색 하 여 랜 섬 웨어, 손상 된 사용자 또는 rogue 응용 프로그램을 식별 하 고, 높은 위험 사용을 분석 하 고, 자동으로 조직에 대 한 위험을 제한 합니다.|         |![녹색 확인 표시](../media/green-check-mark.png)|
|**Microsoft Azure 센티널** 또는 현재 siem 도구를 사용 하 여 환경 전반의 위협을 모니터링 합니다. |         |![녹색 확인 표시](../media/green-check-mark.png)|
|** [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 를 배포** 하 여 온-프레미스 Active Directory 환경을 대상으로 하는 위협 으로부터 모니터링 하 고 보호 합니다.   |         |![녹색 확인 표시](../media/green-check-mark.png) |
|**Azure 보안 센터** 를 사용 하 여 하이브리드 및 클라우드 워크 로드 간의 위협을 모니터링 합니다. Azure 보안 센터에는 리소스 시간이 나 거래에 따라 지불 되는 기능에 대 한 무료 계층 및 표준 계층이 포함 되어 있습니다.|         |         |

다음 다이어그램에서는 이러한 기능을 보여 줍니다.
![지속적인 모니터링 및 감사를 위한 권장 기능](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

권장 되는 주요 모니터링 작업:
- **Microsoft 보안 점수 매주 검토** -보안 점수는 테 넌 트의 보안 상태에 액세스 하 고 최상위 추천을 기반으로 작업을 수행 하는 중앙 위치입니다. 매주이 검사를 수행 하는 것이 좋습니다. 보안 점수에는 Office 365 뿐만 아니라 Azure AD, Intune, Cloud App Security 및 Microsoft Defender Advanced Threat Protection에 대 한 권장 사항이 포함 되어 있습니다. 
- **매주 위험한 로그인 검토** -Azure AD 관리 센터를 사용 하 여 위험 로그인을 매주 검토 합니다. 권장 되는 id 및 장치 액세스 규칙 집합에는 위험한 로그인에 대 한 암호 변경을 적용 하는 정책이 포함 되어 있습니다.  
- **주요 맬웨어 및 phished 사용자를 매주 검토** 하 고, Office Advanced Threat Protection Threat Explorer를 사용 하 여 맬웨어 및 피싱를 대상으로 하는 최고 사용자를 검토 하 고, 이러한 사용자에 게 영향을 주는 이유를 확인할 수 있습니다.
