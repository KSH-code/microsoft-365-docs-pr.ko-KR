---
title: 고객 키의 가용성 키에 대 한 자세한 정보
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 손실 된 고객 키를 복구 하는 데 사용 되는 가용성 키에 대해 알아봅니다.
ms.openlocfilehash: 8e9903294d5fc25e51ef25c0ae6237c943dec6ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632027"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>고객 키의 가용성 키에 대 한 자세한 정보

가용성 키는 데이터 암호화 정책을 만들 때 자동으로 생성 되 고 프로 비전 되는 루트 키입니다. Microsoft 365에서는 가용성 키를 저장 하 고 보호 합니다. 가용성 키는 고객 키를 사용한 서비스 암호화에 제공 되는 두 가지 루트 키와 동일 합니다. 가용성 키는 키 계층 구조에서 1 계층 보다 작은 키를 배치 합니다. Azure 키 자격 증명 모음에서 제공 하 고 관리 하는 키와 달리 가용성 키에 직접 액세스할 수 없습니다. Microsoft 365 자동화 된 서비스는 가용성 키를 프로그래밍 방식으로 관리 합니다. 이러한 서비스는 가용성 키에 직접 액세스 하지 않는 자동화 된 작업을 시작 합니다.

가용성 키의 기본 목적은 사용자가 관리 하는 예상 루트 키 손실 로부터 복구 기능을 제공 하는 것입니다. Mismanagement 또는 악의적인 작업의 결과로 손실 될 수 있습니다. 루트 키를 제어할 수 없는 경우 microsoft 지원 서비스에 문의 하 여 가용성 키를 사용한 복구 프로세스를 지원 해 드릴 수 있습니다. 가용성 키를 사용 하 여 새로운 루트 키를 프로 비전 한 새 데이터 암호화 정책으로 마이그레이션합니다.

가용성 키에 대 한 저장소 및 제어는 다음과 같은 세 가지 이유로 인해 Azure 키 보관소와는 다릅니다.

- 가용성 키를 사용 하면 두 Azure 키를 모두 제어할 수 없는 경우 "고장 유리" 기능을 제공 합니다.
- 논리적 컨트롤과 안전한 저장소 위치를 분리 하면 단일 공격이 나 실패 지점에서 모든 키 및 데이터 손실을 방지 하 고 보안을 강화 하 고 보호할 수가 있습니다.
- Microsoft 365 서비스가 일시적인 오류로 인해 Azure 키 자격 증명 모음에 호스트 된 키에 연결할 수 없는 경우 가용성 키를 통해 고가용성 기능을 제공 합니다. 이 규칙은 Exchange Online 및 비즈니스용 Skype 서비스 암호화에만 적용 됩니다. SharePoint Online, 비즈니스용 OneDrive 및 팀 파일은 Microsoft가 복구 프로세스를 시작 하도록 명시적으로 지시 하지 않으면 가용성 키를 사용 하지 않는 것이 좋습니다.

키 관리에 대 한 다양 한 보호 및 프로세스를 사용 하 여 데이터를 보호 하는 책임을 공유 하면 결국 모든 키 (즉, 데이터)가 영구적으로 손실 되거나 소멸 되는 위험을 줄일 수 있습니다. Microsoft는 서비스를 떠날 때 가용성 키를 비활성화 기능이 하는 단독 기관을 제공 합니다. Microsoft의 가용성 키에 대 한 액세스 권한이 있는 사람에 게는 기본적으로 Microsoft 365 서비스 코드 에서만 액세스할 수 있습니다.

키를 보호 하는 방법에 대 한 자세한 내용은 [Microsoft 보안 센터](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) 를 참조 하세요.
  
## <a name="availability-key-uses"></a>가용성 키 사용

가용성 키는 외부 malefactor 또는 악의적인 사용자가 키 자격 증명 모음을 도용 하거나 실수로 mismanagement 경우 루트 키가 손실 되는 경우의 복구 기능을 제공 합니다. 이 복구 기능은 고객 키와 호환 되는 모든 Microsoft 365 서비스에 적용 됩니다. 개별 서비스에서는 가용성 키를 다르게 사용 합니다. Microsoft 365는 아래 설명 된 방법 으로만 가용성 키를 사용 합니다.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online 및 비즈니스용 Skype 사용

복구 기능 외에도 Exchange Online 및 비즈니스용 Skype는 가용성 키를 사용 하 여 일시적으로 또는 일시적인 운영 문제 중에는 루트 키에 액세스 하는 서비스와 관련 된 데이터 가용성을 보장 합니다. 서비스가 일시적인 오류로 인해 Azure 키 자격 증명 모음의 고객 키에 연결할 수 없는 경우 서비스에서 자동으로 가용성 키를 사용 합니다. 서비스가 가용성 키로 직접 이동 하지 않습니다.

Exchange Online 및 비즈니스용 Skype의 자동화 된 시스템은 일시적인 오류가 발생 하는 경우 가용성 키를 사용 하 여 바이러스 백신, 전자 검색, 데이터 손실 방지, 사서함 이동 및 데이터 인덱싱과 같은 자동화 된 백 엔드 서비스를 지원할 수 있습니다.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에서는 다음을 사용 합니다.

SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우 가용성 키가 복구 기능 외부에서 사용 되지 않으며, 고객은 복구 시나리오에서 가용성 키 사용을 시작 하도록 Microsoft에 명시적으로 지시 해야 합니다. 자동화 된 서비스 작업은 Azure 키 자격 증명 모음의 고객 키에만 의존 합니다. 이러한 서비스에 대해 키 계층 구조가 작동 하는 방식에 대 한 자세한 내용은 [SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에서 가용성 키를 사용](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)하는 방법을 참조 하세요.

## <a name="availability-key-security"></a>가용성 키 보안

Microsoft는 가용성 키를 인스턴스화하고이를 보호 하기 위해 광범위 한 조치를 취하는 방식으로 데이터 보호 책임을 공유 합니다. Microsoft는 가용성 키에 대 한 직접 제어를 고객에 게 공개 하지 않습니다. 예를 들어 Azure Key Vault에서 소유한 키만 롤 (회전) 할 수 있습니다. 자세한 내용은 [고객 키 또는 가용성 키 롤 또는 회전을](customer-key-availability-key-roll.md)참조 하세요.

### <a name="availability-key-secret-stores"></a>가용성 키 보안 저장소

Microsoft는 고객 연결 Azure 키 보관소와 같은 액세스 제어, 내부 비밀 저장소의 가용성 키를 보호 합니다. Microsoft 관리자가에 포함 된 암호에 직접 액세스 하지 못하도록 액세스 제어를 구현 합니다. 키 회전과 삭제를 포함 하는 보안 저장소 작업은 가용성 키에 직접 액세스 하지 않는 자동화 된 명령을 통해 발생 합니다. 보안 저장소 관리 작업은 특정 엔지니어만 사용할 수 있으며 내부 도구인 Lockbox를 통해 권한 에스컬레이션이 필요 합니다. 권한 에스컬레이션을 사용 하려면 관리자 승인 및 근거를 부여 해야 합니다. Lockbox는 시간이 만료 되거나 로그 아웃 될 때 자동 액세스 해지와의 시간 제한이 있습니다.

**Exchange online 및 비즈니스용 Skype** 가용성 키는 Exchange Online Active Directory 암호 저장소에 저장 됩니다. 가용성 키는 Active Directory 도메인 컨트롤러 내의 테 넌 트 특정 컨테이너 내에 안전 하 게 저장 됩니다. 이 보안 저장소 위치는 SharePoint Online, 비즈니스용 OneDrive 및 팀 파일 비밀 저장소와 분리 되어 격리 됩니다.

**SharePoint Online, 비즈니스용 OneDrive 및 팀 파일** 가용성 키는 서비스 팀이 관리 하는 내부 비밀 저장소에 저장 됩니다. 이 보안, 비밀 저장소 서비스는 응용 프로그램 끝점과 SQL 데이터베이스를 백 엔드로 사용 하는 프런트 엔드 서버를 포함 합니다. 가용성 키는 SQL 데이터베이스에 저장 되며, AES-256와 HMAC를 함께 사용 하 여 rest에서 가용성 키를 암호화 하는 비밀 저장소 암호화 키로 래핑 (암호화) 됩니다. 보안 저장소 암호화 키는 동일한 SQL 데이터베이스의 논리적으로 분리 된 구성 요소에 저장 되며 Microsoft CA (인증 기관)에서 관리 하는 인증서에 포함 된 RSA-2048 키를 통해 추가로 암호화 됩니다. 이러한 인증서는 데이터베이스에 대 한 작업을 수행 하는 보안 저장소 프런트 엔드 서버에 저장 됩니다.

### <a name="defense-in-depth"></a>심층 방어

Microsoft는 악의적인 행위자가 Microsoft 클라우드에 저장 된 고객 데이터의 기밀성, 무결성 또는 가용성에 영향을 주지 않도록 하는 심층 방어 전략을 채택 하 고 있습니다. 특정 예방 및 예방용 인지 컨트롤은 중요 보안 전략의 일부로 서 비밀 저장소 및 가용성 키를 보호 하기 위해 구현 됩니다.

가용성 키의 오용을 방지 하기 위해 Microsoft 365이 구축 됩니다. 응용 프로그램 계층은 가용성 키를 비롯 한 키를 사용 하 여 데이터를 암호화 하 고 암호를 해독 하는 유일한 방법입니다. Microsoft 365 서비스 코드만에는 암호화 및 암호 해독 작업을 위한 키 계층 구조를 해석 하 고 트래버스할 수 있는 기능이 있습니다. 논리적 격리는 고객 키, 가용성 키, 기타 계층적 키 및 고객 데이터의 저장 위치 사이에 존재 합니다. 이 격리는 하나 이상의 위치가 손상 되는 경우 데이터 노출 위험을 완화 합니다. 계층 구조의 각 계층은 데이터 및 비밀 저장을 보호 하기 위해 연중 무휴의 침입 검색 기능을 구축 했습니다.

액세스 제어는 가용성 키 보안 저장소를 포함 하 여 내부 시스템에 대 한 무단 액세스를 방지 하기 위해 구현 됩니다. Microsoft 엔지니어가 가용성 키 보안 저장소에 직접 액세스할 수 없습니다. 액세스 제어에 대 한 자세한 내용은 [Microsoft 365에서 관리 액세스 제어](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview)를 검토 하십시오.

기술 제어는 Microsoft 담당자가 높은 권한의 서비스 계정에 로그인 하지 못하도록 차단 하며,이는 공격자가 Microsoft 서비스를 가장 하는 데 사용 될 수도 있습니다. 예를 들어 이러한 컨트롤은 대화형 로그온을 방지 합니다.

보안 로깅 및 모니터링 제어는 Microsoft 서비스 및 데이터에 대 한 위험을 완화 하는 또 다른 심층 방어 방지 수단입니다. Microsoft 서비스 팀은 경고 및 감사 로그를 생성 하는 활성 모니터링 솔루션을 배포 했습니다. 모든 서비스 팀은 로그를 집계 하 고 처리 하는 중앙 리포지토리에 로그를 업로드 합니다. 내부 도구는 자동으로 레코드를 검사 하 여 서비스가 최적의 상태 이며 탄력적 이며 안전한 상태로 작동 하 고 있는지 확인 합니다. 이상한 활동에는 추가 검토를 위해 플래그가 지정 됩니다.

Microsoft 보안 정책에 대 한 잠재적 위반을 나타내는 모든 로그 이벤트는 Microsoft 보안 팀의 주의를 통해 즉시 제공 됩니다. Microsoft 365 security에서 가용성 키 비밀 저장소에 대 한 시도 된 액세스를 검색 하도록 경고를 구성 했습니다. Microsoft 직원이 서비스 계정에 대화형 로그온을 시도 하는 경우 (액세스 제어에 의해 금지 및 보호 됨)에도 경고가 생성 됩니다. Microsoft 365 보안은 또한 일반적인 초기 작업에서 Microsoft 365 서비스의 편차를 감지 하 고 경고 합니다. Microsoft 365 서비스를 악용 하려고 시도 하면 Microsoft 클라우드 환경에서 Malefactors의 제거를 유발 하는 경고가 발생 합니다.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>가용성 키를 사용 하 여 키 손실 복구

고객 키에 대 한 제어 권한이 없는 경우 가용성 키를 통해 데이터를 복구 하 고 다시 암호화할 수 있습니다.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 복구 절차

고객 키를 제어할 수 없는 경우 가용성 키를 통해 데이터를 복구 하 고 영향을 받는 Microsoft 365 리소스를 다시 온라인 상태로 전환할 수 있습니다. 가용성 키는 복구 하는 동안 계속 해 서 데이터를 보호 합니다. 키 손실에서 완전히 복구 하려면 높은 수준에서 새 DEP를 만들고 영향을 받는 리소스를 새 정책으로 이동 해야 합니다.

새 고객 키를 사용 하 여 데이터를 암호화 하려면 Azure 키 자격 증명 모음에서 새 키를 만들고 새 고객 키를 사용 하 여 새 dep를 만든 다음 키가 손실 되거나 손상 된 이전 DEP를 사용 하 여 현재 암호화 된 사서함에 새 DEP를 할당 합니다.

이 다시 암호화 프로세스는 최대 72 시간까지 소요 될 수 있습니다. 이 시간은 DEP를 변경할 때의 표준 기간입니다.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 복구 절차

SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우에는 가용성 키가 복구 기능 외부에서 사용 되지 않습니다. 복구 시나리오에서 가용성 키 사용을 시작 하도록 Microsoft에 명시적으로 지시 해야 합니다. 복구 프로세스를 시작 하려면 Microsoft에 가용성 키를 활성화 하도록 요청 합니다. 일단 활성화 되 면 가용성 키가 새 고객 키와 연결 된 새로 만든 DEP로 데이터를 암호화할 수 있도록 데이터 암호를 해독 하는 데 자동으로 사용 됩니다.  

이 작업은 조직의 사이트 수에 비례 합니다. Microsoft에 전화를 걸어 가용성 키를 사용 하려면 약 4 시간 이내에 완벽 하 게 온라인 상태 여야 합니다.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online 및 비즈니스용 Skype에서 가용성 키를 사용 하는 방법

고객 키를 사용 하 여 DEP를 만들면 Microsoft 365에서 해당 DEP와 연결 된 DEP 키 (데이터 암호화 정책 키)를 생성 합니다. 서비스는 두 번의 각 고객 키와 가용성 키를 사용 하 여 DEP 키를 3 회 암호화 합니다. 암호화 된 버전의 DEP 키만 저장 되 고, DEP 키는 고객 키 또는 가용성 키로만 해독 될 수 있습니다. 그런 다음 개별 사서함을 암호화 하는 사서함 키를 암호화 하는 데 DEP 키를 사용 합니다.
  
다음 프로세스에 따라 고객이 서비스를 사용할 때 데이터를 해독 하 고 제공 합니다. 365
  
1. 고객 키를 사용 하 여 DEP 키의 암호를 해독 합니다.

2. 암호 해독 된 DEP 키를 사용 하 여 사서함 키를 해독 합니다.

3. 암호 해독 된 사서함 키를 사용 하 여 사서함 자체의 암호를 해독 하 여 사서함 내의 데이터에 액세스할 수 있도록 합니다.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일은 가용성 키를 사용 하는 방법

고객 키 및 가용성 키에 대 한 SharePoint Online 및 비즈니스용 OneDrive 아키텍처 및 구현은 Exchange Online 및 비즈니스용 Skype와 다릅니다.
  
조직이 고객 관리 키로 이동 하면 Microsoft 365에서 조직별 중간 키 (TIK)를 만듭니다. Microsoft 365에서는 각 고객 키와 함께 TIK를 두 번 암호화 하 고 두 가지 암호화 버전의 TIK를 저장 합니다. 암호화 된 버전의 TIK만 저장 되 고, TIK는 customer 키로만 암호를 해독할 수 있습니다. 그런 다음 TIK는 blob 키 (파일 청크 키 라고도 함)를 암호화 하는 데 사용 되는 사이트 키를 암호화 하는 데 사용 됩니다. 파일 크기에 따라 서비스에서는 각각 고유한 키를 사용 하 여 파일을 여러 파일 청크로 분할할 수 있습니다. Blob 키를 사용 하 여 blob (파일 청크) 자체를 암호화 하 고 Microsoft Azure Blob 저장소 서비스에 저장 합니다.
  
고객이 서비스를 사용할 때 고객 파일의 암호를 해독 하 고 제공 하기 위해 Microsoft 365에서는 다음과 같은 프로세스를 따릅니다.

1. 고객 키를 사용 하 여 TIK의 암호를 해독 합니다.

2. 암호 해독 된 TIK를 사용 하 여 사이트 키의 암호를 해독 합니다.

3. 암호 해독 된 사이트 키를 사용 하 여 blob 키를 해독 합니다.

4. 해독 된 blob 키를 사용 하 여 blob 암호를 해독 합니다.

Microsoft 365에서는 두 개의 암호 해독 요청을 약간의 오프셋으로 Azure Key Vault에 발급 하 여 TIK를 해독 합니다. 처음에는 검색을 완료 하 여 결과를 제공 다른 요청을 취소 합니다.
  
고객 키에 대 한 액세스 권한이 없는 경우 Microsoft 365는 또한 사용 가능 키를 사용 하 여 TIK를 암호화 하 고, 각 고객 키로 암호화 된 Tik와 함께이를 저장 합니다. 가용성 키를 사용 하 여 암호화 된 TIK는 고객이 악의적으로 또는 실수로 키에 대 한 액세스 권한을 손실 했을 때 복구 경로를 등록 해야 하는 경우에만 사용 됩니다.
  
가용성 및 확장 상의 이유로, 암호 해독 된 TIKs는 시간 제한 메모리 캐시에 캐시 됩니다. TIK 캐시가 만료 되도록 설정 하기 전까지 두 시간 동안 Microsoft 365에서는 각 TIK를 해독 하려고 시도 합니다. TIKs를 해독 하면 캐시의 수명이 연장 됩니다. TIK 암호 해독이 상당한 시간 동안 실패 하면 Microsoft 365는 캐시 만료 전에 엔지니어링에 알리기 위한 경고를 생성 합니다. 고객이 microsoft 365에서 전화를 거는 경우에만 microsoft는 microsoft의 비밀 저장소에 저장 된 가용성 키로 TIK의 암호를 해독 하 고, 해독 된 TIK 및 고객 제공 Azure 키 자격 증명 모음 키의 새 집합을 사용 하 여 해당 테 넌 트를 다시 보 딩 하는 복구 작업을 시작 합니다.
  
현재로 서는 고객 키가 Azure blob 저장소에 저장 된 SharePoint Online 파일 데이터의 암호화 및 암호 해독 체인에 포함 되지만 SharePoint Online 목록 항목이 나 SQL 데이터베이스에 저장 된 메타 데이터는 제외 됩니다. Microsoft 365에서 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 위에 설명 된 사례 (고객 시작)에 게는 가용성 키를 사용 하지 않습니다. 고객 데이터에 대 한 사용자 액세스는 고객 Lockbox에 의해 보호 됩니다.

## <a name="availability-key-triggers"></a>가용성 키 트리거

Microsoft 365는 특정 상황 에서만 가용성 키를 트리거합니다. 이러한 상황은 서비스에 따라 다릅니다.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 트리거
  
1. Microsoft 365는 Azure 키 자격 증명 모음에서 두 고객 키의 위치를 확인 하기 위해 사서함이 할당 되는 DEP를 읽습니다.

2. Microsoft 365는 DEP에서 두 고객 키 중 하나를 선택 하 고 Azure Key Vault에 요청을 보내 고객 키를 사용 하 여 DEP 키를 래핑 해제 합니다.

3. 고객 키를 사용 하 여 DEP 키의 래핑을 해제 하는 요청이 실패 하면 Microsoft 365는 Azure 키 보관소에 두 번째 요청을 전송 하며,이 시간에는 대체 (두 번째) 고객 키를 사용 하도록 지시 합니다.

4. 고객 키를 사용 하 여 DEP 키의 래핑을 해제 하는 두 번째 요청이 실패 하면 Microsoft 365에서 두 요청의 결과를 검사 합니다.

    - 검사 결과, 요청이 시스템 오류를 반환 하는 데 실패 한 것으로 확인 된 경우:

       - Microsoft 365에서 가용성 키를 트리거하여 DEP 키의 암호를 해독 합니다.

       - Microsoft 365에서는 DEP 키를 사용 하 여 사서함 키의 암호를 해독 하 고 사용자 요청을 완료 합니다. 

       - 이 경우 Azure 키 보관소가 일시적인 오류로 인해 응답 하지 않거나 연결할 수 없습니다.

    - 검사 결과 요청이 거부 된 액세스를 반환 하지 못했음을 확인 한 경우:

       - 즉, 서비스를 종료 하는 과정에서 데이터 제거 프로세스 중에 사용자 키를 사용할 수 없게 되는 경우를 위해 의도적인, 실수로 또는 악성 작업을 수행 합니다.

       - 이 경우 가용성 키는 사용자 작업을 수행 하는 것이 아니라 시스템 작업에만 사용 되며, 사용자 요청이 실패 하 고, 사용자가 오류 메시지를 받습니다.

>[!IMPORTANT]
>Microsoft 365 서비스 코드는 항상 고객 데이터를 통해 가치를 강화 하는 클라우드 서비스를 제공 하기 위한 유효한 로그인 토큰을 포함 합니다. 따라서 가용성 키가 삭제 될 때 까지는 검색 인덱스를 만들거나 사서함을 이동 하는 등의 작업을 시작 하거나 내부에서 Exchange Online 및 비즈니스용 Skype의 대체로 사용할 수 있습니다. 이는 Azure 키 자격 증명에 대 한 일시적인 오류 및 액세스 거부 요청에 모두 적용 됩니다.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 트리거

SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우 가용성 키가 복구 기능 외부에서 사용 되지 않으며, 고객은 복구 시나리오에서 가용성 키 사용을 시작 하도록 Microsoft에 명시적으로 지시 해야 합니다.

## <a name="audit-logs-and-the-availability-key"></a>감사 로그 및 가용성 키

Microsoft 365의 자동화 된 시스템은 시스템을 통해 전달 되는 모든 데이터를 처리 하 여 바이러스 백신, 전자 검색, 데이터 손실 방지 및 데이터 인덱싱과 같은 클라우드 서비스를 제공 합니다. Microsoft 365에서이 작업에 대해 고객에 게 표시 되는 로그를 생성 하지 않습니다. 또한 Microsoft 직원은 이러한 일반 시스템 작업의 일부로 데이터에 액세스 하지 못합니다.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online 및 비즈니스용 Skype 가용성 키 로깅

Exchange Online 및 비즈니스용 Skype 액세스 가용성 키를 통해 서비스를 제공 하는 경우 Microsoft 365는 보안 및 준수 센터에서 액세스할 수 있는 고객에 게 표시 되는 로그를 게시 합니다. 가용성 키 작업에 대 한 감사 로그 레코드는 서비스에서 가용성 키를 사용할 때마다 생성 됩니다. "고객 키 서비스 암호화" 라는 새 레코드 유형 (활동 유형이 "Fallback to Availability Key")을 사용 하면 관리자가 [통합 감사 로그](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 검색 결과를 필터링 하 여 가용성 키 레코드를 볼 수 있습니다.

로그 레코드에는 날짜, 시간, 활동, 조직 ID 및 데이터 암호화 정책 ID와 같은 특성이 포함 됩니다. 이 레코드는 통합 된 감사 로그의 일부로 사용할 수 있으며 보안 & 준수 센터 감사 로그 검색 탭에서 액세스 가능 합니다.

![가용성 키 이벤트에 대 한 감사 로그 검색](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online 및 비즈니스용 Skype 가용성 키 레코드는 사용자 지정 매개 변수 정책 Id, 범위 키 버전 Id 및 요청 Id와 함께 Office 365 관리 작업 [일반 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 를 사용 합니다.

![가용성 키 사용자 지정 매개 변수](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일 가용성 키 로깅

이러한 서비스에 대해서는 가용성 키 로깅을 사용할 수 없습니다. SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 경우 가용성 키는 사용자가 복구를 위해 지시한 경우에만 정품 인증을 받아야 합니다. 따라서 이러한 서비스에 대 한 가용성 키가 사용 되는 모든 이벤트를 이미 알고 있습니다.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>고객 키 계층 구조의 가용성 키
  
Microsoft 365에서는 가용성 키를 사용 하 여 고객 키 서비스 암호화에 대해 설정 된 키 계층 구조의 하위 키 계층을 래핑합니다. 서비스 간에는 서로 다른 주요 계층 구조가 있습니다. 또한 주요 알고리즘은 적용 가능한 각 서비스의 계층 구조에 있는 다른 키와 가용성 키 사이에도 차이가 있습니다. 서로 다른 서비스에서 사용 하는 가용성 키 알고리즘은 다음과 같습니다.

- Exchange Online 및 비즈니스용 Skype 가용성 키는 AES-256를 사용 합니다.

- SharePoint Online, 비즈니스용 OneDrive 및 팀 파일 가용성 키는 RSA-2048을 사용 합니다.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 키를 암호화 하는 데 사용 되는 암호화 암호

![Exchange Online 고객 키에 대 한 암호화 암호](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive의 키를 암호화 하는 데 사용 되는 암호화 암호

![SharePoint Online 고객 키에 대 한 암호화 암호](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)
