---
title: 위협 방지 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Microsoft 365의 보호 수준 향상에 대 한 도움말 보기
ms.openlocfilehash: 99b9bfac7867d6f6b29571940f717667fd05a697
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843259"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Microsoft 365 구독에 대 한 위협 보호 강화

이 문서는 Microsoft 365 구독의 보호를 향상 시켜 피싱, 맬웨어 및 기타 위협 으로부터 보호 하는 데 도움이 됩니다. 이러한 권장 사항은 정치적 캠페인, 법률 사무소 및 의료 보험 clinics 같은 보안 요구 사항이 증가 하는 조직에 적합 합니다.

시작 하기 전에 Microsoft 보안 점수를 확인 하세요. Microsoft 보안 점수는 정기 활동 및 보안 설정에 따라 조직의 보안을 분석 하 고 점수를 할당 합니다. 먼저 현재 점수를 기록 합니다. 이 문서에서 권장 하는 작업을 수행 하면 점수가 증가 합니다. 목표는 최대 점수를 얻는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호 하기 위한 기회를 얻기 위한 것입니다.

자세한 내용은 [Microsoft 보안 점수](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)를 참조 하세요.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>메일에서 맬웨어에 대 한 보호 수준 올리기

Office 365 또는 Microsoft 365 환경에는 맬웨어에 대 한 보호 기능이 포함 되어 있지만 일반적으로 맬웨어에 사용 되는 파일 형식을 사용 하 여 첨부 파일이 차단 되므로이 보호 기능을 높일 수 있습니다. 전자 메일에서 맬웨어 보호를 강화 하려면:

1. 으로 이동 하 <https://protection.office.com> 고 관리자 계정 자격 증명으로 로그인 합니다.

2. 보안 & 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리** 에서 **정책** \> **맬웨어 방지** 를 선택 합니다.

3. 기본 정책을 두 번 클릭 하 여이 회사 차원의 정책을 편집 합니다.

4. **설정** 을 클릭합니다.

5. **일반 첨부 파일 형식 필터** 에서 **설정** 를 선택 합니다. 차단 되는 파일 형식은이 컨트롤 바로 아래의 창에 나열 됩니다. 다음 filetypes를 추가 했는지 확인 합니다.

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   필요한 경우 나중에 파일 형식을 추가 하거나 삭제할 수 있습니다.

6. **저장** 을 클릭합니다.

자세한 내용은 [EOP의 맬웨어 방지 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)를 참조 하세요.

## <a name="protect-against-ransomware"></a>랜섬웨어로부터 보호

랜 섬 웨어는 파일 암호화 또는 컴퓨터 화면 잠금을 통해 데이터에 대 한 액세스를 제한 합니다. 그런 다음 일반적으로 데이터에 액세스 하기 위해 exchange에서 "ransom" (예를 들어, Bits 동전) 형식을 사용 하 여 victims에서 ort money를 요청 합니다.

메일 흐름 규칙을 하나 이상 만들어 차단에 일반적으로 사용 되는 파일 확장명 (즉, [메일 단계에서 맬웨어에 대 한 보호 수준 올리기](#raise-the-level-of-protection-against-malware-in-mail) )이 나 전자 메일로 이러한 첨부 파일을 받는 사용자에 게 경고 메시지를 표시 하 여 랜 섬 웨어 로부터 보호할 수 있습니다.

이전 단계에서 차단한 파일 외에도 매크로를 포함 하는 Office 첨부 파일을 열기 전에 사용자에 게 경고 하는 규칙을 만드는 것이 좋습니다. 매크로 내에서 랜 섬 웨어를 숨길 수 있으므로 사용자가 알지 못하는 사용자 로부터 이러한 파일을 열지 않도록 경고 메시지를 표시 합니다.

메일 전송 규칙을 만들려면 다음을 수행 합니다.

1. 관리 센터로 이동 <https://admin.microsoft.com> 하 여 **관리 센터** \> **Exchange** 를 선택 합니다.

2. **메일 흐름** 범주에서 **규칙** 을 클릭 합니다.

3. 을 클릭 한 **+** 다음 **새 규칙 만들기** 를 클릭 합니다.

4. 대화 상자 아래쪽에 있는 **기타 옵션** 을 클릭 하 여 전체 옵션 집합을 표시 합니다.

5. 다음 표에 해당 규칙에 대 한 설정을 적용 합니다. 설정을 변경 하려는 경우가 아니면 나머지 설정은 기본값으로 유지 합니다.

6. **저장** 을 클릭합니다.

|설정|Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시|
|---|---|
|이름|랜 섬 웨어 방지 규칙: 사용자에 게 경고 표시|
|다음 경우에이 규칙을 적용 합니다. . .|모든 첨부 파일 . . 일치 하는 파일 확장명 . .|
|단어 또는 구 지정|다음 파일 형식을 추가 합니다. <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|다음을 수행 합니다. . .|받는 사람에게 메시지로 알림|
|메시지 텍스트 제공|악성 코드가 포함 된 매크로를 포함할 수 있으므로 모르는 사용자 로부터 이러한 유형의 파일을 열지 마십시오.|

자세한 내용은 다음을 참조하세요.

- [랜 섬 웨어: 위험을 줄이는 방법](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [OneDrive 복원](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>전자 메일에 대 한 자동 전달 중지

사용자의 사서함에 대 한 액세스 권한을 획득 하는 해커는 전자 메일을 자동으로 전달 하도록 사서함을 설정 하 여 메일을 도용할 수 있습니다. 사용자의 인식이 없어도이 문제가 발생할 수 있습니다. 메일 흐름 규칙을 구성 하 여 이러한 상황이 발생 하지 않도록 할 수 있습니다.

메일 전송 규칙을 만들려면 [이 짧은 비디오](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 를 시청 하거나 다음 단계를 수행 합니다.

1. Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange** 를 클릭 합니다.

2. **메일 흐름** 범주에서 **규칙** 을 클릭 합니다.

3. 을 클릭 한 **+** 다음 **새 규칙 만들기** 를 클릭 합니다.

4. 대화 상자 아래쪽에 있는 **기타 옵션** 을 클릭 하 여 전체 옵션 집합을 표시 합니다.

5. 다음 표의 설정을 적용 합니다. 설정을 변경 하려는 경우가 아니면 나머지 설정은 기본값으로 유지 합니다.

6. **저장** 을 클릭합니다.

|설정|Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시|
|---|---|
|이름|외부 도메인에 대 한 전자 메일 자동 전달 금지|
|다음 경우에이 규칙 적용 ...|보낸 사람입니다. . . 은 외부/내부입니다. . . 조직 내부|
|조건 추가|메시지 속성 . . 메시지 유형을 포함 합니다. . . 자동 전달|
|다음을 수행 합니다.|메시지를 차단 합니다. . . 메시지를 거부 하 고 설명을 포함 합니다.|
|메시지 텍스트 제공|보안상의 이유로이 조직 외부에서 전자 메일을 자동 전달 하는 것은 허용 되지 않습니다.|

## <a name="protect-your-email-from-phishing-attacks"></a>피싱 공격 으로부터 전자 메일을 보호 합니다.

Office 365 또는 Microsoft 365 환경용으로 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호 기능을 구성할 수 있습니다. 피싱 방지 보호 기능 (Microsoft Defender for Office 365의 일부)은 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격 으로부터 조직을 보호 하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성 하지 않은 경우에는이 작업을 수행 하지 않아도 됩니다.

가장 중요 한 사용자와 사용자 지정 도메인을 보호 하는 정책을 만들어이 보호를 시작 하는 것이 좋습니다.

Defender for Office 365에서 피싱 방지 정책을 만들려면 [이 간략 한 교육 비디오](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)를 시청 하거나 다음 단계를 완료 하세요.

1. <https://protection.office.com>으로 이동합니다.

2. 보안 & 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리** 에서 **정책을** 선택 합니다.

3. **정책** 페이지에서 **피싱 방지** 를 선택 합니다.

4. **피싱 방지** 페이지에서 **+ 만들기** 를 선택 합니다. 피싱 방지 정책을 정의 하는 과정을 안내 하는 마법사가 시작 됩니다.

5. 아래 차트에서 권장 하는 대로 정책에 대 한 이름, 설명 및 설정을 지정 합니다. 자세한 내용은 [Microsoft Defender For Office 365 옵션의 피싱 방지 정책에 대 한](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)자세한 내용을 참조 하세요.

6. 설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장** 을 선택 합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인 및 가장 귀중 한 캠페인 직원|
|설명|가장 중요 한 직원과 해당 도메인이 가장 되 고 있지 않은지 확인 합니다.|
|보호할 사용자를 추가|**조건을 추가 하 고 받는 사람** 을 선택 합니다. 사용자 이름을 입력 하거나 후보, 캠페인 관리자 및 기타 중요 교직원 구성원의 전자 메일 주소를 입력 합니다. 가장을 보호 하려는 최대 20 개의 내부 및 외부 주소를 추가할 수 있습니다.|
|보호할 도메인을 추가|**조건 추가, 받는 사람 도메인** 을 차례로 선택 합니다. Microsoft 365 구독에 연결 된 사용자 지정 도메인 (하나를 정의한 경우)을 입력 합니다. 둘 이상의 도메인을 입력할 수 있습니다.|
|작업 선택|가장 된 사용자가 전자 메일을 보낸 경우: **다른 전자 메일 주소로 메시지 리디렉션을** 선택 하 고 보안 관리자의 전자 메일 주소를 입력 합니다. 예를 들어 *Alice <span> <span> @contoso 합니다.* <br/> 가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.|
|사서함 인텔리전스|새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.|
|신뢰할 수 있는 발신자와 도메인 추가|여기에서 자체 도메인 또는 다른 트러스트 된 도메인을 추가할 수 있습니다.|
|적용 대상|**받는 사람의 도메인이 다음과 같음** 을 선택합니다. **이러한 항목 모두** 아래에서 **선택** 을 선택합니다. **+ 추가** 를 선택합니다. 도메인 이름 (예: contoso) 옆에 있는 확인란을 선택 합니다 *. <span> <span> com* 의 목록에서 **추가** 를 선택 합니다. **완료** 를 선택합니다.|

자세한 내용은 [Defender for 피싱 정책에서 Office 365를](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)참조 하세요.

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Office 365 용 Defender를 사용 하 여 악성 첨부 파일 및 링크 로부터 보호

![를 가리키는 배너 https://aka.ms/aboutM365preview 입니다.](../media/m365admincenterchanging.png)

먼저 관리 센터에서 <https://admin.microsoft.com> 새 관리 센터 미리 보기가 설정 되어 있는지 확인 합니다. 텍스트 옆의 토글을 **새 관리 센터로** 설정 합니다.

   ![새 관리 센터 미리 보기가 설정 되어 있습니다.](../media/previewon.png)

아직 테 넌 트에 카드가 포함 된 **설정** 페이지가 표시 되지 않으면 보안 & 준수 센터에서 다음 단계를 완료 하는 방법을 참조 하세요. 보안 [& 준수 센터에서 안전한 첨부 파일 설정](#set-up-safe-attachments-in-the-security--compliance-center) 및 [Security & 준수 센터에서 안전한 링크 설정을](#set-up-safe-links-in-the-security--compliance-center)참조 하세요.

1. 왼쪽 탐색 창에서 **설치** 를 선택 합니다.
2. **설정** 페이지에서 **고급 위협 으로부터 보호 강화** 카드에서 **보기** 를 선택 합니다.

   ![고급 위협 으로부터 보호 향상에서 보기를 선택 합니다.](../media/startatp.png)

3. **고급 위협 으로부터 보호 기능 향상** 페이지에서 **시작** 을 선택 합니다.
4. 열려 있는 창에서 **전자 메일의 링크 및 첨부** 파일 옆에 있는 확인란을 선택 하 고 **SharePoint, OneDrive 및 팀** 에서 검색 항목, **office desktop 및 office Online 앱에서** 바이러스 검사 링크를 클릭 하 여 **악성 콘텐츠** 를 검사 합니다.

   **전자 메일의 링크 및 첨부 파일** 에서 모든 사용자 또는 전자 메일을 스캔할 특정 사용자를 입력 합니다.

   ![고급 위협의 보호 수준에서 모든 확인란을 선택 합니다.](../media/setatp.png)

5. 안전한 첨부 파일 및 안전한 링크를 설정 하려면 **정책 만들기** 를 선택 합니다.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>보안 & 준수 센터에서 안전한 첨부 파일 설정

사용자가 문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유 합니다. 전자 메일 메시지를 확인 하기만 하면 첨부 파일이 안전한 지 또는 악의적 임을 쉽게 알 수 있습니다. Microsoft Defender for Office 365에는 안전한 첨부 파일 보호가 포함 되어 있지만이 보호 기능은 기본적으로 설정 되어 있지 않습니다. 이 보호 기능을 사용 하기 시작 하는 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft 팀의 파일로 확장 됩니다.

안전한 첨부 파일 정책을 만들려면 [이 짧은 비디오](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)를 시청 하거나 다음 단계를 완료 합니다.

1. 으로 이동 하 <https://protection.office.com> 고 관리자 계정으로 로그인 합니다.

2. 보안 & 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리** 에서 **정책을** 선택 합니다.

3. 정책 페이지에서 **안전한 첨부 파일** 을 선택 합니다.

4. 안전한 첨부 파일 페이지에서 **SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP 설정** 확인란을 선택 하 여이 보호를 광범위 하 게 적용 합니다.

5. **+** 새 정책을 만들려면 선택 합니다.

6. 다음 표의 설정을 적용 합니다.

7. 설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장** 을 선택 합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|검색 된 맬웨어로부터 현재 및 향후 전자 메일을 차단 합니다.|
|설명|검색 된 맬웨어로부터 현재 및 향후 전자 메일 및 첨부 파일을 차단 합니다.|
|첨부 파일 저장 알 수 없는 맬웨어 응답|차단 됨을 선택 하 고 **검색 된 맬웨어로부터 현재 및 앞으로의 전자 메일 및 첨부 파일을 차단** 합니다.|
|검색 시 첨부 파일 리디렉션|리디렉션 사용 (이 상자 선택) <br/> 격리를 위해 관리자 계정 또는 사서함 설정을 입력 합니다. <br/> 첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하면 (이 상자를 선택 하십시오.) 위의 선택 사항을 적용 합니다.|
|적용 대상|받는 사람 도메인은입니다. . . 도메인을 선택 합니다.|

자세한 내용은 [Defender for 피싱 정책에서 Office 365를](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)참조 하세요.

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>보안 & 준수 센터에서 안전한 링크 설정

해커는 전자 메일 이나 다른 파일의 링크에서 악성 웹 사이트를 숨기는 경우가 있습니다. Microsoft Defender for Office 365에 포함 된 안전한 링크는 전자 메일 메시지 및 Office 문서에서 웹 주소 (Url)를 클릭 하 여 확인 하는 시간을 제공 하 여 조직을 보호 하는 데 도움이 될 수 있습니다. 보호는 안전한 링크 정책을 통해 정의 됩니다.

다음을 수행 하는 것이 좋습니다.

- 기본 정책을 수정 하 여 보호를 강화 합니다.

- 도메인의 모든 받는 사람을 대상으로 하는 새 정책을 추가 합니다.

안전한 링크를 설정 하려면 [이 간략 한 교육 비디오](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)를 시청 하거나 다음 단계를 완료 하세요.

1. 으로 이동 하 <https://protection.office.com> 고 관리자 계정으로 로그인 합니다.

2. 보안 & 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리** 에서 **정책을** 선택 합니다.

3. 정책 페이지에서 **안전한 링크** 를 선택 합니다.

기본 정책을 수정 하려면 다음을 수행 합니다.

1. 안전한 링크 페이지의 **전체 조직에 적용 되는 정책** 에서 **기본** 정책을 선택 합니다.

2. **전자 메일을 제외 하 고 콘텐츠에 적용 되는 설정** 아래에서 **Microsoft 365 앱 For enterprise, iOS 및 Android 용 Office를** 선택 합니다.

3. **저장** 을 클릭합니다.

도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들려면 다음을 수행 합니다.

1. 안전한 링크 페이지의 **전체 조직에 적용 되는 정책** 에서를 클릭 하 여 **+** 새 정책을 만듭니다.

2. 다음 표에 나와 있는 설정을 적용 합니다.

3. **저장** 을 클릭합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인의 모든 받는 사람에 대 한 안전한 링크 정책|
|메시지에서 알 수 없는 잠재적 악성 Url에 대 한 작업 선택|**Url 선택-사용자가 링크를 클릭할 때 알려진 악성 링크 목록에 대해 다시 작성 및 확인** 합니다.|
|다운로드 가능한 콘텐츠를 검색 하기 위해 안전한 첨부 파일 사용|이 상자를 선택 합니다.|
|적용 대상|받는 사람 도메인은입니다. . . 도메인을 선택 합니다.|

자세한 내용은 [Defender For Office 365의 안전한 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)를 참조 하세요.

## <a name="turn-on-the-unified-audit-log"></a>통합 된 감사 로그 설정

보안 & 준수 센터에서 감사 로그 검색을 설정한 후에는 로그에서 관리자 및 기타 사용자 작업을 유지 하 고 검색할 수 있습니다.

Microsoft 365 구독에서 감사 로그 검색을 설정 하거나 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다. 기본적으로이 역할은 Exchange 관리 센터의 사용 권한 페이지에 있는 준수 관리 및 조직 관리 역할 그룹에 할당 됩니다. Microsoft 365의 전역 관리자는 기본적으로이 그룹의 구성원입니다.

1. 감사 로그 검색을 켜려면 <https://admin.microsoft.com> 왼쪽 탐색 창의 **관리 센터** 에서 **준수** 를 선택 합니다.
2. **Microsoft 365 준수** 페이지에서 **기타 리소스** 를 선택한 다음 **Office 365 보안 & 센터** 카드에서 **엽니다** .

    ![보안 & 준수 자동차에서 열기를 선택 합니다.](../media/gotosecandcomp.png)
3. 보안 및 준수 페이지에서 **검색** 을 선택한 후 **감사 로그 검색** 을 선택 합니다.
4. **감사 로그 검색** 페이지 맨 위에서 **감사 사용** 을 선택 합니다.

기능이 설정 되 면 파일, 폴더 및 여러 작업을 검색할 수 있습니다. 자세한 내용은 [search the audit log](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)을 참조 하십시오.

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>SharePoint 및 OneDrive 파일 및 폴더에 대 한 조정 익명 공유 설정

기본 익명 링크 만료를 14 일로 변경 하 고 기본 공유 유형을 "특정 사용자"로 변경 합니다. OneDrive 및 SharePoint에 대 한 공유 설정을 변경 하려면:

1. 관리 센터로 이동한 <https://admin.microsoft.com> 후 왼쪽 탐색 창의 **관리 센터** 아래에서 **SharePoint** 를 선택 합니다.
2. SharePoint 관리 센터에서 **정책** \> **공유** 로 이동 합니다.
3. **공유** 페이지의 **파일 및 폴더 링크** 에서 **특정 사용자** 를 선택 하 고, **"모든 사용자" 링크에 대 한 고급 설정** 에서 **이러한 링크는이 며칠 이내에 만료 되어야 함** 을 선택 하 고 14 (연결 수명 범위를 제한 하려는 또 다른 일 수)를 입력 합니다.

   ![특정 사용자를 선택 하 고 연결 만료 날짜를 14 일로 설정 합니다.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>활동 알림

활동 알림을 사용 하 여 관리자 및 사용자 활동을 추적 하 고 조직의 맬웨어 및 데이터 손실 방지 인시던트를 검색할 수 있습니다. 구독에 기본 정책 집합이 포함 되어 있지만 사용자 지정 정책을 만들 수도 있습니다. 자세한 내용은 [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)참조 하세요. 예를 들어 외부에서 사용자를 공유 하지 않으려는 중요 한 파일을 SharePoint에 저장 하는 경우 누군가가이를 공유 하는 경우이를 알리는 알림을 만들 수 있습니다.

다음 그림에는 Microsoft 365에 포함 된 기본 정책이 나와 있습니다.

![Microsoft 365에 포함 된 기본 경고 정책](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>일정 공유를 사용 하지 않도록 설정 또는 관리

조직의 사용자가 일정을 공유 하지 못하도록 하거나, 공유할 수 있는 항목을 관리할 수도 있습니다. 예를 들어 약속 있음/없음 시간만으로 공유를 제한할 수 있습니다.

1. 관리 센터로 이동 <https://admin.microsoft.com> 하 여 **설정** \> **서비스 & 추가 기능** 을 선택 합니다.
2. **서비스 & 추가 기능** 페이지에서 **일정** 을 선택 하 고 조직의 사용자가 Office 365 또는 Exchange를 사용 하는 외부 사용자와 일정을 공유할 수 있는지 여부를 선택 합니다.

   모든 사용자와 공유 옵션을 선택 하는 경우 약속 있음/없음 정보만 공유 하도록 결정할 수 있습니다.

3. 페이지 아래쪽에서 **변경 내용 저장** 을 선택 합니다.

   다음 그림에서는 허용 되지 않는 일정 공유를 보여 줍니다.

   ![허용 되지 않는 외부 일정 공유를 표시 하는 스크린샷](../media/nocalendarsharing.png)

   다음 그림에서는 약속 있음/없음 정보만 있는 전자 메일 링크와 함께 일정 공유를 사용할 수 있는 설정을 보여 줍니다.

   ![모든 사용자와 약속 있음/없음 일정 공유 스크린샷](../media/sharefreebusy.png)

사용자가 일정을 공유할 수 있는 경우 웹용 Outlook에서 공유 하는 방법에 대 한 [다음 지침](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) 을 참고 하세요.
