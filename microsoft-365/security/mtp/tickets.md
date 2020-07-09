---
title: ServiceNow 티켓을 Microsoft 365 보안 센터 및 준수 센터에 통합
description: Microsoft 365 보안 센터 및 준수 센터에서 ServiceNow의 티켓을 만들고 추적 하는 방법에 대해 알아봅니다.
keywords: 보안, Microsoft 365, M365, 규정 준수, 준수 센터, 보안 센터, ServiceNow, 티켓, 작업, 눈, 연결
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086670"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>ServiceNow 티켓을 Microsoft 365 보안 센터 및 준수 센터에 통합

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow는 회사에서 엔터프라이즈 운영을 위한 디지털 워크플로를 관리 하는 데 사용할 수 있는 인기 있는 클라우드 컴퓨팅 플랫폼입니다. 현재 플랫폼에는 IT 워크플로, 직원 워크플로 및 고객 워크플로가 포함 되어 있습니다. [ServiceNow에 대해 자세히 알아보기](https://www.servicenow.com/)

Microsoft는 IT 관리자가 두 플랫폼에서 모두 티켓과 작업을 보다 쉽게 관리할 수 있도록 ServiceNow과 제휴 합니다. [Microsoft 365 보안 센터](overview-security-center.md) 및 [microsoft 365 준수 센터](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) 는 ServiceNow에서 티켓을 기본적으로 만들고 추적할 수 있는 기능을 통해 향상 되었습니다.

- [**보안 센터에서 ServiceNow 티켓 관리**](tickets-security-center.md)
- **준수 센터에서 ServiceNow 티켓 관리** (출시 예정)

## <a name="prerequisites"></a>전제 조건

다음을 포함 하는 Microsoft 365 보안 센터 또는 준수 센터 및 ServiceNow 인스턴스에 대 한 액세스 권한이 있어야 합니다.  

* Kingston 이상 버전
* 관리자 용 자격 증명 포함
* 대상 공급 업체 인스턴스에 대해 관리자 권한이 있어야 합니다.

ServiceNow에서는 사용자가 ServiceNow 인스턴스에 기본 설정을 유지 하는 것이 좋습니다. 사용자 지정 내용이 있으면 설치 검사 목록이 완료 되 고 Microsoft 365 보안 센터와 통합 될 때 오류가 발생할 수 있습니다.

## <a name="data-exchange"></a>데이터 교환

Microsoft 365 보안 센터 또는 준수 센터를 ServiceNow에 연결 하면 Microsoft에서 다음과 같은 추가 데이터를 받게 됩니다.

* ServiceNow 인스턴스 이름
* ServiceNow 클라이언트 ID
* ServiceNow 클라이언트 암호
* ServiceNow 액세스 & 새로 고침 토큰

Microsoft 365 보안 센터 또는 준수 센터에서 ServiceNow 티켓을 만드는 경우 다음 데이터가 ServiceNow로 전송 됩니다.

* 티켓 만들기를 시작 하는 사용자 ID
* 작업 이름
* 작업 설명
* 우선 순위
* 기한
* 권장 사항 원본 (사용자 권장 사항 또는 Microsoft 권장 사항)
* 추천 범주 (장치, 데이터, 앱, Id, 인프라)

## <a name="connect-to-servicenow"></a>ServiceNow에 연결

[Microsoft 365 보안 센터에서 servicenow 티켓 만들기 및 추적](tickets-security-center.md) 으로 이동 하 여 servicenow에 연결 하는 방법을 알아보세요. Microsoft 365 준수 센터에서의 연결이 곧 제공 될 예정입니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>설치 검사 목록의 첫 번째 단계에서 오류가 표시 됩니다 (OAuth 만들기).

**오류 메시지**: 테이블의 범위 간 액세스 정책으로 인해 ' x_mioms_m365ticket ' 범위에서 ' oauth_entity '에 대 한 읽기 작업이 거부 되었습니다.

이 앱에서는 ServiceNow 인스턴스의 관리자가 OAuth 엔터티를 만들고 읽을 수 있다고 가정 합니다. 이 오류는 ServiceNow 인스턴스의 사용자 지정으로 인해 OAuth 엔터티를 만들거나 읽을 수 있는 사용자를 제한 하는 경우에 발생할 수 있습니다.

**ServiceNow에서는 사용자가 기본 기능을 유지 하는 것이 좋습니다.**

"응용 프로그램 레지스트리" 테이블 구성을 기본값으로 설정 합니다.

* Label = Application Registeries
* 이름 = oauth_entity
* 액세스 가능 = 모든 응용 프로그램 범위
* 읽을 수 있음 = 확인란 선택

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 보안 & 준수 커넥터에 대해 만들어진 OAuth 엔터티를 확인 하는 방법

ServiceNow에서 응용 프로그램 레지스트리 (**Menu > System OAuth > Application Registry**)로 이동 하 여 사용자가 만든 OAuth 엔터티를 할당 한 이름을 사용 하 여 찾습니다.

### <a name="logging-in-as-the-integration-user"></a>통합 사용자로 로그인

Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다. 개인 자격 증명은 사용 하지 마십시오.

1. ServiceNow의 인증 페이지로 이동 합니다.
2. 개인 자격 증명으로 로그인 한 경우 오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.
3. 설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.  
4. ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.
5. 설정 단계를 진행 합니다.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Microsoft 365 보안 & 준수 커넥터에 대 한 설치 검사 목록을 사용 하 여 만든 통합 사용자의 유효성을 검사 하는 방법

ServiceNow에서 사용자 **> 관리 > 사용자**로 이동 하 고 자신에 게 만든 통합 사용자를 지정한 이름으로 찾습니다.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>회사에서 Microsoft 365 보안 센터를 통해 ServiceNow에 연결 하지 못하도록 하는 single sign-on을 사용 하도록 설정 되어 있습니다.

회사에서 single sign-on을 사용 하도록 설정 하 고 오류가 수신 되거나 로그인이 실패 하면 두 솔루션 중 하나를 수행 합니다.

#### <a name="log-into-servicenow-as-the-integration-user"></a>통합 사용자로 ServiceNow 로그인

1. ServiceNow에서 인증 페이지로 다시 이동 합니다.
2. 오른쪽 위 모서리에서 링크 **하지 않음** 을 선택 합니다.
3. 설치 검사 목록에서 이전에 만든 통합 사용자로 ServiceNow에 로그인 합니다.  
4. ServiceNow 페이지에서 보안 + 준수 커넥터가 ServiceNow 계정에 연결할 수 있는지 여부를 묻는 **허용** 을 선택 합니다.
5. 설정 단계를 진행 합니다.

#### <a name="create-a-security-admin-user"></a>보안 관리자 사용자 만들기

1. Azure Active Directory에서 보안 관리자 권한을 가진 사용자를 만듭니다. 사용자는 설치 검사 목록에서 만든 통합 사용자와 이름 및 전자 메일 주소를 모두 사용 해야 합니다. 로그인 및 연결이 완료 되 면 보안 관리자 역할을 제거할 수 있습니다.
2. 이 사용자로 Microsoft 365 보안 센터에 로그인 하 고 설치 단계를 따릅니다.

### <a name="ip-filtering"></a>IP 필터링

IP 필터링을 사용 하도록 설정한 경우 IP 주소를 명시적으로 허용 해야 할 수 있습니다. ServiceNow에서 IP 범위를 허용 하는 방법에 대 한 자세한 내용은 [Ip 주소 액세스 제어](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 를 참조 하세요. 허용할 IP 주소 목록은 [AZURE IP 범위 및 서비스 태그-공용 클라우드](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 를 참조 하세요.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>설치가 완료 되었지만 티켓이 표시 되지 않으며 공유할 수 없음

설치 및 설치 단계가 완료 되었지만 홈 페이지에 ServiceNow 카드가 표시 되지 않고 Microsoft 보안 점수에서 ServiceNow을 공유할 수 없는 경우에는의 프로 비전 페이지 상태를 확인 https://security.microsoft.com/ticketProvisioning 합니다. **권한 부여** 를 선택 하 고 홈 페이지로 돌아갑니다. 카드를 표시 합니다.

## <a name="resources"></a>리소스

- [보안 센터에서 ServiceNow 티켓 관리](tickets-security-center.md)