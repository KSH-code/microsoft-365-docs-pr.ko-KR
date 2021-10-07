---
title: 위협 방지 강화
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: 보안 수준 증가에 대한 도움말을 Microsoft 365
ms.openlocfilehash: 42acbae868a3d451add0b93a0b7c21d46893010d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172782"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>구독에 대한 위협 Microsoft 365 증가

이 문서는 피싱, 맬웨어 및 기타 위협으로부터 보호하기 위해 Microsoft 365 구독의 보호를 강화하는 데 도움이 됩니다. 이러한 권장 사항은 정치적 캠페인, 법률 사무소 및 의료 기관과 같이 보안에 대한 필요성이 증가하는 조직에 적합한 권장 사항입니다.

시작하기 전에 Microsoft 보안 점수를 검사합니다. Microsoft 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다. 먼저 현재 점수를 기록해 넣습니다. 이 문서에서 권장하는 작업을 수행하면 점수가 향상됩니다. 목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호하기 위한 기회를 인식하는 것입니다.

자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../security/defender/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>메일의 맬웨어에 대한 보호 수준 높이기

사용자 Office 365 Microsoft 365 환경에는 맬웨어에 대한 보호가 포함되어 있지만 맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다. 전자 메일에서 맬웨어 보호를 범프합니다.

1. Office 365 보안 & <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">센터로</a> 이동하고 관리자 계정 자격 증명으로 로그인합니다.

2. 왼쪽 탐색 창의 **위협** 관리에서 정책 **맬웨어** 방지 \> **를 선택 합니다.**

3. 기본 정책을 두 번 클릭하여 이 회사 전체 정책을 편집합니다.

4. **설정** 을 클릭합니다.

5. 일반 **첨부 파일 형식 필터에서** 를 **선택합니다.** 차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다. 다음 파일 형식을 추가해야 합니다.

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.

6. **저장** 을 클릭합니다.

자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>랜섬웨어로부터 보호

랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다. 그런 다음 데이터에 대한 액세스 대가로 일반적으로 가상화 형식의 "금전"을 요청하여 피해자로부터 돈을 유출하려고 시도합니다.

랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단하는 메일 흐름 규칙을 하나 이상 만들어 랜섬웨어로부터 보호하거나(메일 단계에서 맬웨어에 대한 보호 수준 높이기에서 추가) 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고할 수 있습니다. [](#raise-the-level-of-protection-against-malware-in-mail)

이전 단계에서 차단한 파일 외에도 매크로가 포함된 첨부 파일을 열기 전에 사용자에게 경고하는 Office 만드는 것이 좋습니다. 매크로 내에서 랜섬웨어를 숨길 수 있으므로 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.

메일 전송 규칙을 만들 수 있습니다.

1. 의 관리 센터로 이동하여 관리 센터 <https://admin.microsoft.com>  \> Exchange.

2. 메일 **흐름 범주에서** 규칙을 **클릭합니다.**

3. **+** 를 클릭한 다음 새 규칙 **만들기 를 클릭합니다.**

4. 대화 **상자 아래쪽의** 다른 옵션을 클릭하여 전체 옵션 집합을 볼 수 있습니다.

5. 규칙에 대한 다음 표의 설정을 적용합니다. 나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.

6. **저장** 을 클릭합니다.

|설정|파일 첨부 파일을 열기 전에 Office 경고|
|---|---|
|이름|랜섬웨어 방지 규칙: 사용자에게 경고|
|이 경우 이 규칙을 적용합니다. . .|모든 첨부 파일 . . . 파일 확장명은 을 일치합니다. . .|
|단어 또는 구 지정|다음 파일 형식을 추가합니다. <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|다음을 합니다. . .|받는 사람에게 메시지로 알림|
|메시지 텍스트 제공|악성 코드가 포함된 매크로가 포함되어 있을 수 있기 때문에 모르는 사용자로부터 이러한 형식의 파일을 열지 않습니다.|

자세한 내용은 다음을 참조하세요.

- [랜섬웨어: 위험을 줄이는 방법](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [사용자 OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>전자 메일에 대한 자동 전달 중지

사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다. 이는 사용자의 인식 없이도 발생될 수 있습니다. 메일 흐름 규칙을 구성하여 이러한 문제를 방지할 수 있습니다.

메일 전송 규칙을 만들 수 [](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 있는 경우 이 짧은 비디오를 시청하거나 다음 단계를 따르세요.

1. 에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a> **에서** 관리 센터 를 \> **Exchange.**

2. 메일 **흐름 범주에서** 규칙을 **클릭합니다.**

3. **+** 를 클릭한 다음 새 규칙 **만들기 를 클릭합니다.**

4. 대화 **상자 아래쪽의** 다른 옵션을 클릭하여 전체 옵션 집합을 볼 수 있습니다.

5. 다음 표의 설정을 적용합니다. 나머지 설정을 변경하지 않는 한 나머지 설정을 기본값으로 그대로 두면 됩니다.

6. **저장** 을 클릭합니다.

|설정|파일 첨부 파일을 열기 전에 Office 경고|
|---|---|
|이름|외부 도메인으로 전자 메일 자동 전달 방지|
|다음의 경우 이 규칙을 적용합니다.|보낸 사람 입니다. . . 은 외부/내부입니다. . . 조직 내부|
|조건 추가|메시지 속성 입니다. . . 메시지 유형 을 포함합니다. . . 자동 전달|
|다음 작업을 합니다.|메시지를 차단합니다. . . 메시지를 거부하고 설명을 포함합니다.|
|메시지 텍스트 제공|보안상의 이유로 이 조직 외부에서 전자 메일을 자동 전달할 수 없습니다.|

## <a name="protect-your-email-from-phishing-attacks"></a>피싱 공격으로부터 전자 메일 보호

Office 365 또는 Microsoft 365 사용자 지정 도메인을 하나 이상 구성한 경우 대상 피싱 방지 보호를 구성할 수 있습니다. Microsoft Defender for Office 365 피싱 방지 보호는 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.

가장 중요한 사용자와 사용자 지정 도메인을 보호하는 정책을 만들어 이 보호를 시작하는 것이 좋습니다.

사용자용 Defender에서 피싱 방지 정책을 Office 365 이 짧은 [](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)교육 비디오를 시청하거나 다음 단계를 완료합니다.

1. 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 준수 & 로 이동</a>

2. 왼쪽 탐색 창의 **위협 관리에서** 정책을 **선택 합니다.**

3. 정책 **페이지에서** 피싱 **방지 를 선택합니다.**

4. 피싱 **방지 페이지에서** + **만들기를 선택합니다.** 피싱 방지 정책을 정의하는 단계를 안내하는 마법사가 실행됩니다.

5. 아래 차트에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다. 자세한 내용은 Microsoft Defender에서 피싱 방지 정책에 대해 자세히 Office 365 [참조하세요.](../security/office-365-security/set-up-anti-phishing-policies.md)

6. 설정을 검토한 후 이 정책  만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인 및 가장 중요한 직원|
|설명|가장 중요한 직원과 도메인이 가장되지 않도록 합니다.|
|보호할 사용자를 추가|+ **조건 추가를 선택합니다. 받는 사람은 입니다.** 사용자 이름을 입력하거나 비즈니스 소유자, 파트너 또는 후보, 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다. 가장으로부터 보호할 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.|
|보호할 도메인을 추가|+ **조건 추가를 선택하고 받는 사람 도메인은 입니다.** 사용자 지정 도메인을 정의한 경우 Microsoft 365 사용자 지정 도메인을 입력합니다. 두 개 이상의 도메인을 입력할 수 있습니다.|
|작업 선택|가장된 사용자가 전자 메일을 보낸 경우: **메시지를** 다른 전자 메일 주소로 리디렉션을 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 *Alice <span> <span> @contoso.com.* <br/> 가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.|
|사서함 인텔리전스|새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.|
|신뢰할 수 있는 발신자와 도메인 추가|여기에서 자체 도메인 또는 기타 신뢰할 수 있는 도메인을 추가할 수 있습니다.|
|적용 대상|**받는 사람의 도메인이 다음과 같음** 을 선택합니다. **이러한 항목 모두** 아래에서 **선택** 을 선택합니다. **+ 추가** 를 선택합니다. 도메인 이름 옆의 확인란(예: *contoso)을 선택합니다. <span> <span> 목록에서 com* 을 선택하고 추가를 **선택합니다.** **완료** 를 선택합니다.|

자세한 내용은 [Set up anti-phishing policies in Defender for Office 365.](../security/office-365-security/set-up-anti-phishing-policies.md)

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>악의적인 첨부 파일, 파일 및 링크를 보호하기 위해 Defender를 Office 365

![을(를) 포인트로 하는 https://aka.ms/aboutM365preview 배너입니다.](../media/m365admincenterchanging.png)

먼저 관리 센터에서 새 관리 센터 미리 보기가 <https://admin.microsoft.com> 켜져 있는지 확인 합니다. 텍스트 옆에 있는 토글을 켜면 새 **관리 센터 입니다.**

   ![새 관리 센터 미리 보기가 설정됩니다.](../media/previewon.png)

테넌트에 카드가  있는 설치 페이지가 아직 없는 경우 보안 및 준수 센터에서 & 완료하는 방법을 참조하세요. 보안 [금고](#set-up-safe-attachments-in-the-security--compliance-center) 준수 센터에서 & 첨부 파일 설정 및 보안 금고 준수 센터에서 금고 링크를 [& 참조하세요.](#set-up-safe-links-in-the-security--compliance-center)

1. In the left nav, choose **Setup**.
2. 설치 **페이지에서** 고급 **위협으로부터** 보호 강화 **카드에서 보기를** 선택합니다.

   ![고급 위협으로부터 보호 강화에서 보기를 선택하십시오.](../media/startatp.png)

3. 고급 **위협으로부터 보호 강화 페이지에서** 시작 **을 선택합니다.**
4. 창이 열리면 전자 메일의 링크 및 첨부 파일, **SharePoint,** OneDrive 및 Teams 에서 파일 검색 옆의 확인란을 선택하고 Office 데스크톱 및 Office **Online** 앱의 링크 검사에서 악성 콘텐츠가 검색됩니다.

   전자 메일의 링크 **및 첨부 파일에서** 모든 사용자 또는 전자 메일을 검사할 특정 사용자를 입력합니다.

   ![고급 위협으로부터 보호 강화의 모든 확인란을 선택합니다.](../media/setatp.png)

5. 정책 **만들기를** 선택하면 첨부 파일 및 금고 설정 금고 을 하게 됩니다.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>보안 금고 준수 센터에서 & 첨부 파일 설정

문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다. 전자 메일 메시지를 확인하여 첨부 파일이 안전한지 악성인지를 항상 쉽게 알 수 있는 것은 아닙니다. Microsoft Defender for Office 365 첨부 금고 포함하지만 기본적으로 이 보호는 켜져 있지 않습니다. 이 보호를 사용하 여 시작 하는 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft Teams.

첨부 파일 금고 만들거나 이 짧은 [](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)비디오를 시청하거나 다음 단계를 완료합니다.

1. 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 준수 & 관리</a> 계정으로 로그인합니다.

2. 왼쪽 탐색 창의 **위협 관리에서** 정책을 **선택 합니다.**

3. 정책 페이지에서 첨부 **금고 선택합니다.**

4. 금고 첨부 파일 페이지에서 SharePoint, OneDrive 및 Microsoft Teams ATP 켜기 확인란을 선택하여 이 보호를 **광범위하게 적용합니다.**

5. 새 **+** 정책을 만들 수 있습니다.

6. 다음 표의 설정을 적용합니다.

7. 설정을 검토한 후 이 **정책** 만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.|
|설명|감지된 맬웨어로 현재 및 미래의 전자 메일 및 첨부 파일을 차단합니다.|
|첨부 파일 알 수 없는 맬웨어 응답 저장|차단 - 감지된 맬웨어로 현재 및 미래의 전자 메일 **및 첨부 파일을 차단을 선택합니다.**|
|검색 시 첨부 파일 리디렉션|리디렉션 사용(이 상자 선택) <br/> 관리자 계정 또는 사서함 설정을 입력하여 검지합니다. <br/> 첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자 선택).|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|

자세한 내용은 [Set up anti-phishing policies in Defender for Office 365.](../security/office-365-security/set-up-anti-phishing-policies.md)

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>보안 금고 준수 센터에서 & 링크 설정

해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다. 금고 Microsoft Defender의 일부인 Office 365 링크는 전자 메일 메시지 및 문서의 웹 주소(URL)에 대한 클릭 시간 확인을 제공하여 조직을 Office 있습니다. 보호는 링크 정책을 통해 금고 정의됩니다.

다음을 하는 것이 좋습니다.

- 보호를 강화하도록 기본 정책을 수정합니다.

- 도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.

링크 금고 설정하기 위해 이 [짧은](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)교육 비디오를 시청하거나 다음 단계를 완료합니다.

1. 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 준수 & 관리</a> 계정으로 로그인합니다.

2. 왼쪽 탐색 창의 **위협 관리에서** 정책을 **선택 합니다.**

3. 정책 페이지에서 링크 **금고 선택합니다.**

기본 정책을 수정하려면

1. 사이트 금고 페이지의 전체 조직에 적용되는 정책에서 **기본** **정책을** 선택합니다.

2. 전자 **설정** 제외한 콘텐츠에 적용되는 응용 프로그램 아래에서 iOS 및 엔터프라이즈용 Microsoft 365 앱 Office **를 선택합니다.**

3. **저장** 을 클릭합니다.

도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.

1. 사이트 금고 페이지의 전체 조직에 적용되는 정책에서 **를** 클릭하여 새 정책을 **+** 만드십시오.

2. 다음 표에 나열된 설정을 적용합니다.

3. **저장** 을 클릭합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|금고 받는 사람에 대한 링크 정책 설정|
|메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택|을 **선택합니다.** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련한 URL이 다시 덮어지지 않습니다.|
|첨부 금고 사용하여 다운로드 가능한 콘텐츠 검색|이 상자를 선택합니다.|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|

자세한 내용은 에 [대한 금고 Defender의 링크를 Office 365.](../security/office-365-security/safe-links.md)

## <a name="turn-on-the-unified-audit-log"></a>통합 감사 로그 켜기

보안 및 준수 센터에서 감사 로그 검색을 & 로그에 관리자 및 기타 사용자 활동을 보존하고 검색할 수 있습니다.

감사 로그 검색을 Exchange Online 구독에서 감사 로그 검색을 설정하거나 해제하려면 감사 로그 역할이 Microsoft 365 합니다. 기본적으로 이 역할은 Exchange 관리 센터의 사용 권한 페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. Microsoft 365 전역 관리자는 기본적으로 이 그룹의 구성원입니다.

1. 감사 로그 검색을 켜기 위해 의 관리 센터로 이동한 다음 왼쪽 탐색의 관리 센터에서 보안을 <https://admin.microsoft.com> 선택하세요.  
2. 보안 **Microsoft 365** 추가 리소스 를 선택한 다음  Office 365 **보안** 및 준수 센터 카드에서 & 을 선택합니다. 

    ![보안 및 준수 자동차에서 & 를 선택 합니다.](../media/gotosecandcomp.png)
3. 보안 및 준수 페이지에서 검색을 **선택한** 다음 로그 검색 **감사 를 선택합니다.**
4. 감사 로그 **검색** 페이지의 맨 위에 있는 감사 **켜기 를 선택합니다.**

기능이 켜진 후 파일, 폴더 및 여러 활동을 검색할 수 있습니다. 자세한 내용은 감사 로그 [검색을 참조하세요.](../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>파일 및 폴더에 대한 익명 SharePoint OneDrive 설정 조정

기본 익명 링크 만료를 14일로 변경하고 기본 공유 유형을 "특정 사용자"로 변경) 사용자 및 사용자에 대한 공유 OneDrive 변경하려면 SharePoint.

1. 의 관리 센터로 이동한 다음 왼쪽 SharePoint 관리 센터에서 관리 센터를 <https://admin.microsoft.com> 선택하세요.  
2. SharePoint 관리 센터에서 정책 공유 **로** \> **이동하세요.**
3. 공유  페이지의 파일 및 폴더 링크에서  **특정** 사용자 및 **"모든 사용자"** 링크의 고급 설정에서 이러한 링크가 이 기간 내에 만료되어야 합니다.를 선택하고 14(또는 링크 수명을 제한하려는 다른 일 수)를 입력합니다. 

   ![특정 사용자 및 링크 만료를 14일로 설정](../media/anyonelinks.png)

## <a name="activity-alerts"></a>활동 알림

활동 알림을 사용하여 관리자 및 사용자 활동을 추적하고 조직의 맬웨어 및 데이터 손실 방지 인시던트 감지를 할 수 있습니다. 구독에는 기본 정책 집합이 포함되어 있지만 사용자 지정 정책 집합을 만들 수도 있습니다. 자세한 내용은 경고 정책을 [참조하세요.](../compliance/alert-policies.md) 예를 들어 다른 사람이 외부에서 공유하지 SharePoint 중요한 파일을 저장하는 경우 다른 사용자가 공유하는 경우 알림을 만들 수 있습니다.

다음 그림에서는 정책에 포함된 기본 정책을 Microsoft 365.

![정책에 포함된 기본 경고 Microsoft 365.](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>일정 공유를 사용하지 않도록 설정하거나 관리

조직의 사용자가 일정을 공유하지 못하게 할 수도 있습니다. 또는 공유할 수 있는 것을 관리할 수도 있습니다. 예를 들어 공유를 사용/사용 중 시간으로만 제한할 수 있습니다.

1. 의 관리 센터로 이동하여 설정 <https://admin.microsoft.com>  \> **또는 설정**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**을 선택하세요.**</a>

1. 일정 **을** 선택하고 조직의 사용자들이 일정을 다른 사용자나 다른 사용자와 공유할 수 Office 365 Exchange 선택할 수 있습니다.

   모든 사용자와 공유 옵션을 선택하는 경우 사용 중 정보만 공유하기로 결정할 수 있습니다.

3. 페이지 **아래쪽의** 변경 내용 저장을 선택합니다.

   다음 그림에서는 일정 공유를 허용하지 않는지 보여줍니다.

   ![허용되지 않는 외부 일정 공유를 표시하는 스크린샷.](../media/nocalendarsharing.png)

   다음 그림에서는 약속 있는/약속이 있는 정보만 있는 전자 메일 링크로 일정 공유가 허용되는 경우의 설정을 보여줍니다.

   ![모든 사람과 약속이 있는 일정 공유의 스크린샷.](../media/sharefreebusy.png)

사용자가 일정을 공유할 수 있는 경우 [](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) 다음 지침을 참조하여 일정에서 공유하는 웹용 Outlook.
