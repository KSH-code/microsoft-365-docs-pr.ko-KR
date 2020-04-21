---
title: Microsoft 365 비즈니스에 대 한 위협 요소 보호 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection을 설정 하 고 피싱, 맬웨어 및 기타 위협 으로부터 중요 한 데이터를 보호 합니다.
ms.openlocfilehash: 2dd75b20bf203b9b8f0cdefb2459c45d1d0ccec1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627129"
---
# <a name="increase-threat-protection"></a>위협 방지 강화

이 문서는 Microsoft 365 구독의 보호를 향상 시켜 피싱, 맬웨어 및 기타 위협 으로부터 보호 하는 데 도움이 됩니다. 이러한 권장 사항은 법률 사무소 및 의료 보험 clinics 같은 보안 요구 사항이 증가 하는 조직에 적합 합니다.

시작 하기 전에 Office 365 보안 점수를 확인 하세요. Office 365 안전한 점수는 정규 활동 및 보안 설정에 따라 조직의 보안을 분석 하 고 점수를 할당 합니다. 먼저 현재 점수를 기록 합니다. 점수를 높이려면이 문서에서 권장 하는 작업을 완료 하세요. 목표는 최대 점수를 얻는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호 하기 위한 기회를 얻기 위한 것입니다. 

자세한 내용은 [Microsoft 보안 점수](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)를 참조 하세요.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>메일에서 맬웨어에 대 한 보호 수준 올리기

Office 365 또는 Microsoft 365 환경에는 맬웨어에 대 한 보호 기능이 포함 되어 있습니다. 일반적으로 맬웨어에 사용 되는 파일 형식을 사용 하 여 첨부 파일이 차단 되므로이 보호를 강화할 수 있습니다. 전자 메일에서 맬웨어 보호를 강화 하려면:
  
1. 으로 이동 [https://protection.office.com](https://protection.office.com) 하 고 관리자 계정 자격 증명으로 로그인 합니다. 
    
2. 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책** \> **맬웨어 방지**를 선택 합니다.
    
3. 기본 정책을 두 번 클릭 하 여이 회사 차원의 정책을 편집 합니다.
    
4. **설정**을 선택합니다.
    
5. **일반 첨부 파일 형식 필터**에서 **설정**를 선택 합니다. 차단 되는 파일 형식은이 컨트롤 바로 아래의 창에 나열 됩니다. 다음 파일 형식을 추가 했는지 확인 합니다.
   - ade, adp, ani, bas, bat, chm, cmd, a, m, s, com, cpl, crt, .hlp, ht, mdz, inf, v p v, ini, 작업, js, shs, 모바일,, mde, msi, wsc, .pcd, s p l, exe, .wsf 인  <br/> 
   
   필요한 경우 나중에 파일 형식을 추가 하거나 삭제할 수 있습니다.
    
6. **저장을 선택 합니다.**
    
자세한 내용은 [맬웨어 방지 보호](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)를 참조 하세요.
  
## <a name="protect-against-ransomware"></a>랜섬웨어로부터 보호

랜 섬 웨어는 파일 암호화 또는 컴퓨터 화면 잠금을 통해 데이터에 대 한 액세스를 제한 합니다. 그런 다음 일반적으로 데이터에 액세스 하기 위해 exchange에서 "ransom" (예를 들어, Bits 동전) 형식을 사용 하 여 victims에서 ort money를 요청 합니다. 
  
랜 섬 웨어 로부터 보호 하려면 메일 흐름 규칙을 하나 이상 만들어 랜 섬 웨어에 일반적으로 사용 되는 파일 확장명을 차단 합니다. ( [메일 단계에서 맬웨어에 대 한 보호 수준 올리기](#raise-the-level-of-protection-against-malware-in-mail) 에서 이러한 규칙을 추가 했습니다.) 전자 메일로 이러한 첨부 파일을 받는 사용자에 게 경고할 수도 있습니다.

이전 단계에서 차단한 파일 외에도 매크로를 포함 하는 Office 첨부 파일을 열기 전에 사용자에 게 경고 하는 규칙을 만드는 것이 좋습니다. 매크로 내에서 랜 섬 웨어를 숨길 수 있으므로 사용자가 알지 못하는 사용자 로부터 이러한 파일을 열지 않도록 경고 메시지를 표시 합니다.

메일 전송 규칙을 만들려면 다음을 수행 합니다.
  
1. 관리 센터 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>()로 이동 하 고 **관리 센터** \> **Exchange**를 선택 합니다.
    
2. **메일 흐름** 범주에서 **규칙**을 선택 합니다.
    
3. 를 **+** 선택한 다음 **새 규칙 만들기**를 선택 합니다.
    
4. 대화 상자 아래쪽의 **기타 옵션** 을 선택 하 여 전체 옵션 집합을 표시 합니다. 
    
5. 다음 표에 해당 규칙에 대 한 설정을 적용 합니다. 나머지 설정에 대해서는 기본값을 변경 하지 않는 한 기본 값을 사용 합니다.
    
6. **저장**을 선택합니다.
    
|**설정**|**Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시**||
|:-----|:-----|:-----|
|이름  <br/> |랜 섬 웨어 방지 규칙: 사용자에 게 경고 표시  <br/>  |
|다음 경우에이 규칙을 적용 합니다. . .  <br/> |모든 첨부 파일 . . 일치 하는 파일 확장명 . .  <br/> |
|단어 또는 구 지정  <br/> |다음 파일 형식을 추가 합니다.  <br/> normal.dotm, .docm, .xlsm, sltm, .xla, xlam, xll, pptm, potm, ppam, ppsm, sltm  <br/>|
|다음을 수행 합니다. . .  <br/> |받는 사람에게 메시지로 알림  <br/> |
|메시지 텍스트 제공  <br/> |악성 코드가 포함 된 매크로를 포함할 수 있으므로 모르는 사용자 로부터 이러한 유형의 파일을 열지 마십시오.  <br/> |
   
자세한 내용은 다음을 참조하세요.
  
- [랜 섬 웨어를 처리 하는 방법](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [OneDrive 복원](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>전자 메일에 대 한 자동 전달 중지

사용자의 사서함에 대 한 액세스 권한을 획득 하는 해커는 자동으로 전자 메일을 전달 하도록 사서함을 설정 하 여 메일을 도용할 수 있습니다. 사용자의 인식이 없어도이 문제가 발생할 수 있습니다. 이러한 상황이 발생 하지 않도록 하려면 메일 흐름 규칙을 구성 합니다. 
  
메일 전송 규칙을 만들려면 [이 짧은 비디오](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 를 시청 하거나 다음 단계를 수행 합니다.
  
1. Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.
    
2. **메일 흐름** 범주에서 **규칙**을 선택 합니다.
    
3. 를 **+** 선택한 다음 **새 규칙 만들기**를 선택 합니다.
    
4. 모든 옵션을 보려면 대화 상자 아래쪽에서 **기타 옵션** 을 선택 합니다. 
    
5. 다음 표의 설정을 적용 합니다. 나머지 설정에 대해서는 기본값을 변경 하지 않는 한 기본 값을 사용 합니다.
    
6. **저장**을 선택합니다.
    
|**설정**|**Office 파일의 첨부 파일을 열기 전에 사용자에 게 경고 표시**|
|:-----|:-----|
|이름  <br/> |외부 도메인에 대 한 전자 메일 자동 전달 금지  <br/> |
|다음 경우에이 규칙 적용 ...  <br/> |보낸 사람입니다. . . 은 외부/내부입니다. . . 조직 내부  <br/> |
|조건 추가  <br/> |메시지 속성 . . 메시지 유형을 포함 합니다. . . 자동 전달  <br/> |
|다음을 수행 합니다.  <br/> |메시지를 차단 합니다. . . 메시지를 거부 하 고 설명을 포함 합니다.  <br/> |
|메시지 텍스트 제공  <br/> |보안상의 이유로이 조직 외부에서 전자 메일을 자동 전달 하는 것은 허용 되지 않습니다.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>피싱 공격 으로부터 전자 메일을 보호 합니다.

Office 365 또는 Microsoft 365 환경용으로 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호 기능을 구성할 수 있습니다. ATP 피싱 방지 보호, Office 365 Advanced Threat Protection의 일부분은 악의적인 가장 기반 피싱 공격과 기타 피싱 공격 으로부터 조직을 보호 하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성 하지 않은 경우에는이 작업을 수행 하지 않아도 됩니다.
  
가장 중요 한 사용자와 사용자 지정 도메인을 보호 하는 정책을 만들어이 보호를 시작 하는 것이 좋습니다. 

ATP 피싱 방지 정책을 만들려면 [이 간략 한 교육 비디오](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)를 시청 하거나 다음 단계를 완료 하세요.
  
1. [https://protection.office.com](https://protection.office.com)으로 이동합니다. 
    
2. 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.
    
3. **정책** 페이지에서 **ATP 피싱 방지**를 선택 합니다.
    
4. **피싱 방지** 페이지에서 **+ 만들기**를 선택 합니다. 피싱 방지 정책을 정의 하는 과정을 안내 하는 마법사가 시작 됩니다.
    
5. 다음 표에 나와 있는 것 처럼 정책에 대 한 이름, 설명 및 설정을 지정 합니다. 자세한 내용은 [ATP 피싱 방지 정책 옵션에 대 한](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options)정보를 참조 하세요. 
    
6. 설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장**을 선택 합니다.
    

|**설정 또는 옵션**<br/>|**권장 설정** <br/>|
|:-----|:-----|
|이름  <br/> |도메인 및 가장 귀중 한 캠페인 직원  <br/> |
|설명  <br/> |가장 중요 한 직원과 해당 도메인이 가장 되 고 있지 않은지 확인 합니다.  <br/> |
|보호할 사용자를 추가  <br/> |**조건을 추가 하 고 받는 사람**을 선택 합니다. 사용자 이름을 입력 하거나 후보, 캠페인 관리자 및 기타 중요 교직원 구성원의 전자 메일 주소를 입력 합니다. 가장을 보호 하려는 최대 20 개의 내부 및 외부 주소를 추가할 수 있습니다.  <br/> |
|보호할 도메인을 추가  <br/> |**조건 추가, 받는 사람 도메인**을 차례로 선택 합니다. Microsoft 365 구독에 연결 된 사용자 지정 도메인 (하나를 정의한 경우)을 입력 합니다. 둘 이상의 도메인을 입력할 수 있습니다.  <br/> |
|작업 선택  <br/> |가장 된 사용자가 전자 메일을 보낸 경우: **다른 전자 메일 주소로 메시지 리디렉션을**선택 하 고 보안 관리자의 전자 메일 주소를 입력 합니다. 예를 들어 *Alice<span><span>@contoso 합니다.* 가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지**를 선택합니다.  <br/> |
|사서함 인텔리전스  <br/> |새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐**에 둡니다.  <br/> |
|신뢰할 수 있는 발신자와 도메인 추가  <br/> |여기에서 자체 도메인 또는 다른 트러스트 된 도메인을 추가할 수 있습니다.  <br/> |
|적용 대상  <br/> |**받는 사람의 도메인이 다음과 같음**을 선택합니다. **이러한 항목 모두** 아래에서 **선택**을 선택합니다. **+ 추가**를 선택합니다. 도메인 이름 (예: contoso) 옆에 있는 확인란을 선택 합니다 *.<span> com <span>* 의 목록에서 **추가**를 선택 합니다. **완료**를 선택합니다.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>ATP 안전한 첨부 파일을 사용 하 여 악의 있는 첨부 파일과 파일을 보호 합니다.

사용자가 문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유 합니다. 전자 메일 메시지를 확인 하기만 하면 첨부 파일이 안전한 지 또는 악의적 임을 쉽게 알 수 있습니다. Office 365 Advanced Threat Protection은 ATP Safe 첨부 파일 보호를 포함 하지만이 보호 기능은 기본적으로 설정 되어 있지 않습니다. 이 보호 기능을 사용 하기 시작 하는 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft 팀의 파일로 확장 됩니다.
  
ATP 안전한 첨부 파일 정책을 만들려면 [이 짧은 비디오](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)를 시청 하거나 다음 단계를 완료 합니다.
  
1. [https://protection.office.com](https://protection.office.com)으로 이동 하 고 관리자 계정으로 로그인 합니다. 
    
2. 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.
    
3. 정책 페이지에서 **ATP 안전한 첨부 파일**을 선택 합니다.
    
4. 안전한 첨부 파일 페이지에서 **SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP 설정** 확인란을 선택 하 여이 보호를 광범위 하 게 적용 합니다. 
    
5. 새 **+** 정책을 만들려면 선택 합니다. 
    
6. 다음 표의 설정을 적용 합니다. 
    
7. 설정을 검토 한 후에는 **이 정책 만들기** 또는 적절 한 **저장**을 선택 합니다.
    

|**설정 또는 옵션**|**권장 설정** <br/>|
|:-----|:-----|
|이름  <br/> |검색 된 맬웨어로부터 현재 및 향후 전자 메일을 차단 합니다.  <br/> |
|설명  <br/> |검색 된 맬웨어로부터 현재 및 향후 전자 메일 및 첨부 파일을 차단 합니다.  <br/> |
|첨부 파일 저장 알 수 없는 맬웨어 응답  <br/> |차단 됨을 선택 하 고 **검색 된 맬웨어로부터 현재 및 앞으로의 전자 메일 및 첨부 파일을 차단**합니다.  <br/> |
|검색 시 첨부 파일 리디렉션  <br/> |리디렉션 사용 (이 상자를 선택 합니다.) 격리를 위해 관리자 계정 또는 사서함 설정을 입력 합니다.          첨부 파일에 대 한 맬웨어 검사 시간이 초과 되거나 오류가 발생 하면 (이 상자를 선택 하십시오.) 위의 선택 사항을 적용 합니다.  <br/> |
|적용 대상  <br/> |받는 사람 도메인은입니다. . . 도메인을 선택 합니다.  <br/> |
   
자세한 내용은 [Set Up Office 365 ATP 피싱 방지 정책](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)를 참조 하세요.
  
## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>ATP 안전한 링크를 통한 피싱 공격 으로부터 보호

해커는 전자 메일 이나 다른 파일의 링크에서 악성 웹 사이트를 숨기는 경우가 있습니다. Office 365 ATP 안전한 링크 (ATP 안전한 링크)는 Office 365 Advanced Threat Protection의 일부 이며, 전자 메일 메시지 및 Office 문서에서 웹 주소 (Url)를 클릭 하 여 확인할 시간을 제공 하 여 조직을 보호 하는 데 도움이 될 수 있습니다. 보호는 ATP 안전한 링크 정책을 통해 정의 됩니다.
  
다음을 수행 하는 것이 좋습니다.
  
- 기본 정책을 수정 하 여 보호를 강화 합니다.
    
- 도메인의 모든 받는 사람을 대상으로 하는 새 정책을 추가 합니다.
    
ATP 안전한 링크를 설정 하려면 [이 간략 한 교육 비디오](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)를 시청 하거나 다음 단계를 완료 하세요.
  
1. [https://protection.office.com](https://protection.office.com)으로 이동 하 고 관리자 계정으로 로그인 합니다. 
    
2. 보안 &amp; 및 준수 센터의 왼쪽 탐색 창에 있는 **위협 관리**에서 **정책을**선택 합니다.
    
3. 정책 페이지에서 **ATP 안전한 링크**를 선택 합니다.
    
기본 정책을 수정 하려면 다음을 수행 합니다.
  
1. 안전한 링크 페이지의 **전체 조직에 적용 되는 정책**에서 **기본** 정책을 선택 합니다. 
    
2. **전자 메일을 제외 하 고 콘텐츠에 적용 되는 설정**아래에서 **Microsoft 365 앱 For enterprise, iOS 및 Android 용 Office를**선택 합니다.
    
3. **저장**을 선택합니다. 
    
도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들려면 다음을 수행 합니다.
  
1. 안전한 링크 페이지의 **전체 조직에 적용 되는 정책**에서 새 정책을 만들도록 선택 **+** 합니다. 
    
2. 다음 표에 나와 있는 설정을 적용 합니다.
    
3. **저장**을 선택합니다. 

|**설정 또는 옵션**|**권장 설정** <br/>|
|:-----|:-----|
|이름  <br/> |도메인의 모든 받는 사람에 대 한 안전한 링크 정책  <br/> |
|메시지에서 알 수 없는 잠재적 악성 Url에 대 한 작업 선택  <br/> |**Url 선택-사용자가 링크를 클릭할 때 알려진 악성 링크 목록에 대해 다시 작성 및 확인**합니다.  <br/> |
|다운로드 가능한 콘텐츠를 검색 하기 위해 안전한 첨부 파일 사용  <br/> |이 상자를 선택 합니다.  <br/> |
|적용 대상  <br/> |받는 사람 도메인은입니다. . . 도메인을 선택 합니다.  <br/> |
   
자세한 내용은 [Office 365 ATP 안전한 링크](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)를 참조 하세요.

## <a name="go-to-intune-admin-center"></a>Intune 관리 센터로 이동합니다.

1. [Azure 포털](https://portal.azure.com/)에 로그인 합니다.

2. **모든 서비스**를 선택하고 **검색 상자**에 *Intune*을 입력합니다.

3. 결과가 표시 되 면 **Microsoft Intune** 옆에 있는 시작을 선택 하 여 즐겨찾기로 지정 하 고 나중에 쉽게 찾을 수 있도록 합니다.

관리 센터 외에도 Intune을 사용 하 여 조직의 장치를 등록 하 고 관리할 수 있습니다. 자세한 내용은 [Windows 장치용 등록 방법](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) 및 [Intune으로 관리 되는 장치에 대 한 등록 옵션](https://docs.microsoft.com/intune/enrollment-options)의 기능을 참조 하세요.
