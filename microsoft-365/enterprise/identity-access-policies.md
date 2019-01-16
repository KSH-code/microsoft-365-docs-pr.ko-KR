---
title: 일반적인 id 및 장치에 대 한 액세스 정책-Microsoft 365 Enterprise | Microsoft 문서
description: ID 및 장치 액세스 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870354"
---
# <a name="common-identity-and-device-access-policies"></a>일반 ID 및 장치 액세스 정책
이 문서에서는 온-프레미스 응용 프로그램을 비롯 하 여 Azure AD 응용 프로그램 프록시를 사용 하 여 게시 클라우드 서비스에 대 한 액세스를 보호 하는 것에 대 한 정책 권장 공통을 설명 합니다. 

이 설명서에서는 새로 프로 비전 된 환경에서 권장된 정책 배포 하는 방법에 설명 합니다. 별도 랩 환경에서 이러한 정책 설정을 이해 하 고 프로덕션 이전 및 프로덕션 환경에 배포를 준비 하기 전에 권장된 정책을 평가할 수 있습니다. 클라우드 전용 새로 구축 된 환경의 수 또는 하이브리드 합니다.  

## <a name="policy-set"></a>정책 설정 

다음 다이어그램에서는 권장 되는 정책 집합을 보여줍니다. 어떤 계층 보호를 적용 하는 각 정책 및 Pc 또는 전화 및 태블릿 장치의 두 범주에 정책이 적용 되는 여부를 표시 합니다. 또한 이러한 정책은 구성 된 위치를 나타냅니다.

![Id 및 장치에 대 한 액세스를 구성 하기 위한 일반적인 정책](../images/Identity_device_access_policies_byplan.png)


이 문서의 나머지 부분에서는 이러한 정책을 구성 하는 방법에 설명 합니다. 

장치가 의도 한 사용자를 소유 하는 보증에 대 한 Intune로 장치를 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다. 또한 장치 규정 준수 정책을 적용 하기 전에 Intune에 장치를 등록 해야 합니다.

제공 하려면 이러한 작업을 수행 하기 위해 시간,이 표에 나열 된 순서 대로 기본 정책을 구현 하는 것이 좋습니다. 그러나 중요 한 및 높은 규제 보호에 대 한 MFA 정책 언제 든 지 구현할 수 있습니다.


|보호 수준|Policies(정책)|추가 정보|
|:---------------|:-------|:----------------|
|**기준**|[로그인 위험 *보통* 또는 *높음* 때 MFA 필요](#require-mfa-based-on-sign-in-risk)| |
|        |[현대 인증을 지원 하지 않는 블록 클라이언트](#block-clients-that-dont-support-modern-authentication)|이러한 차단 하는 것이 중요 하므로 현대 인증을 사용 하지 않는 클라이언트 조건부 액세스 규칙을 무시할 수 있습니다.|
|        |[높은 위험 수준 사용자 암호를 변경 해야 합니다.](#high-risk-users-must-change-password)|강제로 사용자가 자신의 계정에 대 한 위험성이 높은 작업이 감지 되 면 하는 경우 로그인 할 때 자신의 암호를 변경 하려면|
|        |[응용 프로그램 보호 정책 정의](#define-app-protection-policies)|플랫폼 (iOS, Android, Windows) 당 하나의 정책입니다.|
|        |[승인 된 앱 필요](#require-approved-apps)|전화 및 태블릿에 대 한 모바일 응용 프로그램 보호 강제 적용|
|        |[장치 규정 준수 정책 정의](#define-device-compliance-policies)|각 플랫폼에 대 한 정책|
|        |[호환 Pc 필요](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Pc의 Intune 관리 강제 적용|
|**중요**|[로그인 위험 *낮음*, *보통* , *높음* 때 MFA 필요](#require-mfa-based-on-sign-in-risk)| |
|         |[준수 Pc *및* 모바일 장치 필요](#require-compliant-pcs-and-mobile-devices)|Pc 및 전화/태블릿 Intune 관리 강제 적용|
|**높은 규제**|[*항상* MFA 필요](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>사용자에 게 정책 할당
정책을 구성 하기 전에 각 계층 보호에 대 한를 사용 하는 Azure AD 그룹을 식별 합니다. 일반적으로 초기 보호 조직의 모든 사용자에 게에 적용 됩니다. 초기 계획 및 중요 한 보호를 모두 포함 된 사용자에 적용 된 모든 기본 정책 및 중요 한 정책을 갖습니다. 보호 누적 이며 가장 제한적인 정책이 적용 됩니다. 

조건부 액세스 제외에 대 한 Azure AD 그룹을 만들려면는 것이 좋습니다. "제외" 아래에서 조건부 액세스 규칙의 모든이 그룹을 추가 합니다. 이렇게 하면 액세스 문제를 해결 하는 동안 사용자에 대 한 액세스를 제공 하는 방법입니다. 임시 솔루션만으로 이러한 것이 좋습니다. 변경 내용에 대 한이 그룹을 모니터링 하 고 제외 그룹은 의도 한 대로 사용 되 고 있는지 확인 합니다. 

다음 다이어그램에서는 사용자 할당 및 제외 항목의 예를 제공합니다.

![예제 사용자 할당 및 MFA 규칙에 대 한 제외](../images/identity-access-policies-assignment.png)

그림의 "위쪽 비밀 프로젝트 X 팀" MFA *항상*필요로 하는 조건부 액세스 정책을 할당 됩니다. 사용자에 게 보다 높은 수준의 보호를 적용할 때 적절히를 수 있습니다. 이 프로젝트 팀의 구성원 매우 규제 된 콘텐츠를 표시 되지 않음 하는 경우에 로그온 할 때마다 두 형태의 인증을 제공 해야 합니다.  

Office 365 그룹으로 이러한 지침의 일부로 만들어진 모든 Azure AD 그룹을 만들어야 합니다. 이 SharePoint Online에서 문서를 보호 하는 경우에 특히 Azure 정보 보호 (AIP)의 배포에 대 한 중요 합니다.

![Office 365 그룹을 만들기 위한 화면 캡처](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>로그인 위험에 따라 MFA 필요
MFA 요구를 하기 전에 먼저는 Identity 보호 MFA 등록 정책을 사용 하 여 MFA에 대 한 사용자를 등록 합니다. 사용자는 등록 한 후에 로그인에 대 한 MFA를 적용할 수 있습니다. [필수 구성 요소 작업](identity-access-prerequisites.md) MFA 통해 등록 하는 모든 사용자를 포함 합니다.

새 조건부 액세스 정책을 만들려면 

1. [Azure 포털](https://portal.azure.com)이동 하 고 사용자의 자격 증명을 사용 하 여 로그인 합니다. 했을 때 성공적으로 로그인 후, Azure 대시보드를 참조 합니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

![기준 CA 정책 만들기](./media/secure-email/CA-EXO-policy-1.png)

 다음 표에서이 정책을 구현 하기 위한 조건부 액세스 정책 설정을 설명 합니다.

**할당**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|사용자 및 그룹|포함|사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작|
||제외|예외 보안 그룹; 서비스 계정(앱 ID)|필요에 따라 임시 기준 수정 하는 멤버 자격|
|클라우드 앱|포함|이 규칙을 적용 하려면 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택합니다||
|조건|구성됨|예|사용자 환경 및 요구에 맞게 구성|
|로그인 위험|위험 수준||다음 표에서의 지침을 참조 하십시오|

**로그인 위험**

대상으로 하는 보호 수준에 따라 설정을 적용 합니다.

|속성|보호 수준|값|참고|
|:---|:---------|:-----|:----|
|위험 수준|기준|높음, 중간|모두 선택|
| |중요|높음, 보통, 낮음|세 항목 모두 선택|
| |높은 규제| |모든 옵션을 항상 MFA을 적용 하도록 선택 하지 않은 상태로 유지|

**액세스 제어**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|권한 부여|액세스 허가|True|선택|
||MFA 필요|True|Check|
||규격으로 표시 하는 장치 필요|False||
||하이브리드 Azure AD 가입 장치 필요|False||
||승인 된 클라이언트 응용 프로그램을 필요|False||
||선택된 컨트롤이 모두 필요함|True|선택|

> [!NOTE]
> **** 선택 하 여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하는 것이 좋습니다.



## <a name="block-clients-that-dont-support-modern-authentication"></a>현대 인증을 지원 하지 않는 블록 클라이언트
1. [Azure 포털](https://portal.azure.com)이동 하 고 사용자의 자격 증명을 사용 하 여 로그인 합니다. 했을 때 성공적으로 로그인 후, Azure 대시보드를 참조 합니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

다음 표에서이 정책을 구현 하기 위한 조건부 액세스 정책 설정을 설명 합니다.

**할당**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|사용자 및 그룹|포함|사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작|
||제외|예외 보안 그룹; 서비스 계정(앱 ID)|필요에 따라 일시적으로 수정한 멤버 자격|
|클라우드 앱|포함|이 규칙을 적용 하려면 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택합니다||
|조건|구성됨|예|클라이언트 응용 프로그램 구성|
|클라이언트 응용 프로그램|구성됨|예|모바일 응용 프로그램 및 데스크톱 클라이언트를 다른 클라이언트 (두 항목 모두 선택)|

**액세스 제어**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|권한 부여|액세스 차단|True|선택|
||MFA 필요|False||
||규격으로 표시 하는 장치 필요|False||
||하이브리드 Azure AD 가입 장치 필요|False||
||승인 된 클라이언트 응용 프로그램을 필요|False||
||선택된 컨트롤이 모두 필요함|True|선택|

> [!NOTE]
> **** 선택 하 여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하는 것이 좋습니다.



## <a name="high-risk-users-must-change-password"></a>높은 위험 수준 사용자 암호를 변경 해야 합니다.
모든 위험성이 높은 사용자의 손상 된 계정이 있는지 확인 하려면를 강제로 수행 하도록 암호 변경에 서명할 때, 다음과 같은 정책을 적용 해야 합니다.

에 로그인 하는 [Microsoft Azure 포털 (http://portal.azure.com) ](http://portal.azure.com/) 관리자 자격 증명으로 다음으로 이동 하 고 **Azure AD Id 보호 > 사용자 위험 정책**합니다.

**할당**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|사용자|포함|모든 사용자|선택|
||제외|없음||
|조건|사용자 위험|높은|선택|

**컨트롤**

| 유형 | 속성 | 값                  | 참고 |
|:-----|:-----------|:------------------------|:------|
|      | 액세스     | 액세스 허용            | True  |
|      | 액세스     | 암호 변경 필요 | True  |

**검토:** 는 적용 되지 않음

> [!NOTE]
> **** 선택 하 여이 정책을 사용 하도록 설정 해야 합니다. 또한 정책을 테스트할 [경우에 어떻게](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 고려

## <a name="define-app-protection-policies"></a>응용 프로그램 보호 정책 정의
허용 되는 앱 app 보호 정책을 정의 하 고 조직의 데이터에 적용할 수 있는 작업은 키를 누릅니다. Azure 포털 내에서 보호 정책을 Intune 응용 프로그램을 만듭니다. 

각 플랫폼에 대 한 정책을 만듭니다.
- iOS
- Android
- Windows 10

새 응용 프로그램 보호 정책을 만들려면 관리 자격 증명을 사용 하 여 Microsoft Azure 포털에 로그인 하 고 다음을 이동 **모바일 앱 > 앱 보호 정책**합니다. **정책 추가**선택 합니다.

IOS와 Android 간의 정책 옵션은 app 보호에 약간의 차이점이 있습니다. 특히 for Android는 정책 아래 있습니다. 다른 정책에 대 한 지침으로 사용 합니다.

앱의 권장된 목록에는 다음이 포함 됩니다.
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

다음 표에서 권장된 설정에 설명 합니다.

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|데이터 재배치|Android 백업 차단|예|iOS의 경우 iTunes 및 iCloud를 명시적으로 호출|
||앱이 다른 앱으로 데이터를 전송하도록 허용|정책 관리 앱||
||앱에서 다른 앱의 데이터를 받을 수 있도록 허용|정책 관리 앱||
||"다른 이름으로 저장" 차단|예||
||회사 데이터를 저장할 수 있는 저장소 서비스 선택|SharePoint 비즈니스용 OneDrive||
||다른 앱에서 잘라내기, 복사 및 붙여넣기 제한|정책에 붙여넣기와 함께 응용 프로그램 관리||
||Managed Browser에서 표시할 수 있는 웹 콘텐츠 제한|아니요||
||앱 데이터 암호화|예|iOS의 경우 옵션 선택: 장치가 잠긴 경우|
||장치를 사용할 때 app 암호화를 사용 하지 않도록 설정|예|이중 암호화 되지 않도록 하려면이 설정을 사용 하지 않도록 설정|
||연락처 동기화 사용 안 함|아니요||
||인쇄를 사용 하지 않도록 설정|아니요||
|액세스|액세스 시 PIN 필요|예||
||유형 선택|숫자||
||단순한 PIN 허용|아니요||
||PIN 길이|6||
||PIN 대신 지문 허용|예||
||장치 PIN 관리 되는 경우 PIN app를 사용 하지 않도록 설정|예||
||액세스에 대 한 회사 자격 증명을 요구 합니다.|아니요||
||액세스 요구 사항을 다시 확인할 시간(분)|30||
||화면 캡처 및 Android Assistant 차단|아니요|iOS의 경우 이 옵션을 사용할 수 없음|
|로그인 보안 요구 사항|최대 PIN 시도|5|Pin을 다시 설정|
||오프라인 유예 기간|720|액세스 차단|
||앱 데이터가 초기화되기 전의 오프라인 간격(일)|90|데이터를 초기화 합니다.|
||Jailbroken/루트가 아닌 장치| |데이터를 초기화 합니다.|

완료 되 면 "만들기"를 선택 해야 합니다. 위의 단계를 반복 하 고 iOS 선택한 플랫폼 (드롭다운)으로 바꿉니다. 두 응용 프로그램 정책 그렇기 때문에, 따라서 정책을 만들면 다음 그룹 정책에 할당 하 고 배포 합니다.

정책을 편집 하 여 이러한 정책을 사용자에 게 할당 참조 하십시오 [만들고 app 보호 정책에 할당 하는 방법](https://docs.microsoft.com/intune/app-protection-policies)입니다. 

## <a name="require-approved-apps"></a>승인 된 앱 필요
승인 된 앱을 요구 합니다.

1. [Azure 포털](https://portal.azure.com)이동 하 고 사용자의 자격 증명을 사용 하 여 로그인 합니다. 했을 때 성공적으로 로그인 후, Azure 대시보드를 참조 합니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 선택 합니다.

8. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

9. **클라이언트 응용 프로그램을 승인 필요**를 선택, **액세스 권한 부여를**선택 합니다. 여러 컨트롤에 대 한 **선택된 된 컨트롤 필요**를 선택 하 고 **선택**를 선택 합니다. 

10. **Create(만들기)** 를 선택합니다.

## <a name="define-device-compliance-policies"></a>장치 준수 정책 정의

장치 준수 정책에는 장치 규격으로 표시 하기 위해 준수 해야 하는 요구 사항을 정의 합니다. Azure 포털 내에서 규정 준수 정책 Intune 장치를 만듭니다. 

각 플랫폼에 대 한 정책을 만듭니다.
- Android
- Android enterprise
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1 및 이상
- Windows 10 이상

장치 정책 준수를 만들려면 관리 자격 증명을 사용 하 여 Microsoft Azure 포털에 로그인 하 고 다음 이동 **Intune > 장치 준수**합니다. **정책 만들기를**선택 합니다.

Windows 10은 다음 설정은 사용 하는 것이 좋습니다.

**장치 상태: Windows 상태 증명 서비스 평가 규칙**

|속성|값|참고|
|:---------|:-----|:----|
|BitLocker 필요|필수||
|장치에서 사용 하도록 설정 하려면 보안 부팅 필요|필수||
|코드 무결성 필요|필수||


**장치 속성**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|운영 체제 버전|모두|구성되지 않음||

모든 것으로 간주 하는 위의 정책 배포에 대 한 사용자 그룹에 자신이 대상을 지정 해야 합니다. 이 정책을 만들어 수행할 수 있습니다 (저장할 때) (추가와 같은 수준) **정책** 섹션에서 **관리 배포** 를 선택 하 여 이상입니다.

**시스템 보안**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|암호|모바일 장치 잠금을 해제 하려면 암호 필요|필수||
||단순 암호|Block||
||암호 유형|기본 장치||
||최소 암호 길이|6||
||암호를 입력 하기 전에 비활성 최대 시간 (분)|15 |Android 버전 4.0 이상과이 설정이 지원 또는 KNOX 4.0 이상. IOS 장치에 대 한 것은 지원 되는 iOS 8.0에 대 한 및 위에|
||암호 만료(일)|41||
||재사용을 방지 하기 위해 이전 암호의 수|5||
||암호를 묻는 (모바일 및 Holographic) 유휴 상태에서 장치를 반환 하는 경우|필수|Windows 10에 대 한 사용 가능 하 고 이상|
|암호화|장치에서 데이터 저장소의 암호화|필수||
|장치 보안|방화벽|필수||
||바이러스 검사|필수||
||스파이웨어 방지|필수|이 설정은 필요한 Windows 보안 센터에 등록 하는 스파이웨어 방지 솔루션|
|Defender|Windows Defender 맬웨어 방지|필수||
||Windows Defender 맬웨어 방지 최소 버전||Windows 10 바탕 화면에 대해서만 지원 합니다. Microsoft는 권장 버전 보다 최신 버전에서 뒤에 5 개|
||Windows Defender 맬웨어 방지 서명을 최신 상태로 유지|필수||
||끕니다|필수|Windows 10 데스크톱에 대해서만 지원|

**Windows Defender ATP**

|유형|속성|값|참고|
|:---|:---------|:-----|:----|
|Windows Defender 고급 위협 보호 규칙|또는 그 컴퓨터 위험 점수 아래에서 되도록 장치 필요|보통||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>호환 Pc (하지만 규격이 아닙니다. 전화 및 태블릿) 필요
호환 Pc를 요구 하는 정책의 추가 하기 전에 Intune에 관리를 위한 장치를 등록 해야 합니다. 장치가 의도 한 사용자를 소유 하는 보증에 대 한 Intune로 장치를 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다. 

호환 Pc를 요구 합니다.

1. [Azure 포털](https://portal.azure.com)이동 하 고 사용자의 자격 증명을 사용 하 여 로그인 합니다. 했을 때 성공적으로 로그인 후, Azure 대시보드를 참조 합니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 선택 합니다.

8. 호환 Pc 하지만 따르지 않는 전화와 태블릿을 요구 하려면 **조건** 및 **장치 플랫폼**을 선택 합니다. **장치 플랫폼을 선택 합니다.** 를 선택 하 고 **Windows** 및 **macOS**을 선택 합니다.

9. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

10. **액세스 권한 부여를**선택, **규격이 것으로 표시 하는 장치 필요**를 선택 합니다. 여러 컨트롤에 대 한 **필요 선택한 모든 컨트롤**을 선택 하 고 **선택**를 선택 합니다. 

11. **Create(만들기)** 를 선택합니다.

목표를 규격 Pc *및* 모바일 장치에 필요한 경우에 플랫폼을 선택 하지 마십시오. 이 모든 장치에 대 한 규정 준수를 적용합니다. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>준수 Pc *및* 모바일 장치 필요

모든 장치에 대 한 규정 준수를 요구 합니다.

1. [Azure 포털](https://portal.azure.com)이동 하 고 사용자의 자격 증명을 사용 하 여 로그인 합니다. 했을 때 성공적으로 로그인 후, Azure 대시보드를 참조 합니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱을 선택 합니다.** 를 선택, **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예, Office 365 Exchange Online을 선택 합니다. **선택** 하 고 **완료**를 선택 합니다.

8. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

9. **액세스 권한 부여를**선택, **규격이 것으로 표시 하는 장치 필요**를 선택 합니다. 여러 컨트롤에 대 한 **필요 선택한 모든 컨트롤**을 선택 하 고 **선택**를 선택 합니다. 

10. **Create(만들기)** 를 선택합니다.

이 정책을 만들 때에 플랫폼을 선택 하지 마십시오. 호환 장치를 적용합니다.




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>다음 단계

[메일을 보호하기 위한 정책 권장 사항에 대해 알아보기](secure-email-recommended-policies.md)
