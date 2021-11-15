---
title: 비즈니스용 요금제의 보안 Microsoft 365 10가지 방법
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 랜섬웨어, 피싱 및 악의적인 첨부 파일을 포함하여 사이버 위협으로부터 비즈니스 전자 메일 및 데이터를 보호하는 방법
ms.openlocfilehash: 1923f4a13e2971cf58c83ccfb1444b7446133566
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962726"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>비즈니스용 요금제의 보안 Microsoft 365 10가지 방법

Microsoft의 비즈니스 계획 중 하나를 사용하는 중소 규모 조직인 경우 조직 유형이 사이버 범죄자 및 해커의 대상이 될 경우 이 문서의 지침을 사용하여 조직의 보안을 강화하세요. 이 지침은 조직에서 Harvard Kennedy School [Cybersecurity Campaign Handbook에](https://go.microsoft.com/fwlink/p/?linkid=2015598)설명된 목표를 달성하는 데 도움이 됩니다.

서비스 계획에 적용되는 다음 표에 나열된 작업을 완료하는 것이 좋습니다.

|*숫자*|작업|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[다단계 인증 설정](secure-your-business-data.md#setup)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[사용자 교육](secure-your-business-data.md#train)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3 |[전용 관리자 계정 사용](secure-your-business-data.md#admin)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[메일의 맬웨어에 대한 보호 수준 높이기](secure-your-business-data.md#malware)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[랜섬웨어로부터 보호](secure-your-business-data.md#ransomware)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[전자 메일에 대한 자동 전달 중지](secure-your-business-data.md#forwarding)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[메시지 Office 사용](secure-your-business-data.md#encryption)||![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[피싱 공격으로부터 전자 메일 보호](secure-your-business-data.md#phishing)||![포함.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[첨부 파일을 통해 악의적인 첨부 파일 및 금고 보호](secure-your-business-data.md#atp)||![포함](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[링크로 피싱 금고 보호](secure-your-business-data.md#phishingatp)||![포함](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Microsoft Business Premium이 있는 경우 보안을 설정하고 안전하게 공동 작업을 시작하는 가장 빠른 방법은 [소규모 기업 및 캠페인을 위한 Microsoft 365](../../campaigns/index.md) 라이브러리의 지침을 따르는 것입니다. 이 지침은 Microsoft Defending Democracy 팀과 협력하여 정교한 해커가 시작한 사이버 위협으로부터 모든 중소기업 고객을 보호하기 위해 개발되었습니다.

시작하기 전에 보안 [센터에서 Microsoft 365](../../security/defender/microsoft-secure-score.md) 보안 점수를 Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">합니다.</a> 중앙 집중식 대시보드에서 ID, 데이터, 앱, 장치 및 인프라에 대한 Microsoft 365 모니터링하고 개선할 수 있습니다. 권장 보안 기능을 구성하거나, 보안 관련 작업(예: 보고서 보기)을 수행하거나, 타사 응용 프로그램 또는 소프트웨어를 사용하여 권장 사항을 해결하기 위한 포인트가 부여됩니다. 더 광범위한 Microsoft 제품 및 서비스 집합에 대한 추가 통찰력과 가시성을 통해 조직의 보안 상태 보고를 확신할 수 있습니다.

![Microsoft 보안 점수 스크린샷.](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: 다단계 인증 설정
<a name="setup"> </a>

다단계 인증을 사용하는 것은 조직의 보안을 강화하는 가장 쉽고 효과적인 방법 중 하나입니다. 소리보다 쉽습니다. 로그인할 때 다단계 인증을 사용하면 휴대폰에서 코드를 입력하여 앱에 액세스할 수 Microsoft 365. 이렇게 하면 해커가 암호를 알고 있는 경우 이를 인계하지 못하게 할 수 있습니다. 다단계 인증을 2단계 인증이라고도 합니다. 개인은 대부분의 계정(예: Google 또는 Microsoft 계정에)에 2단계 인증을 쉽게 추가할 수 있습니다. 다음은 개인 [Microsoft 계정에 2단계 인증을 추가하는 방법입니다.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

사용자를 Microsoft 365 기업의 경우 사용자가 다단계 인증을 사용하여 로그인해야 하는 설정을 추가합니다. 이 변경을 하면 다음에 로그인할 때 2단계 인증을 위해 휴대폰을 설정하라는 메시지가 표시됩니다.
MFA를 설정하는 방법과 사용자가 설정 완료하는 방법에 대한 교육 비디오를 보고 [MFA](../../business-video/turn-on-mfa.md) 및 사용자 설정 을 [참조합니다.](../../business-video/set-up-mfa.md)

다단계 인증을 설정하기 위해 보안 기본값을 켜야 합니다.

대부분의 조직에서 보안 기본값은 적절한 수준의 추가 로그인 보안을 제공합니다. 자세한 내용은 [보안 기본값이란?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.

신규 구독이면 보안 기본값이 이미 자동으로 설정되었을 수 있습니다.

Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.

1. 전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.
2. 왼쪽 탐색 메뉴에서 **모두 표시** 를 선택하고 **관리 센터** 에서 **Azure Active Directory** 를 선택합니다.
3. **Azure Active Directory 관리 센터** 에서 **Azure Active Directory** > **속성** 을 선택합니다.
4. 페이지 하단에서 **보안 기본값 관리** 를 선택합니다.
5. 보안 기본값을 사용하도록 설정하려면 **예** 를 선택하고 사용하지 않도록 설정하려면 **아니요** 를 선택한 다음 **저장** 을 선택합니다.

조직에 대한 다단계 인증을 설정한 후에는 사용자가 장치에서 2단계 인증을 설정해야 합니다. 자세한 내용은 [Set up 2-step verification for Microsoft 365.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

전체 세부 정보 및 전체 권장 사항은 사용자에 대해 [다단계 인증 설정 을 참조하세요.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: 사용자 교육
<a name="train"> </a>

하버드 Kennedy [학교](https://go.microsoft.com/fwlink/p/?linkid=2015598) 사이버 보안 캠페인 핸드북은 피싱 공격을 식별하기 위한 교육을 포함하여 조직 내에서 강력한 보안 인식 문화를 설정하기 위한 훌륭한 지침을 제공합니다.

이 지침 외에도 사용자는 이 문서에 설명된 작업을 수행하여 해커와 맬웨어로부터 계정 및 장치를 [보호하는 것이 좋습니다.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) 이러한 작업은 다음과 같습니다.

- 강력한 암호 사용

- 장치 보호

- Windows 10 및 Mac PC에서 보안 기능 사용

또한 다음 문서에서 권장하는 작업을 수행하여 사용자가 개인 전자 메일 계정을 보호하는 것이 좋습니다.

- [Outlook.com 전자 메일 계정 보호](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2단계 인증을 사용하여 Gmail 계정 보호](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: 전용 관리자 계정 사용
<a name="admin"> </a>

사용자 환경 관리에 사용하는 관리 계정에는 Microsoft 365 권한이 포함됩니다. 이는 해커와 사이버 범죄자에 대한 중요한 대상입니다. 관리에만 관리자 계정을 사용하세요. 관리자는 관리가 아닌 일반 사용에 대해 별도의 사용자 계정이 필요하며, 필요한 경우 해당 작업 기능과 관련된 작업을 완료하는 데만 관리 계정을 사용해야 합니다. 추가 권장 사항:

- 다단계 인증을 위해 관리자 계정도 설정해야 합니다.

- 관리자 계정을 사용하려면 먼저 개인 전자 메일 계정을 포함하여 관련 없는 모든 브라우저 세션 및 앱을 닫습니다.

- 관리 작업을 완료한 후 브라우저 세션에서 로그아웃해야 합니다.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: 메일의 맬웨어에 대한 보호 수준 높이기
<a name="malware"> </a>

사용자 Microsoft 365 환경에는 맬웨어에 대한 보호가 포함되어 있지만 맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다. 전자 메일에서 맬웨어 보호를 범프하거나 짧은 교육 비디오를 [보거나](../../business-video/anti-malware.md)다음 단계를 완료합니다.

1. 으로 <https://protection.office.com> 이동하여 관리자 계정 자격 증명으로 로그인합니다.

2. 보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서  정책 맬웨어 방지 \> **를 선택 합니다.**

3. 기본 정책을 두 번 클릭하여 이 회사 전체 정책을 편집합니다.

4. **설정** 을 선택합니다.

5. 일반 **첨부 파일 형식 필터에서** 를 **선택합니다.** 차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다. 필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.

6. 저장을 **선택합니다.**

자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](../../security/office-365-security/anti-malware-protection.md)

## <a name="5-protect-against-ransomware"></a>5: 랜섬웨어로부터 보호
<a name="ransomware"> </a>

랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다. 그런 다음 데이터에 대한 액세스 대가로 일반적으로 가상화 형식의 "금전"을 요청하여 피해자로부터 돈을 유출하려고 시도합니다.

랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단하거나 전자 메일에서 이러한 첨부 파일을 받는 사용자에게 경고하는 메일 흐름 규칙을 하나 이상 만들어 랜섬웨어로부터 보호할 수 있습니다. 좋은 시작 지점은 다음 두 규칙을 만드는 것입니다.

- 매크로가 포함된 Office 파일을 열기 전에 사용자에게 경고합니다. 매크로 내에서 랜섬웨어를 숨길 수 있으므로 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.

- 랜섬웨어 또는 기타 악성 코드를 포함할 수 있는 파일 형식을 차단합니다. 아래 표에 나열된 실행 가능한 일반적인 목록으로 시작해보겠습니다. 조직에서 이러한 실행 형식을 사용하는 경우 이러한 유형이 전자 메일로 전송될 것으로 예상되는 경우 이전 규칙에 추가합니다(사용자에게 경고).

메일 전송 규칙을 만들거나 짧은 교육 비디오를 [보거나](../../business-video/prevent-ransom-in-email.md)다음 단계를 완료합니다.

1. [Exchange 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2059104)로 이동합니다.

2. 메일 **흐름 범주에서** 규칙을 **선택합니다.**

3. **+** 를 선택한 다음 **새 규칙 만들기 를 선택합니다.**

4. 전체 옵션 집합을 확인하려면 대화 상자 아래쪽에서 ****를 선택합니다.

5. 각 규칙에 대해 다음 표의 설정을 적용합니다. 나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.

6. **저장** 을 선택합니다.
    
| 설정 | 파일 첨부 파일을 열기 전에 Office 경고 | 랜섬웨어 또는 기타 악성 코드를 포함할 수 있는 파일 형식 차단 |
|:-----|:-----|:-----|
|이름  <br/> |랜섬웨어 방지 규칙: 사용자에게 경고  <br/> |랜섬웨어 방지 규칙: 파일 형식 차단  <br/> |
|이 경우 이 규칙을 적용합니다. . .  <br/> |모든 첨부 파일 . . . 파일 확장명은 을 일치합니다. . .  <br/> |모든 첨부 파일 . . . 파일 확장명은 을 일치합니다. . .  <br/> |
|단어 또는 구 지정  <br/> |다음 파일 형식을 추가합니다.  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |다음 파일 형식을 추가합니다.  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|다음을 합니다. . .  <br/> |고지서 사전 준비  <br/> |메시지를 차단합니다. . . 메시지를 거부하고 설명 포함  <br/> |
|메시지 텍스트 제공  <br/> |파일에 악성 코드가 포함되어 있을 수 있으며 보낸 사람이 안전하지 않다는 것을 알지 못하기 때문에 이러한 유형의 파일을 예상하지 않은 경우 열지 않습니다.  <br/> ||
   
> [!TIP]
> 4단계의 맬웨어 방지 목록에 차단할 파일을 추가할 [수 있습니다.](#4-raise-the-level-of-protection-against-malware-in-mail)

자세한 내용은 다음 항목을 참조하세요.

- [랜섬웨어: 위험을 줄이는 방법](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [사용자 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: 전자 메일에 대한 자동 전달 중지
<a name="forwarding"> </a>

사용자의 사서함에 액세스할 수 있는 해커는 자동으로 전자 메일을 전달하도록 사서함을 구성하여 메일을 유출할 수 있습니다. 이는 사용자의 인식 없이도 발생될 수 있습니다. 메일 흐름 규칙을 구성하여 이러한 문제를 방지할 수 있습니다.

메일 전송 규칙을 만들 수 있습니다.

1. [Exchange 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2059104)로 이동합니다.

2. 메일 **흐름 범주에서** 규칙을 **선택합니다.**

3. **+** 를 선택한 다음 **새 규칙 만들기 를 선택합니다.**

4. 전체 **옵션 집합을** 확인하려면 대화 상자 아래쪽에서 다른 옵션을 선택합니다.

5. 다음 표의 설정을 적용합니다. 나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.

6. **저장** 을 선택합니다.

|설정|외부 도메인으로 자동 전달 전자 메일 거부|
|---|---|
|이름|외부 도메인으로 전자 메일 자동 전달 방지|
|다음의 경우 이 규칙을 적용합니다.|보낸 사람 입니다. . . 은 외부/내부입니다. . . 조직 내부|
|조건 추가|받는 사람 입니다. . . 은 외부/내부입니다. . . 조직 외부|
|조건 추가|메시지 속성 입니다. . . 메시지 유형 을 포함합니다. . . 자동 전달|
|다음 작업을 합니다.|메시지를 차단합니다. . . 메시지를 거부하고 설명을 포함합니다.|
|메시지 텍스트 제공|보안상의 이유로 이 조직 외부에서 전자 메일을 자동 전달할 수 없습니다.|

## <a name="7-use-office-message-encryption"></a>7: 메시지 Office 사용
<a name="encryption"> </a>

Office 메시지 암호화는 메시지 암호화에 Microsoft 365. 이미 설정되어 있습니다. 메시지 Office 사용하여 조직 내부 및 외부 사용자 간에 암호화된 전자 메일 메시지를 보내고 받을 수 있습니다. Office 365 메시지 암호화는 Outlook.com, Yahoo!, Gmail 및 기타 전자 메일 서비스와 연동됩니다. 전자 메일 메시지 암호화를 사용하면 받는 사람만 메시지 콘텐츠를 볼 수 있습니다.

Office 메시지 암호화는 메일을 보낼 때 다음과 같은 두 가지 보호 옵션을 제공합니다.

- 전달하지 않습니다.

- 암호화

조직에서 기밀과 같은 레이블을 전자 메일에 적용하는 추가 옵션을 구성한 것일 수 있습니다.

### <a name="to-send-protected-email"></a>보호된 전자 메일을 보내기 위해

PC용 Outlook **메일에서 옵션을** 선택한 다음 사용 **권한을 선택합니다.**

![전자 메일 메시지 암호화를 Outlook.](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

in Outlook.com, select **Protect** in the email. 기본 보호는 **전달 금지입니다.** 암호화를 위해 이 옵션을 변경하려면 **사용 권한 암호화 변경 을** \> **선택합니다.**

![Outlook.com의 전자 메일 메시지 암호화.](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>암호화된 전자 메일을 받으면

받는 사람이 Outlook 2013 또는 Outlook 2016 Microsoft 전자 메일 계정이 있는 경우 읽기 창에 항목의 제한된 사용 권한에 대한 경고가 표시됩니다. 메시지를 연 후 받는 사람은 다른 메시지와 마찬가지로 메시지를 볼 수 있습니다.

받는 사람이 Gmail 또는 Yahoo와 같은 다른 전자 메일 클라이언트 또는 전자 메일 계정을 사용하는 경우 로그인하여 전자 메일 메시지를 읽거나 일회용 암호를 요청하여 웹 브라우저에서 메시지를 볼 수 있는 링크가 표시됩니다. 사용자가 전자 메일을 받지 못하면 스팸 또는 정크 폴더를 확인하게 합니다.

자세한 내용은 PC용 에서 암호화된 메시지 보내기, Outlook [회신을 참조하세요.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. 피싱 공격으로부터 전자 메일 보호
<a name="phishing"> </a>

Microsoft 365 사용자 지정 도메인을 하나 이상 구성한 경우 대상 피싱 방지 보호 기능을 구성할 수 있습니다. Microsoft Defender의 일부인 피싱 방지 Office 365 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호할 수 있습니다. 사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.

가장 중요한 사용자와 사용자 지정 도메인을 보호하는 정책을 만들어 이 보호를 시작하는 것이 좋습니다.

![Microsoft Defender에서 피싱 방지 정책 Office 365.](../../media/security-and-compliance-center.png)

사용자용 Defender에서 피싱 방지 정책을 Office 365 짧은 교육 [](../../business-video/setup-anti-phishing.md)비디오를 보거나 다음 단계를 완료합니다.

1. <https://protection.office.com>로 이동합니다.

2. 보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택합니다.**

3. 정책 페이지에서 피싱 **방지 를 선택합니다.**

4. 피싱 방지 페이지에서 **+ 만들기를 선택합니다.** 피싱 방지 정책을 정의하는 단계를 안내하는 마법사가 실행됩니다.

5. 아래 차트에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다. 자세한 [내용은 Microsoft Defender의](../../security/office-365-security/set-up-anti-phishing-policies.md) 피싱 방지 정책에 대한 자세한 Office 365 옵션을 참조하세요.

6. 설정을 검토한 후 이  정책 만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인 및 가장 중요한 캠페인 직원|
|설명|가장 중요한 직원과 도메인이 가장되지 않도록 합니다.|
|보호할 사용자를 추가|+ **조건 추가를 선택합니다. 받는 사람은 입니다.** 사용자 이름을 입력하거나 후보, 캠페인 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다. 가장으로부터 보호할 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.|
|보호할 도메인을 추가|+ **조건 추가를 선택하고 받는 사람 도메인은 입니다.** 사용자 지정 도메인을 정의한 경우 Microsoft 365 사용자 지정 도메인을 입력합니다. 두 개 이상의 도메인을 입력할 수 있습니다.|
|작업 선택|가장된 사용자가 전자 메일을 보낸 경우: **메시지를** 다른 전자 메일 주소로 리디렉션을 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 securityadmin@contoso.com. <br/> 가장된 도메인에서 전자 메일을 보낸 경우: 메시지 **검역을 선택합니다.**|
|사서함 인텔리전스|새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.|
|신뢰할 수 있는 발신자와 도메인 추가|해당 예제에서는 어떠한 재정의도 정의하지 않아야 합니다.|
|적용 대상|**받는 사람의 도메인이 다음과 같음** 을 선택합니다. **이러한 항목 모두** 아래에서 **선택** 을 선택합니다. **+ 추가** 를 선택합니다. 도메인 이름 옆의 확인란을 선택하고(예 contoso.com 목록에서 추가를 **선택합니다.** **완료** 를 선택합니다.|
|

자세한 내용은 [Set up anti-phishing policies in Defender for Office 365.](../../security/office-365-security/configure-atp-anti-phishing-policies.md)

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: 첨부 파일을 통해 악의적인 첨부 파일 및 금고 보호
<a name="atp"> </a>

문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다. 전자 메일 메시지를 확인하여 첨부 파일이 안전한지 악성인지를 항상 쉽게 알 수 있는 것은 아닙니다. Microsoft Defender for Office 365 첨부 금고 포함하지만 기본적으로 이 보호는 켜져 있지 않습니다. 이 보호를 사용하 여 시작 하는 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft Teams.

첨부 파일 금고 만들거나 짧은 교육 비디오를 [보거나](../../business-video/safe-attachments.md)다음 단계를 완료합니다.

1. 으로 <https://protection.office.com> 이동하여 관리자 계정으로 로그인합니다.

2. 보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택합니다.**

3. 정책 페이지에서 첨부 **파일 금고 선택합니다.**

4. 금고 첨부 파일 페이지에서 SharePoint, OneDrive 및 Microsoft Teams ATP 켜기 확인란을 선택하여 이 보호를 **광범위하게 적용합니다.**

5. 새 **+** 정책을 만들 수 있습니다.

6. 다음 표의 설정을 적용합니다.

7. 설정을 검토한 후 이  정책 만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.|
|설명|감지된 맬웨어로 현재 및 미래의 전자 메일 및 첨부 파일을 차단합니다.|
|첨부 파일 알 수 없는 맬웨어 응답 저장|차단 - 감지된 맬웨어로 현재 및 미래의 전자 메일 **및 첨부 파일을 차단을 선택합니다.**|
|검색 시 첨부 파일 리디렉션|리디렉션 사용(이 상자 선택) <br/> 관리자 계정 또는 사서함 설정을 입력하여 검지합니다. <br/> 첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자 선택).|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|
|

자세한 내용은 [Set up anti-phishing policies in Defender for Office 365.](../../security/office-365-security/configure-atp-anti-phishing-policies.md)

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: 링크로 피싱 금고 보호
<a name="phishingatp"> </a>

해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다. 금고 Microsoft Defender의 일부인 Office 365 링크는 전자 메일 메시지 및 문서의 웹 주소(URL)에 대한 클릭 시간 확인을 제공하여 조직을 보호하는 Office 있습니다. 보호는 링크 정책을 통해 금고 정의됩니다.

다음을 하는 것이 좋습니다.

- 보호를 강화하도록 기본 정책을 수정합니다.

- 도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.

링크로 금고 짧은 교육 비디오를 [보거나](../../business-video/safe-links.md)다음 단계를 완료합니다.

1. 으로 <https://protection.office.com> 이동하여 관리자 계정으로 로그인합니다.

2. 보안 및 & 센터의 왼쪽 탐색 창에 있는 **위협** 관리에서 정책을 **선택합니다.**

3. 정책 페이지에서 링크 **금고 선택합니다.**

기본 정책을 수정하려면

1. 사이트 금고 페이지의 전체 조직에 적용되는 정책에서 **기본** 정책을 두 **번** 클릭합니다.

2. **에서** 설정 콘텐츠에 적용되는 Office 365 에서 차단할 URL(예: example.com 을 **+** 선택합니다.

3. 전자 **설정** 제외한 콘텐츠에 적용되는 목록에서 Office 365 **응용** 프로그램 **,** 사용자가 안전한 링크를 클릭하는 경우 추적 안 를 선택하고 사용자가 원래 URL에 대한 안전한 링크를 클릭할 수 있도록 하지 않습니다.를 **선택합니다.**

4. **저장** 을 선택합니다.

도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.

1. 사이트 금고 페이지의 특정 받는 사람에게 적용되는 정책에서 **를** 선택하여 새 정책을 **+** 만드십시오.

2. 다음 표에 나열된 설정을 적용합니다.

3. **저장** 을 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|금고 받는 사람에 대한 링크 정책 설정|
|메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택|을 **선택합니다.** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련한 URL이 다시 덮어지지 않습니다.|
|파일을 지정하는 의심스러운 링크 및 링크에 대한 실시간 URL 검사 적용|이 상자를 선택합니다.|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|
|

자세한 내용은 microsoft [Defender에서](../../security/office-365-security/atp-safe-links.md)금고 링크를 참조하세요Office 365.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 다단계](multi-factor-authentication-microsoft-365.md) 인증(문서)\
[우선 순위 계정 관리](../setup/priority-accounts.md) 및 모니터링(문서)\
[Microsoft 365 센터의 보고서(동영상)](../activity-reports/activity-reports.md)