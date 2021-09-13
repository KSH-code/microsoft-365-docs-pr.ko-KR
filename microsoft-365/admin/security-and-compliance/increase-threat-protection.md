---
title: 비즈니스용 보안 기능의 Microsoft 365 보호 강화
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 피싱, Office 365 및 기타 위협으로부터 중요한 데이터를 보호하고 보호할 수 있는 Microsoft Defender를 설정하십시오.
ms.openlocfilehash: f7e82497baff1f14d1a1ff2cfc1d0e05c38700be
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186851"
---
# <a name="increase-threat-protection"></a>위협 방지 강화

이 문서는 피싱, 맬웨어 및 기타 위협으로부터 보호하기 위해 Microsoft 365 구독의 보호를 강화하는 데 도움이 됩니다. 이러한 권장 사항은 법률 사무소 및 의료 기관과 같이 보안에 대한 필요성이 증가하는 조직에 적합합니다.

시작하기 전에 보안 점수를 Office 365 검사합니다. Office 365 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다. 먼저 현재 점수를 기록해 넣습니다. 점수를 높이기 위해 이 문서에서 권장하는 작업을 완료합니다. 목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호할 기회를 인식하는 것입니다.

자세한 내용은 Microsoft 보안 점수를 [참조하세요.](../../security/defender/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>메일의 맬웨어에 대한 보호 수준 높이기

사용자 Office 365 Microsoft 365 맬웨어에 대한 보호가 포함됩니다. 맬웨어에 일반적으로 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다. 전자 메일에서 맬웨어 보호를 강화하는 방법:

1. 으로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정 자격 증명으로 로그인합니다.

2. 보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 정책 &amp; 맬웨어 방지   \> **를 선택 합니다.**

3. 기본 정책을 두 번 클릭하여 이 회사 전체 정책을 편집합니다.

4. **설정** 을 선택합니다.

5. 일반 **첨부 파일 형식 필터에서** 를 **선택합니다.** 차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다. 다음 파일 형식을 추가해야 합니다.

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.

6. 저장을 **선택합니다.**

자세한 내용은 [EOP의 맬웨어 방지 보호를 참조하세요.](../../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>랜섬웨어로부터 보호

랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다. 그런 다음 데이터에 대한 액세스 대가로 일반적으로 가상화 형식의 "금전"을 요청하여 피해자로부터 돈을 유출하려고 시도합니다.

랜섬웨어로부터 보호하기 위해 하나 이상의 메일 흐름 규칙을 만들어 랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단합니다. 메일 단계에서 맬웨어에 대한 보호 수준을 [높이기](#raise-the-level-of-protection-against-malware-in-mail) 위해 이러한 규칙을 추가했습니다. 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고할 수도 있습니다.

이전 단계에서 차단한 파일 외에도 매크로가 포함된 첨부 파일을 열기 전에 사용자에게 경고하는 Office 만드는 것이 좋습니다. 매크로 내에서 랜섬웨어를 숨길 수 있으므로 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.

메일 전송 규칙을 만들 수 있습니다.

1. 의 관리 센터로 이동하여 관리 센터 <https://admin.microsoft.com>  \> Exchange.

2. 메일 **흐름 범주에서** 규칙을 **선택합니다.**

3. **+** 를 선택한 다음 새 규칙 **만들기 를 선택합니다.**

4. 전체 **옵션 집합을** 확인하려면 대화 상자 아래쪽에서 다른 옵션을 선택합니다.

5. 규칙에 대한 다음 표의 설정을 적용합니다. 나머지 설정은 변경하지 않는 한 기본값을 사용합니다.

6. **저장** 을 선택합니다.

|설정|파일 첨부 파일을 열기 전에 Office 경고|
|---|---|
|이름|랜섬웨어 방지 규칙: 사용자에게 경고|
|이 경우 이 규칙을 적용합니다. . .|모든 첨부 파일 . . . 파일 확장명은 을 일치합니다. . .|
|단어 또는 구 지정|다음 파일 형식을 추가합니다.  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|다음을 합니다. . .|받는 사람에게 메시지로 알림|
|메시지 텍스트 제공|악성 코드가 포함된 매크로가 포함되어 있을 수 있기 때문에 모르는 사용자로부터 이러한 형식의 파일을 열지 않습니다.|

자세한 내용은 다음을 참조하세요.

- [랜섬웨어: 위험을 줄이는 방법](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [사용자 OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>전자 메일에 대한 자동 전달 중지

사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다. 이는 사용자의 인식 없이도 발생될 수 있습니다. 이러한 문제를 방지할 수 있도록 메일 흐름 규칙을 구성합니다.

메일 전송 규칙을 만들 수 [](../../business-video/stop-email-auto-forward.md) 있는 경우 이 짧은 비디오를 시청하거나 다음 단계를 따르세요.

1. 다음 Microsoft 365 관리 센터 에서 관리 센터 **를** \> **Exchange.**

2. 메일 **흐름 범주에서** 규칙을 **선택합니다.**

3. **+** 를 선택한 다음 새 규칙 **만들기 를 선택합니다.**

4. 모든 옵션을 확인하려면 대화 **상자** 아래쪽에서 다른 옵션을 선택합니다.

5. 다음 표의 설정을 적용합니다. 나머지 설정은 변경하지 않는 한 기본값을 사용합니다.

6. **저장** 을 선택합니다.

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

Microsoft Defender에서 피싱 방지 정책을 Office 365 이 짧은 교육 [](../../business-video/setup-anti-phishing.md)비디오를 시청하거나 다음 단계를 완료하세요.

1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.

2. 보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** 

3. 정책 **페이지에서** 피싱 **방지 를 선택합니다.**

4. 피싱 **방지 페이지에서** + **만들기를 선택합니다.** 피싱 방지 정책을 정의하는 단계를 안내하는 마법사가 실행됩니다.

5. 다음 표에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다. 자세한 내용은 Microsoft [Defender에서](../../security/office-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책에 대해 자세히 Office 365 옵션을 참조하세요.

6. 설정을 검토한 후 이 정책  만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인 및 가장 중요한 캠페인 직원|
|설명|가장 중요한 직원과 도메인이 가장되지 않도록 합니다.|
|보호할 사용자를 추가|+ **조건 추가를 선택합니다. 받는 사람은 입니다.** 사용자 이름을 입력하거나 후보, 캠페인 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다. 가장으로부터 보호할 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.|
|보호할 도메인을 추가|+ **조건 추가를 선택하고 받는 사람 도메인은 입니다.** 사용자 지정 도메인을 정의한 경우 Microsoft 365 사용자 지정 도메인을 입력합니다. 두 개 이상의 도메인을 입력할 수 있습니다.|
|작업 선택|가장된 사용자가 전자 메일을 보낸 경우: **메시지를** 다른 전자 메일 주소로 리디렉션을 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 *Alice <span> <span> @contoso.com.* 가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.|
|사서함 인텔리전스|새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.|
|신뢰할 수 있는 발신자와 도메인 추가|여기에서 자체 도메인 또는 기타 신뢰할 수 있는 도메인을 추가할 수 있습니다.|
|적용 대상|**받는 사람의 도메인이 다음과 같음** 을 선택합니다. **이러한 항목 모두** 아래에서 **선택** 을 선택합니다. **+ 추가** 를 선택합니다. 도메인 이름 옆의 확인란(예: *contoso)을 선택합니다. <span> <span> 목록에서 com* 을 선택하고 추가를 **선택합니다.** **완료** 를 선택합니다.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>첨부 파일을 통해 악의적인 첨부 파일 및 금고 보호

문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다. 전자 메일 메시지를 확인하여 첨부 파일이 안전한지 악성인지를 항상 쉽게 알 수 있는 것은 아닙니다. Microsoft Defender for Office 365 첨부 금고 포함하지만 기본적으로 이 보호는 켜져 있지 않습니다. 이 보호를 사용하 여 시작 하는 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft Teams.

첨부 파일 금고 만들거나 이 짧은 [](../../business-video/safe-attachments.md)비디오를 시청하거나 다음 단계를 완료합니다.

1. 로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정으로 로그인합니다.

2. 보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** 

3. 정책 페이지에서 첨부 **금고 선택합니다.**

4. 금고 첨부 파일 페이지에서 SharePoint, OneDrive 및 Microsoft Teams ATP 켜기 확인란을 선택하여 이 보호를 **광범위하게 적용합니다.**

5. 새 **+** 정책을 만들 수 있습니다.

6. 다음 표의 설정을 적용합니다.

7. 설정을 검토한 후 이  정책 만들기 또는 **저장을** 적절하게 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.|
|설명|감지된 맬웨어로 현재 및 미래의 전자 메일 및 첨부 파일을 차단합니다.|
|첨부 파일 알 수 없는 맬웨어 응답 저장|차단 - 감지된 맬웨어로 현재 및 미래의 전자 메일 **및 첨부 파일을 차단을 선택합니다.**|
|검색 시 첨부 파일 리디렉션|리디렉션 사용(이 상자 선택) 관리자 계정 또는 사서함 설정을 입력하여 확인란을 선택합니다.          첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자 선택).|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|

자세한 내용은 [Microsoft Defender에서](../../security/office-365-security/set-up-anti-phishing-policies.md)피싱 방지 정책 Office 365.

## <a name="protect-against-phishing-attacks-with-safe-links"></a>링크로 피싱 금고 보호

해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다. 금고 Microsoft Defender의 일부인 Office 365 링크는 전자 메일 메시지 및 문서의 웹 주소(URL)에 대한 클릭 시간 확인을 제공하여 조직을 Office 있습니다. 보호는 링크 정책을 통해 금고 정의됩니다.

다음을 하는 것이 좋습니다.

- 보호를 강화하도록 기본 정책을 수정합니다.

- 도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.

링크 금고 설정하기 위해 이 [짧은](../../business-video/safe-links.md)교육 비디오를 시청하거나 다음 단계를 완료합니다.

1. 로 [https://protection.office.com](https://protection.office.com) 이동하여 관리자 계정으로 로그인합니다.

2. 보안 및 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 &amp; 정책을 **선택 합니다.** 

3. 정책 페이지에서 링크 **금고 선택합니다.**

기본 정책을 수정하려면

1. 사이트 금고 페이지의 전체 조직에 적용되는 정책에서 **기본** **정책을** 선택합니다.

2. 전자 **설정** 제외한 콘텐츠에 적용되는 응용 프로그램 아래에서 iOS 및 엔터프라이즈용 Microsoft 365 앱 Office **를 선택합니다.**

3. **저장** 을 선택합니다.

도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.

1. 사이트 금고 페이지의 전체 조직에 적용되는 정책에서 **를** 선택하여 새 정책을 **+** 만들 수 있습니다.

2. 다음 표에 나열된 설정을 적용합니다.

3. **저장** 을 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|금고 받는 사람에 대한 링크 정책 설정|
|메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택|을 **선택합니다.** 사용자가 링크를 클릭할 때 알려진 악성 링크 목록과 관련한 URL이 다시 덮어지지 않습니다.|
|첨부 금고 사용하여 다운로드 가능한 콘텐츠 검색|이 상자를 선택합니다.|
|적용 대상|받는 사람 도메인은 입니다. . . 도메인을 선택합니다.|

자세한 내용은 링크 금고 [참조하세요.](../../security/office-365-security/safe-links.md)

## <a name="go-to-intune-admin-center"></a>Intune 관리 센터로 이동합니다.

1. [Azure Portal에 로그인합니다.](https://portal.azure.com/)

2. **모든 서비스** 를 선택하고 **검색 상자** 에 *Intune* 을 입력합니다.

3. 결과가 나타나면 나중에 쉽게 찾을  수 Microsoft Intune 만들기 위해 목록 옆에 있는 시작을 선택합니다.

관리 센터 외에도 Intune을 사용하여 조직의 장치를 등록하고 관리할 수 있습니다. 자세한 내용은 Windows [](/intune/enrollment/enrollment-method-capab) 장치 등록 방법 및 [Intune에서](/intune/enrollment-options)관리하는 장치에 대한 등록 옵션을 참조하세요.
